# Robotics MCP

The Robotics MCP is the open-source control surface for Asimov District.

It gives agents a safe way to discover robot capabilities, request actions, inspect status, read telemetry, and route commands through human-approved governance gates.

## Purpose

Robotics MCP turns physical robot access into structured tools instead of loose prompts.

It is designed for:

- open-source humanoid projects
- DIY robot kits
- ROS 2 robots
- simulation-first workflows
- parts and bill of materials tracking
- safety gates
- maintenance logs
- operator approval
- auditable embodied agent actions

## Core Rule

Agents do not directly control robots by default.

They request actions through MCP tools. The governance layer decides whether the action is allowed, blocked, or requires human approval.

```text
Agent -> MCP Tool -> Policy Gate -> Robot Adapter -> Robot or Simulator -> Audit Log
```

## Initial MCP Tool Groups

### Registry Tools

- `robot.list`
- `robot.get`
- `robot.register`
- `robot.update_status`

### Capability Tools

- `capability.list`
- `capability.get`
- `capability.request`

### Safety Tools

- `safety.preflight`
- `safety.estop`
- `safety.remote_shutdown`
- `safety.audit_status`

### Simulation Tools

- `sim.run_task`
- `sim.validate_task`
- `sim.report`

### Deployment Tools

- `deployment.request`
- `deployment.approve`
- `deployment.deny`
- `deployment.log_event`

### Maintenance Tools

- `maintenance.log`
- `maintenance.schedule`
- `maintenance.parts_needed`

## Adapter Targets

The MCP should support adapters for:

- ROS 2
- Gazebo / Ignition simulation
- Webots simulation
- MuJoCo simulation
- Open-RMF fleet workflows
- Arduino / microcontroller bridges
- Python robotics scripts
- vendor-neutral REST APIs

## Open Source First

This MCP should prefer open standards, open protocols, and open-source robotics stacks wherever possible.

Commercial robotics APIs can be added later only as optional adapters.
