---
name: launch-product-discovery
description: Launch Product Discovery
disable-model-invocation: true
---

# Launch Product Discovery

Requirements interview after TRACK is locked. Spec only.

## MUST cover

- Job the robot does (one sentence)
- Sim vs hardware milestones
- Topics / tf frames that must exist
- Sensors (camera, IMU, mics, depth)
- Control rate (e.g. 50 Hz policy sidecar)
- Safety (estop, velocity limits)
- What would falsify the spec
- Interfaces to VLA / swarm agent / Zephyr MCU (if any)

Write `.cursor/plans/project-init/<slug>-technical-requirements.plan.md`
from `../templates/technical-requirements-template.md`.

## MUST NOT

- Implement nodes
- Invent undocumented motors as if they were Pollen's SKU
