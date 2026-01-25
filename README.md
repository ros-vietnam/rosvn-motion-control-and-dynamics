# ROS Vietnam – Motion Control, Dynamics & Actuation  
`rosvn-motion-control-and-dynamics`

> **A research-grade repository for robot motion control, system dynamics, and actuation algorithms in ROS 2.**

---

## 1. Overview

**ROS Vietnam Motion Control, Dynamics & Actuation** is the official control-focused repository of the **ROS Vietnam** community.

This repository addresses the **lowest and most critical layer of robotics autonomy**:
- Motion control
- Robot dynamics
- Actuation modeling
- Control stability and robustness

The repository is **simulation-first**, hardware-agnostic, and academically rigorous.

---

## 2. Why This Repository Matters

Many robotics projects fail not because of perception or planning,
but because of **poor control and unmodeled dynamics**.

This repository exists to:
- Bridge control theory and real-world robotics
- Promote physically-consistent modeling
- Enable reproducible control experiments
- Educate contributors in *correct* robotics engineering

> *Autonomy collapses without stable control.*

---

## 3. Philosophy

### 3.1 Physics First
- Control must respect dynamics
- No magic gains
- No unmodeled forces

### 3.2 Stability Before Performance
- Convergence > speed
- Robustness > tuning tricks

### 3.3 Reproducibility
- Fixed time steps
- Deterministic controllers
- Explicit actuator models

### 3.4 Hardware-Agnostic Design
- No vendor-specific drivers
- Abstracted actuator interfaces
- Portable controllers

---

## 4. Scope & Focus

### In Scope
- Kinematic and dynamic modeling
- Low-level motion control
- Trajectory tracking
- Actuator modeling
- Disturbance rejection
- Control benchmarking

### Out of Scope
- Hardware drivers
- Vendor SDKs
- Application-level behaviors
- High-level autonomy logic

---

## 5. Control Domains

### 5.1 Kinematics
- Differential drive
- Ackermann steering
- Omnidirectional bases
- Mobile manipulator kinematics (research)

### 5.2 Dynamics
- Rigid body dynamics
- Wheel–ground interaction
- Friction and slip modeling
- Payload effects

### 5.3 Control Methods
- PID / Cascaded PID
- LQR / iLQR
- MPC
- Sliding Mode Control
- Adaptive control (research)

### 5.4 Actuation
- DC motor models
- BLDC / PMSM abstraction
- Torque vs velocity control
- Saturation and dead zones

---

## 6. Repository Structure

```bash

rosv-motion-control-and-dynamics/
├── README.md
├── docs/
│ ├── control-architecture.md
│ ├── dynamics-modeling.md
│ ├── actuator-models.md
│ ├── evaluation-metrics.md
│ └── contribution-guidelines.md
├── models/
│ ├── kinematics/
│ ├── dynamics/
│ └── actuators/
├── controllers/
│ ├── pid/
│ ├── lqr/
│ ├── mpc/
│ └── adaptive/
├── benchmarks/
│ ├── tracking/
│ ├── disturbance/
│ └── robustness/
├── evaluation/
│ ├── metrics/
│ ├── scripts/
│ └── visualization/
├── launch/
├── config/
├── tools/
└── .github/

```
---

## 7. Architecture Overview

All controllers must follow a **layered control architecture**:

1. Reference generation  
2. Trajectory tracking  
3. Low-level control  
4. Actuator command  
5. State feedback & logging  

Each controller must:
- Declare assumptions
- Specify stability conditions
- Provide tuning guidance

---

## 8. Simulation Dependency

This repository depends on: rosvn-sim-foundation


Simulation requirements:
- Accurate mass & inertia
- Actuator saturation
- Control loop timing
- Sensor latency

---

## 9. Evaluation & Metrics

### Core Metrics
- Tracking error
- Settling time
- Overshoot
- Control effort
- Energy proxy

### Robustness Metrics
- Disturbance rejection
- Parameter uncertainty
- Noise sensitivity
