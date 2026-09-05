# Active Suspension Control System (PID & System Dynamics)

## 1. System Overview
* Repository implements a closed-loop Proportional-Integral-Derivative (PID) control architecture coupled with a vehicle dynamics plant model.
* Simulation environment: MATLAB/Simulink.
* Primary objective: Suppress transient vibration profiles and optimize mechanical system settling time.

## 2. System Architecture
* Plant model utilizes modular subsystems to manage feedback loops and signal propagation.
* Model visualization asset:

![Simulink Block Diagram](outputs/active_simulink.png)

## 3. Execution & Verification Workflow
* Pre-execution workspace validation executed via initialization script (`active_code.m`).
* Data logging configured using Simulink `Dataset` logging format for programmatic post-processing.
* Transient response waveform exported at 300 DPI resolution:

![System Response Scope](outputs/ScopeactiveToFigure.png)

## 4. Repository Directory Structure

├── assets/
│   ├── active_suspension_model.png     # Architectural block diagram export
│   └── active_suspension_response.png  # High-resolution time-series response
├── active_code.m                       # Parameter initialization & workspace verification
├── active.slx                          # Simulink plant and controller model
└── README.md                           # Technical documentation

# quarter-car suspension & pid control

simulink & matlab setup for a quarter-car suspension model with a basic active pid controller. built to test ride comfort and suspension response against road bumps.

## what's in here
- `suspension.m`: self-contained script that documents the governing equations, sets up vehicle constants, runs a natural frequency/damping check, and plots an analytical response preview.
- ![System Response Scope](outputs/ScopesuspensionToFigure.png)
- `suspension_model.slx`: block diagram handling the multi-degree-of-freedom physics loop and control feedback.
![Simulink Block Diagram](outputs/suspension_simulink.png)

## governing equations
the model is built on standard 2-dof quarter-car equations of motion:
- **sprung mass (chassis):** $m_s \ddot{x}_s = -k_s(x_s - x_u) - c(\dot{x}_s - \dot{x}_u) + u$
- **unsprung mass (wheel):** $m_{us} \ddot{x}_u = k_s(x_s - x_u) + c(\dot{x}_s - \dot{x}_u) - k_t(x_u - x_r) - u$

