# 无人机平台

> **Current Status:** 🚧 Hardware Construction & Architecture Design  
> **Latest Version:** v1.1.0 (Planning)

## 📖 Introduction
This repository documents the iterative development of a custom **250mm wheelbase quadrotor** designed for advanced autonomous navigation and control research. 

The goal is to build a robust hardware and software foundation, starting from classical SLAM and planning algorithms, and gradually migrating towards **Deep Reinforcement Learning (DRL)** based perception and control systems.

## 🛠️ Hardware Platform
The drone is built on a custom 250mm carbon fiber frame, featuring a high-performance compute module for onboard AI processing.

| Component | Model / Specs | Note |
| :--- | :--- | :--- |
| **Onboard Computer** | **NVIDIA Jetson Orin NX (8GB)** | Core computing unit |
| **Flight Controller**| **Holybro Pixhawk 4** | 32-bit, running PX4/ArduPilot |
| **LiDAR** | **Livox Mid-360** | Omnidirectional 3D LiDAR |
| **Depth Camera** | **Intel RealSense D435** | For VIO and depth sensing |
| **Frame** | **Custom Carbon Fiber (250mm)** | "Taobao" Custom Cut |
| **Motors** | **Koofly 2207 V2 (1960KV)** | 4S Power System |
| **ESC** | **EMAX BLHeli32 (45A)** | 4-in-1 ESC supported |
| **Battery** | **Gens Ace 4S 4000mAh** | Long endurance for computing |
| **Propellers** | **Gemfan 5147 (3-blade)** | Efficient 5-inch props |
| **RC System** | **RadioLink AT9S Pro + R12DSM** | Reliable control link |

📄 **For a complete list of parts, cables, and tools, please check the [BOM List](./BOM.md).**

## 🗺️ Roadmap & Versions

### ✅ v1.0.0: The Visual Baseline
**Focus:** Establishing a stable flight platform using Visual-Inertial Odometry (VIO).
* **Localization:** [VINS-Fusion](https://github.com/HKUST-Aerial-Robotics/VINS-Fusion) (Stereo + IMU)
* **Planning:** [EGO-Planner](https://github.com/ZJU-FAST-Lab/ego-planner)
* **Key Hardware:** Jetson NX + D435

### 🚀 v1.1.0: Lidar-Inertial Upgrade (Current Target)
**Focus:** Integrating Livox Mid-360 for robust, high-precision localization in complex environments.
* **Localization:** [Fast-LIVO2](https://github.com/hku-mars/FAST-LIVO) (LiDAR-Inertial-Visual Odometry)
* **Planning:** [EGO-Planner](https://github.com/ZJU-FAST-Lab/ego-planner)
* **Key Hardware:** Jetson NX + Mid360 + D435
* *Note: This version aims to leverage the wide FOV of Mid-360 for better obstacle avoidance.*

### 🔮 Future Goals: Intelligent Control
**Focus:** Advanced research driven by Deep Reinforcement Learning.
* End-to-end Navigation using DRL.
* Sim-to-Real transfer for complex maneuvers.
* Integration of Neural Network-based perception modules.

## 📂 Repository Structure
```text
.
├── BOM.csv             # Detailed Hardware Bill of Materials
├── docs/               # System diagrams and design notes
├── scripts/            # (Coming Soon) Setup scripts for Jetson
└── README.md           # This file
