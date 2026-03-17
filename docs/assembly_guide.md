# Assembly Guide | 组装指南

> 🚧 **Work in Progress** — Detailed step-by-step instructions with photos coming soon.

## Overview | 概览

The Q1 nano assembly process consists of the following major stages:

## Stage 1: Print Parts | 打印零件

1. Download STL/STEP files from [`hardware/step/`](../hardware/step/)
2. Print all structural components (see [BOM](bom.md) for printing specs)
3. Remove supports and clean up printed parts
4. Verify part fit before proceeding

## Stage 2: Assemble Lower Body | 组装下半身

1. Assemble hip joints (left/right)
2. Attach upper leg servos
3. Connect knee joints
4. Mount lower leg servos
5. Attach feet with rubber pads

## Stage 3: Assemble Upper Body | 组装上半身

1. Build torso frame
2. Mount shoulder servos
3. Assemble arms
4. Attach head mount (if applicable)

## Stage 4: Wiring | 接线

1. Connect all servos to the controller board (daisy-chain serial bus)
2. Wire the power system (battery → regulator → controller)
3. Double-check polarity before powering on!

## Stage 5: Controller & Firmware | 控制器与固件

1. Flash firmware to the main controller ([firmware guide](../firmware/))
2. Run servo calibration script
3. Verify all servo IDs are correctly assigned

## Stage 6: First Walk! | 第一步！

1. Place Q1 nano on a flat surface
2. Run the pre-trained walking policy
3. 🎉 Enjoy!

---

## Tools Required | 所需工具

- Phillips screwdriver (M2/M3)
- Hex key set
- Wire stripper
- Soldering iron (for power connections)
- 3D printer (or access to printing service)

## ⚠️ Safety Notes | 安全提示

- Always disconnect the battery before wiring
- Ensure correct voltage levels before powering servos
- Secure all cables to prevent snagging during operation
