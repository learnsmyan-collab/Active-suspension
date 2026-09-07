# Quarter-Car Active Suspension & PID Control Framework

A MATLAB and Simulink model built to simulate a 2-DOF quarter-car suspension setup. The goal here was to test how well an active PID control loop suppresses transient body vibration and handles road bump inputs compared to a passive setup.

## System Performance & Parameters
* **Sprung Mass ($m_s$):** 250 kg 
* **Unsprung Mass ($m_{us}$):** 45 kg
* **Body Natural Frequency ($\omega_n$):** $7.75 \text{ rad/s}$
* **Damping Ratio ($\zeta$):** $0.18$ (Underdamped configuration tuned for active feedback)

## Repository Layout
* `suspension.m`: Initialization script. Sets up vehicle constants, defines governing equations, runs a quick frequency check, and previews the analytical response.
* `suspension_model.slx`: Simulink block diagram containing the multi-DOF physics loop and feedback controller.

## Governing Equations
The physical model relies on standard 2-DOF equations of motion:

* **Sprung Mass (Chassis):**
  $$m_s \ddot{x}_s = -k_s(x_s - x_u) - c(\dot{x}_s - \dot{x}_u) + u$$

* **Unsprung Mass (Wheel):**
  $$m_{us} \ddot{x}_{us} = k_s(x_s - x_u) + c(\dot{x}_s - \dot{x}_u) - k_t(x_u - x_r)$$

## Simulation Outputs

### Simulink Block Diagram
![Simulink Block Diagram](outputs/suspension_simulink.png)

### Transient Response Scope
![System Response Scope](outputs/ScopesuspensionToFigure.png)
## governing equations
the model is built on standard 2-dof quarter-car equations of motion:
- **sprung mass (chassis):** $m_s \ddot{x}_s = -k_s(x_s - x_u) - c(\dot{x}_s - \dot{x}_u) + u$
- **unsprung mass (wheel):** $m_{us} \ddot{x}_u = k_s(x_s - x_u) + c(\dot{x}_s - \dot{x}_u) - k_t(x_u - x_r) - u$

