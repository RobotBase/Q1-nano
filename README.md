<div align="center">

# Q1 nano

### Open-Source Desktop Servo Humanoid Robot

**Reinforcement-Learning-Driven Gait · Full-Stack Open Source · Under ¥2,000 BOM**

[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](LICENSE)
[![Stars](https://img.shields.io/github/stars/RobotBase/Q1-nano?style=social)](https://github.com/RobotBase/Q1-nano)
[![Issues](https://img.shields.io/github/issues/RobotBase/Q1-nano)](https://github.com/RobotBase/Q1-nano/issues)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)

<!-- TODO: Replace with actual demo GIF/video -->
<!-- ![Q1 nano Walking Demo](media/demo_videos/walking_demo.gif) -->

*🚧 Demo video coming soon — stay tuned!*

[Getting Started](docs/getting_started.md) · [BOM](docs/bom.md) · [Assembly Guide](docs/assembly_guide.md) · [Architecture](docs/architecture.md)

---

</div>

## ✨ What is Q1 nano?

Q1 nano is a **desktop-sized servo humanoid robot** that walks with a natural, fluid gait — powered by **MuJoCo simulation** and **reinforcement learning**.

Traditional servo humanoid robots are known for stiff, jerky movements. Q1 nano breaks that stereotype by training walking policies in simulation and deploying them to real hardware, achieving smooth, human-like locomotion on standard hobby servos.

### 🎯 Key Features

| Feature | Description |
|---------|-------------|
| 🧠 **RL-Driven Gait** | Smooth walking trained via reinforcement learning in MuJoCo — not hand-tuned keyframes |
| 🔧 **Fully Reproducible** | Complete BOM, STEP files, URDF, assembly guide — build one at home |
| 💰 **Affordable** | Total BOM cost under ¥2,000 (~$275 USD) |
| 📐 **SolidWorks → URDF → MuJoCo → Real** | End-to-end pipeline from CAD to walking robot |
| 🌍 **Open Source** | Hardware, simulation, training, and firmware — everything is open |

## 🏗️ Project Structure

```
Q1-nano/
├── docs/                  # Documentation
│   ├── getting_started.md # Quick start guide
│   ├── bom.md             # Bill of Materials + purchase links
│   ├── assembly_guide.md  # Step-by-step assembly instructions
│   └── architecture.md    # System architecture overview
├── hardware/
│   ├── solidworks/        # Original SolidWorks CAD files
│   ├── step/              # STEP format (universal CAD exchange)
│   └── urdf/              # URDF model for simulation
├── simulation/
│   ├── mujoco/            # MuJoCo simulation environment
│   └── configs/           # Training & simulation configs
├── training/
│   ├── rl/                # Reinforcement learning training code
│   ├── checkpoints/       # Pre-trained model weights
│   └── scripts/           # Training & evaluation scripts
├── firmware/
│   ├── servo_control/     # Servo communication & control
│   └── main_controller/   # Main controller program
└── media/
    ├── demo_videos/       # Demo videos & GIFs
    └── renders/           # 3D renders & photos
```

## 🚀 Quick Start

> **Note:** Full quick-start instructions are under development. Check back soon!

```bash
# Clone the repository
git clone https://github.com/RobotBase/Q1-nano.git
cd Q1-nano

# Check out the docs
cat docs/getting_started.md
```

## 🗺️ Roadmap

- [x] Repository scaffolding & README
- [ ] Upload development history & existing codebase
- [ ] URDF model & MuJoCo simulation environment
- [ ] Demo video of RL-trained walking gait
- [ ] BOM & assembly guide
- [ ] v0.1 Release — community can clone → simulate → build
- [ ] Submit to awesome-robotics lists
- [ ] Community contributions & iteration

## 🤝 Contributing

We welcome contributions of all kinds! Whether it's fixing a typo, improving documentation, tuning RL parameters, or designing new gaits — every contribution matters.

Please read our [Contributing Guide](CONTRIBUTING.md) to get started.

Check out our [Good First Issues](https://github.com/RobotBase/Q1-nano/labels/good%20first%20issue) for beginner-friendly tasks.

## 📄 License

This project is licensed under the [Apache License 2.0](LICENSE).

---

<div align="center">

## 🇨🇳 中文说明

</div>

### Q1 nano 是什么？

Q1 nano 是一款**桌面级舵机人形机器人**，通过 **MuJoCo 仿真 + 强化学习**训练步态，实现丝滑自然的行走效果。

传统舵机人形机器人步态僵硬笨拙，Q1 nano 打破了这一刻板印象——在仿真环境中训练行走策略，再部署到真实硬件，用普通舵机实现接近人类的步态。

### 核心亮点

- 🧠 **强化学习驱动** — 非手调关键帧，而是 RL 训练出的自然步态
- 🔧 **完全可复现** — 从 BOM 清单到组装指南，在家就能造
- 💰 **低成本** — BOM 总成本 ¥2,000 以内
- 📐 **全链路开源** — SolidWorks → URDF → MuJoCo → 强化学习 → 真机部署
- 🌍 **全栈开放** — 硬件、仿真、训练、固件，一切开源

### 快速开始

```bash
git clone https://github.com/RobotBase/Q1-nano.git
cd Q1-nano
```

详细文档请查阅 [docs/](docs/) 目录。

### 参与贡献

欢迎任何形式的贡献！无论是修复文档、调参、训练新步态，都非常欢迎。

请先阅读 [贡献指南](CONTRIBUTING.md)。

---

<div align="center">

**If you find this project interesting, please give us a ⭐ — it helps a lot!**

**如果你觉得这个项目有意思，请给我们一个 ⭐ — 这对我们非常重要！**

</div>
