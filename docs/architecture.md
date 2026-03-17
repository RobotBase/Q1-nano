# System Architecture | 系统架构

## Overview | 概览

Q1 nano follows a **Sim-to-Real** pipeline: design the robot in CAD, simulate in MuJoCo, train walking policies with reinforcement learning, then deploy to real hardware.

```
┌─────────────┐    ┌──────────┐    ┌───────────┐    ┌──────────┐    ┌──────────┐
│ SolidWorks  │───▶│   URDF   │───▶│  MuJoCo   │───▶│ RL Train │───▶│  Deploy  │
│  (CAD)      │    │  Model   │    │ Simulation│    │ (Policy) │    │ (Real HW)│
└─────────────┘    └──────────┘    └───────────┘    └──────────┘    └──────────┘
```

## Pipeline Stages | 流水线阶段

### 1. Hardware Design (CAD → URDF)

- **Input**: Mechanical design in SolidWorks
- **Output**: URDF model file for simulation
- **Location**: `hardware/solidworks/`, `hardware/step/`, `hardware/urdf/`

The physical robot is designed in SolidWorks, exported as STEP for universal access, and converted to URDF for simulation compatibility.

### 2. Simulation (MuJoCo)

- **Input**: URDF model
- **Output**: Simulated environment for training
- **Location**: `simulation/mujoco/`, `simulation/configs/`

MuJoCo provides a fast, accurate physics simulation. The URDF model is loaded into MuJoCo, where we can run thousands of episodes in parallel for RL training.

### 3. Reinforcement Learning Training

- **Input**: MuJoCo simulation environment
- **Output**: Trained walking policy (neural network weights)
- **Location**: `training/rl/`, `training/checkpoints/`, `training/scripts/`

We use reinforcement learning (e.g., PPO) to train a walking policy. The agent learns to control joint positions to produce stable, natural-looking gait.

**Key Training Details:**
- Observation space: joint positions, velocities, body orientation (IMU)
- Action space: target joint positions for all servos
- Reward: forward velocity + stability + energy efficiency + style penalties

### 4. Deployment (Sim-to-Real Transfer)

- **Input**: Trained policy checkpoint
- **Output**: Walking robot 🤖
- **Location**: `firmware/servo_control/`, `firmware/main_controller/`

The trained policy is deployed to the real robot's microcontroller. The controller reads sensor data and outputs servo commands at ~50 Hz.

**Sim-to-Real Challenges:**
- Domain randomization during training for robustness
- Servo response delay compensation
- Real-world surface friction variation

## Hardware Architecture | 硬件架构

```
                    ┌─────────────────┐
                    │  Main Controller │
                    │  (ESP32/STM32)  │
                    └────────┬────────┘
                             │ Serial Bus
              ┌──────────────┼──────────────┐
              │              │              │
         ┌────┴────┐   ┌────┴────┐   ┌────┴────┐
         │ Servo 1 │   │ Servo 2 │   │ Servo N │
         │ (Hip L) │   │ (Hip R) │   │  (...)  │
         └─────────┘   └─────────┘   └─────────┘
```

- **12 DOF** (Degrees of Freedom): 6 per leg (hip yaw/roll/pitch, knee pitch, ankle pitch/roll)
- **Serial bus servos**: All servos on a single bus, addressed by ID
- **Control loop**: ~50 Hz policy inference → servo command
