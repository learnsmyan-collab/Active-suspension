# Active Suspension Control System (PID & System Dynamics)

## 1. System Overview
* Repository implements a closed-loop Proportional-Integral-Derivative (PID) control architecture coupled with a vehicle dynamics plant model.
* Simulation environment: MATLAB/Simulink.
* Primary objective: Suppress transient vibration profiles and optimize mechanical system settling time.

## 2. System Architecture
* Plant model utilizes modular subsystems to manage feedback loops and signal propagation.
* Model visualization asset:

![Simulink Block Diagram](outputs/active_suspension.png)

## 3. Execution & Verification Workflow
* Pre-execution workspace validation executed via initialization script (`active_code.m`).
* Data logging configured using Simulink `Dataset` logging format for programmatic post-processing.
* Transient response waveform exported at 300 DPI resolution:

![System Response Scope](outputs/ScopeactiveToFigure.png)

## 4. Repository Directory Structure
```text
├── assets/
│   ├── active_suspension_model.png     # Architectural block diagram export
│   └── active_suspension_response.png  # High-resolution time-series response
├── active_code.m                       # Parameter initialization & workspace verification
├── active.slx                          # Simulink plant and controller model
└── README.md                           # Technical documentation
