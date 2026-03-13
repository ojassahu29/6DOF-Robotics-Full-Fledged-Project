# 6DOF Robotics Full-Fledged Project

## Overview

This project provides a comprehensive implementation of algorithms and models for a 6 Degrees of Freedom (6DOF) robotic manipulator. It covers essential aspects of robotics including kinematics, dynamics, and control systems, serving as a complete toolkit for robotic simulation and analysis.

## Features

### Kinematics
- **Forward Kinematics**: Compute the position and orientation of the end-effector given joint angles
- **Inverse Kinematics**: Calculate joint angles required to achieve a desired end-effector pose
- **Jacobian Matrix**: Compute velocity relationships between joint and Cartesian spaces

### Dynamics
- **Dynamic Modeling**: Implement equations of motion using Lagrangian mechanics
- **Torque Calculations**: Compute joint torques for given trajectories
- **Mass Matrix and Coriolis Forces**: Handle inertial and centrifugal effects

### Control Systems
- **PID Control**: Basic proportional-integral-derivative controllers
- **Trajectory Planning**: Generate smooth joint-space and Cartesian-space trajectories
- **Motion Control**: Implement position, velocity, and force control algorithms

### Simulation and Visualization
- **Robot Simulation**: Simulate robot motion in a virtual environment
- **Visualization Tools**: Plot joint angles, end-effector paths, and force/torque profiles
- **Interactive GUI**: User interface for parameter tuning and real-time control

## Installation

### Prerequisites
- Python 3.8 or higher
- NumPy
- SciPy
- Matplotlib
- (Optional) ROS for advanced simulation

### Setup
1. Clone the repository:
   ```bash
   git clone https://github.com/ojassahu29/6DOF-Robotics-Full-Fledged-Project.git
   cd 6DOF-Robotics-Full-Fledged-Project
   ```

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Run the main simulation:
   ```bash
   python main.py
   ```

## Usage

### Basic Example
```python
from robot_kinematics import ForwardKinematics
from robot_dynamics import DynamicModel

# Define joint angles
q = [0, 0.5, 0, 0.5, 0, 0]

# Compute forward kinematics
fk = ForwardKinematics()
pose = fk.compute_pose(q)
print("End-effector pose:", pose)

# Compute dynamics
dm = DynamicModel()
torques = dm.compute_torques(q, q_dot, q_ddot)
print("Joint torques:", torques)
```

### Advanced Usage
- Modify robot parameters in `config/robot_params.yaml`
- Use the GUI for interactive control: `python gui.py`
- Run simulations with different controllers: `python simulation.py`

## Project Structure

```
├── kinematics/
│   ├── forward_kinematics.py
│   ├── inverse_kinematics.py
│   └── jacobian.py
├── dynamics/
│   ├── dynamic_model.py
│   └── torque_calculations.py
├── control/
│   ├── pid_controller.py
│   └── trajectory_planner.py
├── simulation/
│   ├── robot_simulator.py
│   └── visualization.py
├── config/
│   └── robot_params.yaml
├── tests/
│   └── test_kinematics.py
├── main.py
├── gui.py
└── requirements.txt
```

## Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/new-feature`)
3. Commit your changes (`git commit -am 'Add new feature'`)
4. Push to the branch (`git push origin feature/new-feature`)
5. Create a Pull Request

## Testing

Run the test suite:
```bash
python -m pytest tests/
```

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- Based on standard robotics textbooks and research papers
- Inspired by open-source robotics projects
- Special thanks to the robotics community for valuable resources

## Contact

For questions or suggestions, please open an issue on GitHub or contact the maintainer.