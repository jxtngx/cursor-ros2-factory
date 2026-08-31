# Cursor ROS 2 Factory

A **factory**, not a lab.

Boilerplate for a new **ROS 2 Jazzy** product. Cursor's team implements from a spec
you write in the first session.

If you want to *learn* ROS 2 by typing every node, use
[cursor-robotics-lab](https://github.com/jxtngx/cursor-robotics-lab).

This factory is tightly coupled to **ROS 2 Jazzy**, **C++20**, and **rclcpp**.
Sim-first: Gazebo Harmonic or a MuJoCo bridge before a physical robot.

Commanded by [cursor-factory-command](https://github.com/jxtngx/cursor-factory-command)
for campaigns (example: tabletop swarm).

---

## First command

```
@init-robot
```

1. Locks **distro** (Jazzy) and **language** (C++20 `rclcpp`; optional `rclpy` bridge if the spec needs Python for VLA/HF)
2. Asks **sim** (Gazebo Harmonic, MuJoCo bridge, or sim-later with an ADR)
3. Asks **kind** (mobile, manipulator, expressive-desktop, biped, sensor-payload, other)
4. Walks requirements discovery
5. Writes `.cursor/plans/project-init/<name>-technical-requirements.plan.md`
6. Writes `TRACK.md`
7. Hands off to `@chief-architect` → `@ros2-sme` → `@scrum-master` → tickets

Do not ask an engineer to `ros2 pkg create` before the spec exists.

## Opinionated stack (not optional)

| Layer | Choice |
| --- | --- |
| Distro | ROS 2 Jazzy |
| Language | C++20, `rclcpp`, `rclcpp_lifecycle` |
| Build | ament_cmake, colcon |
| Python | `rclpy` only as a named bridge package, never the default node language |
| Sim | Gazebo Harmonic and/or MuJoCo; hardware is stretch |
| Time | tf2, `sensor_msgs`, `geometry_msgs` |
| Tests | GTest + launch_testing |
| Style | clang-format, official ROS 2 docs over blogs |

## Team

| Agent | Job |
| --- | --- |
| Product Manager | `@init-robot` / `@launch-product-discovery` |
| Chief Architect | Package graph, lifecycle, sim vs hw |
| ROS 2 SME | Official Jazzy APIs, tf, DDS |
| Scrum Master | Sprint + tickets |
| Robotics Engineer | Nodes, launch, urdf/xacro |
| Platform Engineer | colcon, CI, rosdep, docker |
| Test Developer | GTest, launch_testing |

## Tracks (`TRACK.md`)

- `jazzy-cpp-gz` — C++ nodes, Gazebo Harmonic
- `jazzy-cpp-mujoco` — C++ nodes, MuJoCo
- `jazzy-cpp-bridge` — C++ plus one `rclpy` VLA/HF bridge
