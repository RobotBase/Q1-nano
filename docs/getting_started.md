# Getting Started | 快速上手

Welcome to Q1 nano! This guide will help you get up and running.

## Prerequisites | 前置要求

- **Git** — to clone the repository
- **Python 3.8+** — for simulation and training scripts
- **MuJoCo** — physics simulation engine ([installation guide](https://mujoco.readthedocs.io/en/stable/python.html))

### Recommended

- **SolidWorks** (optional) — to view/edit original CAD files (STEP files provided as universal alternative)
- **NVIDIA GPU** — for RL training acceleration (CPU works but is slower)

## Clone the Repository | 克隆仓库

```bash
git clone https://github.com/RobotBase/Q1-nano.git
cd Q1-nano
```

## Run Simulation | 运行仿真

> 🚧 **Coming Soon** — Simulation environment and pre-trained checkpoints are being uploaded.

```bash
# Install dependencies (coming soon)
pip install -r requirements.txt

# Run MuJoCo simulation with pre-trained policy (coming soon)
python simulation/mujoco/run_sim.py --checkpoint training/checkpoints/walking_v1.pt
```

## Build the Robot | 组装机器人

1. Check the [Bill of Materials (BOM)](bom.md) for all required parts
2. Follow the [Assembly Guide](assembly_guide.md) for step-by-step instructions
3. Flash the [firmware](../firmware/) to your controller board

## Next Steps | 下一步

- 📖 Read the [Architecture Overview](architecture.md) to understand the system design
- 🧠 Explore the [training code](../training/rl/) to understand the RL pipeline
- 🤝 Check [CONTRIBUTING.md](../CONTRIBUTING.md) to start contributing
