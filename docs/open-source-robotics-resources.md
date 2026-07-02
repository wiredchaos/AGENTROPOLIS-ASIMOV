# Open-Source Robotics Resources

This file tracks open-source resources for the Asimov District Robotics MCP and API.

These resources should be treated as research targets, adapter targets, and integration candidates. Verify license, activity, security, and hardware compatibility before production use.

## Core Robotics Middleware

### ROS 2

- Category: robotics middleware
- Use: robot communication, nodes, topics, services, actions, transforms
- Integration target: primary robotics adapter
- Notes: default open robotics ecosystem for Asimov District

### micro-ROS

- Category: embedded robotics middleware
- Use: connect microcontrollers into ROS 2 systems
- Integration target: microcontroller bridge

### Open-RMF

- Category: fleet management
- Use: robot fleet coordination, facility integration, task dispatch
- Integration target: multi-robot district operations

## Simulation Engines

### Gazebo / Ignition

- Category: robot simulation
- Use: physics simulation, robot testing, sensor simulation
- Integration target: simulation-first safety gate

### Webots

- Category: robot simulation
- Use: education, prototyping, robot behavior simulation
- Integration target: accessible district simulator

### MuJoCo

- Category: physics simulation
- Use: control research, locomotion, manipulation
- Integration target: humanoid control experiments

### PyBullet

- Category: physics simulation
- Use: robotics experiments, manipulation, reinforcement learning tests
- Integration target: lightweight simulation tasks

## Motion Planning and Navigation

### MoveIt 2

- Category: motion planning
- Use: robotic arms, manipulation planning, collision-aware motion
- Integration target: manipulation skill layer

### Nav2

- Category: robot navigation
- Use: autonomous navigation, mapping, path planning
- Integration target: mobile robot movement gate

### SLAM Toolbox

- Category: mapping and localization
- Use: create maps and localize robots
- Integration target: district map tooling

### Cartographer

- Category: SLAM
- Use: mapping and localization
- Integration target: alternate SLAM adapter

## Robot Learning and Control

### LeRobot

- Category: robot learning
- Use: learning policies, datasets, robot skill research
- Integration target: skill training rooms

### Gymnasium Robotics

- Category: robotics reinforcement learning environments
- Use: simulated control training and evaluation
- Integration target: experiment lane only

### Drake

- Category: robotics toolbox
- Use: modeling, planning, control, optimization
- Integration target: advanced robotics engineering lane

## Humanoid and Embodied AI Research Targets

### Open-source humanoid projects

- Category: humanoid robot builds
- Use: reference designs, BOMs, mechanical and electrical design
- Integration target: body registry and build lab
- Rule: do not assume safety or production readiness. Verify everything.

### DIY humanoid kits

- Category: build kits
- Use: accessible robot bodies for builders
- Integration target: assembly lab and education portal
- Rule: kit does not equal deployment clearance.

## Embedded and Hardware Control

### Arduino

- Category: microcontroller platform
- Use: sensors, actuators, robotics prototypes
- Integration target: low-level hardware bridge

### PlatformIO

- Category: embedded development
- Use: cross-platform firmware workflows
- Integration target: firmware build lane

### Raspberry Pi

- Category: edge compute
- Use: robot brains, sensors, camera pipelines
- Integration target: edge robotics node

### ESP32

- Category: microcontroller / wireless edge device
- Use: sensors, motor control, telemetry
- Integration target: lightweight robot modules

## Computer Vision

### OpenCV

- Category: computer vision
- Use: perception, object detection, calibration, tracking
- Integration target: perception adapter

### AprilTag

- Category: fiducial marker detection
- Use: localization, calibration, object tracking
- Integration target: safety arena and lab tracking

## Data, Telemetry, and Observability

### Foxglove

- Category: robotics visualization and observability
- Use: inspect ROS data, telemetry, logs, sensor streams
- Integration target: district observability dashboard

### MCAP

- Category: robotics log format
- Use: record and replay robotics data
- Integration target: audit logs and incident review

## API and Protocol Layer

### Model Context Protocol

- Category: agent tool protocol
- Use: expose robotics tools to agents safely
- Integration target: Robotics MCP server

### OpenAPI

- Category: API specification
- Use: define REST API contracts
- Integration target: Robotics API

### JSON Schema

- Category: schema validation
- Use: validate robot registry and events
- Integration target: body registry and deployment validation

### MQTT

- Category: lightweight messaging protocol
- Use: telemetry, edge messages, IoT-style robot communication
- Integration target: telemetry adapter

### WebSocket

- Category: real-time API protocol
- Use: telemetry streaming, status events
- Integration target: live dashboard and operator console

## Safety and Governance Resources

### Safety checklist templates

- Category: governance
- Use: preflight, build, maintenance, deployment reviews
- Integration target: Asimov District safety gates

### Policy engines

- Category: access control
- Use: decide whether a robot action is allowed
- Integration target: MCP policy gate
- Candidates: Open Policy Agent style rules, local JSON rules, signed approvals

## License Policy

Preferred licenses:

- MIT
- Apache-2.0
- BSD-2-Clause
- BSD-3-Clause
- MPL-2.0 where compatible

Use caution with:

- GPL or AGPL dependencies in commercial-facing deployments
- unclear hardware licenses
- abandoned repositories
- unreviewed firmware blobs

## Integration Rule

A resource does not become part of Asimov District until it has:

- license checked
- security reviewed
- adapter path defined
- failure mode documented
- safety impact reviewed
- operator approval requirements defined
