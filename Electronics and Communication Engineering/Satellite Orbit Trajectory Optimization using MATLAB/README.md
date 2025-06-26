# Satellite Orbit Trajectory Optimization using MATLAB

## Project Overview
This project demonstrates the application of mathematical optimization techniques to model and simulate satellite orbital trajectories using MATLAB. The work focuses on determining optimal paths for satellites and launch vehicles by solving complex differential equations that govern celestial mechanics.

## Key Features
- **Trajectory Optimization**: Implements direct methods (single/multiple shooting) to solve orbital mechanics problems
- **MATLAB Implementation**: Uses ODE solvers (ode45) with precision controls (RelTol, AbsTol)
- **3D Visualization**: Generates interactive plots of satellite orbits around Earth
- **Physical Modeling**: Accounts for gravitational forces, atmospheric drag, and mass consumption
- **Launch Vehicle Analysis**: Includes propulsion system considerations for orbital insertion

## Methodology
### Core Techniques
1. **Differential Equation Solving**:
   ```matlab
   options = odeset('RelTol',1e-8,'AbsTol',1e-10);
   [t,y] = ode45(@orbit_equations, tspan, y0, options);
   ```

2. **Optimization Approaches**:
   - Single Shooting Method
   - Multiple Shooting Method
   - Collocation Method

3. **Physical Parameters**:
   - Aerodynamic drag: 
     ```
     D = ½ρ(r)SC_DV²
     ```
   - Orbital velocity calculations
   - Mass consumption modeling

## MATLAB Implementation
### Key Functions
| Function | Purpose | Example Usage |
|----------|---------|---------------|
| `ode45` | Solve orbital differential equations | `[t,y] = ode45(@orbit_eqn, [0 100], [x0;y0;z0])` |
| `linspace` | Generate time vectors | `t = linspace(0, orbital_period, 1000)` |
| `mesh` | 3D surface plotting | `mesh(X,Y,Z)` |
| `rotate3d` | Interactive 3D view | `rotate3d on` |

### Visualization Code Snippet
```matlab
figure;
hold all;
plot3(y(:,1), y(:,2), y(:,3), 'LineWidth', 2); % Orbit path
grid on;
xlabel('X (km)'); ylabel('Y (km)'); zlabel('Z (km)');
title('Satellite Orbital Trajectory');
rotate3d on;
```

## Results
The simulation successfully generates:
1. Time-domain plots of inertial position/velocity
2. Mass consumption profiles during launch
3. 3D orbital trajectories showing:
   - Perigee/apogee points
   - Orbital transfers
   - Multiple shooting segments

## Applications
- **Space Mission Planning**: Optimize fuel consumption for satellite deployments
- **Launch Vehicle Design**: Improve payload capacity through trajectory optimization
- **Orbital Mechanics Education**: Visualize complex celestial dynamics
- **Satellite Constellation Design**: Plan optimal orbital configurations

## Future Enhancements
1. **High-Fidelity Modeling**:
   - Incorporate J2 perturbation effects
   - Add lunar/solar gravitational influences
2. **GUI Development**:
   - Interactive parameter tuning interface
   - Real-time trajectory updates
3. **Machine Learning Integration**:
   - Neural networks for rapid trajectory prediction
   - Reinforcement learning for adaptive control

## Acknowledgments
- **Dr. Satyendra Singh Chauhan** (Faculty Guide, Amrita Vishwa Vidyapeetham)
- **Amrita School of Engineering, Chennai** for computational resources
- **MATLAB Optimization Toolbox** for advanced solvers
