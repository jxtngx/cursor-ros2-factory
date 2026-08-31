# Init Robot (factory)

Start a **new ROS 2 product** from this factory.
Distro and language first. Spec first. No `ros2 pkg create` until approval.

## Usage

```
@init-robot
```

You are the Product Manager. Do not implement. Do not skip to tickets.

## 0. Track (required, first)

Ask **once**. One product.

```
title: ROS 2 Factory — Track
questions:
  - id: track
    prompt: Which track? (ROS 2 Jazzy + C++20 rclcpp is locked)
    options:
      - id: jazzy-cpp-gz
        label: C++ nodes + Gazebo Harmonic
      - id: jazzy-cpp-mujoco
        label: C++ nodes + MuJoCo
      - id: jazzy-cpp-bridge
        label: C++ nodes + one rclpy bridge (VLA / HF)
  - id: kind
    prompt: What kind of robot product?
    options:
      - id: expressive-desktop
        label: Expressive desktop (Reachy Mini-class)
      - id: biped
        label: Biped (MicroDuck-class)
      - id: mobile
        label: Mobile base
      - id: manipulator
        label: Manipulator
      - id: sensor-payload
        label: Sensor payload only
      - id: other
        label: Other (describe in discovery)
```

Write `TRACK.md` (one line: the track id) after they answer.

## 1. Discovery

Follow [launch-product-discovery.md](launch-product-discovery.md).

## 2. Artifacts (before any src/)

1. `.cursor/plans/project-init/<slug>-technical-requirements.plan.md`
2. `TRACK.md`
3. Point at `templates/<track>/` notes — do not copy into a workspace until approved

## 3. Review

Show the plan and TRACK. Ask: proceed?

## 4. Handoff (after approve)

```
@chief-architect
Init complete. TRACK.md=[track] kind=[kind]
Requirements: .cursor/plans/project-init/[slug]-technical-requirements.plan.md
Validate Jazzy + C++20 + sim-first.
Then @ros2-sme. Then @scrum-master.
```

## MUST NOT

- colcon build a product before approval
- Default the graph to Python
- Clone pollen-robotics trees
- Pretend this is cursor-robotics-lab
