# AGENTROPOLIS ASIMOV DISTRICT

**ASIMOV DISTRICT** is the robotics, embodiment, and physical-agent governance layer of Agentropolis.

This repository defines the open-source district where agents do not stay trapped on screens. They can be simulated, assembled, connected to cloud intelligence, governed, repaired, audited, and deployed into physical workflows with human oversight.

> Build the body. Govern the mind.

## Core Thesis

Physical agents are not just software.

They require:

- hardware and parts sourcing
- build documentation
- robot identity and ownership
- repair and maintenance workflows
- safety testing
- operator permissions
- human-in-the-loop controls
- cloud and edge coordination
- deployment logs
- emergency stops
- insurance and compliance planning
- embodied-agent governance

ASIMOV is where open robotics meets agentic coordination.

## District Purpose

ASIMOV helps builders move from:

```text
AI chat agent
  -> tool-using agent
  -> simulated worker
  -> cloud-connected robot
  -> governed physical agent
```

The goal is not uncontrolled autonomy.

The goal is useful robotics with clear boundaries, auditable actions, local safety authority, and human command.

## District Architecture

```text
AGENTROPOLIS INTELLIGENCE GRID
        -> HERMES / Agent Runtime
        -> ASIMOV Cloud Control Plane
        -> Governance and Approval Layer
        -> Open-RMF Task and Fleet Dispatch
        -> Zenoh Secure Data Fabric
        -> ROS 2 Edge Runtime
        -> Robot, Arm, Hand, Sensor Rig, or Simulator
        -> ASIMOV Audit Ledger
```

Heavy workloads can be offloaded through FogROS2 while final physical safety remains on the robot.

## Access Models

### BYOK — Bring Your Own Key

Used for commercial robotics providers and external cloud accounts.

The user supplies and retains control of:

- provider credentials
- cloud credentials
- robot or fleet identifiers
- provider billing
- permission scopes

Commercial providers are adapters inside ASIMOV. They do not own the district or bypass Agentropolis governance.

Initial commercial adapter:

- `ASIMOV-ADAPTER-1X`

### BYOH — Bring Your Own Hardware

Used for open-source or custom ROS 2 hardware.

The user controls:

- robot body
- firmware
- controller computer
- model weights
- telemetry
- maintenance history
- network access

Initial open adapters:

- `ASIMOV-ADAPTER-ROS2`
- `ASIMOV-ADAPTER-RUKA`
- `ASIMOV-ADAPTER-ORCA`
- `ASIMOV-ADAPTER-SIM`

## ASIMOV Cloud

ASIMOV Cloud is the open-source, hardware-neutral control plane for embodied agents.

| Layer | Default component | Responsibility |
|---|---|---|
| Robot runtime | ROS 2 | Drivers, services, actions, and local execution |
| Cloud offload | FogROS2 | Remote CPU and GPU workloads |
| Fleet orchestration | Open-RMF | Task dispatch, traffic, charging, and fleet adapters |
| Secure transport | Zenoh | Robot-to-cloud data fabric |
| Motion planning | MoveIt 2 | Manipulation and trajectory planning |
| Simulation | Gazebo / MuJoCo | Simulation-first validation and digital twins |
| Container platform | Kubernetes | Deployment, scaling, and recovery |
| Database | PostgreSQL | Registry, permissions, and job metadata |
| Object storage | MinIO | Models, reports, recordings, and sensor artifacts |
| Telemetry | OpenTelemetry | Traces, metrics, and execution evidence |
| Dashboards | Grafana | Fleet health and task monitoring |
| Logs | Loki | Searchable operational history |

Full architecture: [`docs/asimov-cloud-architecture.md`](docs/asimov-cloud-architecture.md)

Machine-readable registry: [`registry/asimov-cloud.yaml`](registry/asimov-cloud.yaml)

## Core Skills

| Skill | Role |
|---|---|
| `ASIMOV-SENSE` | Build a current model of the physical environment |
| `ASIMOV-PLAN` | Convert intent into bounded physical task graphs |
| `ASIMOV-GUARD` | Apply risk classes, permissions, and safety gates |
| `ASIMOV-GRASP` | Select grip, pressure, hand pose, and release behavior |
| `ASIMOV-MOVE` | Control navigation and body positioning |
| `ASIMOV-TELEOP` | Open a declared and auditable human-control session |
| `ASIMOV-AUDIT` | Record intent, approvals, actions, failures, and outcomes |

## Primary Modules

### 1. Robotics Assembly Lab

A build environment for humanoid robots, mobile robots, grippers, sensor rigs, and custom embodied-agent hardware.

Initial focus:

- open-source humanoid kits
- DIY robotics documentation
- bill of materials tracking
- assembly checklists
- maintenance logs
- repair history

### 2. Agent Body Registry

A registry for physical robot bodies inside Agentropolis.

Each body should have:

- body ID
- model type
- parts list
- firmware version
- operator owner
- active permissions
- safety constraints
- inspection status
- deployment history
- edge runtime status
- shutdown procedure

### 3. Skill Upload Training Rooms

A controlled training layer for embodied tasks.

Examples:

- pick and place
- navigation
- workspace inspection
- inventory scan
- delivery route
- cleaning routine
- warehouse assist
- elder-support workflow
- classroom demonstration mode

No skill should graduate to live physical use without simulation, checklist review, and human approval.

### 4. Safety Arena

A controlled testing zone for embodied agents before deployment.

Required checks:

- emergency stop works
- remote shutdown works
- safe state activates on disconnect
- geofence works
- speed and force limits work
- collision detection works
- human proximity rules work
- command expiry works
- logging works
- permission scope is correct

### 5. Repair Bay

A maintenance and parts-management system for robots.

Tracks:

- failed parts
- replacement parts
- wear cycles
- service intervals
- battery health
- actuator health
- sensor calibration
- firmware rollback notes

### 6. Robotics Marketplace

A future district market for parts, services, robot bodies, build kits, repair services, and certified operators.

Possible categories:

- humanoid kits
- servos and actuators
- sensors
- cameras
- batteries
- printed parts
- tools
- repair labor
- operator training
- inspection services

### 7. Governance Console

The layer that keeps embodied agents aligned with Agentropolis rules.

It must answer:

- Who owns this robot?
- Who may operate it?
- What can it do?
- Where can it go?
- What tools can it access?
- Which actions require approval?
- Which cloud or provider credentials are active?
- How do we stop it?
- What happened during the last run?

## Execution Chain

```text
User request
   -> HERMES interprets intent
   -> ASIMOV-PLAN creates task graph
   -> ASIMOV-GUARD assigns risk class
   -> human approval when required
   -> ASIMOV-SENSE validates environment
   -> provider adapter opens scoped session
   -> Open-RMF dispatches task
   -> robot-side controller validates command
   -> physical execution
   -> ASIMOV-AUDIT records evidence
```

## Risk Classes

| Class | Meaning | Rule |
|---|---|---|
| A0 | Observe | Automatic within declared sensor scope |
| A1 | Low-risk action | Automatic within approved policy |
| A2 | Controlled action | Environment validation required |
| A3 | Sensitive action | Explicit human approval required |
| A4 | Prohibited action | Blocked |

## Teleoperation Doctrine

Teleoperation is a declared execution mode, never a hidden fallback.

Every teleoperation session must record:

- operator identity
- start and stop time
- why autonomy stopped
- granted camera and sensor access
- commands issued
- objects or zones touched
- session outcome

## Agentropolis Integration

ASIMOV connects to:

- **HERMES CITY** as the orchestration city
- **AGENTROPOLIS** as the master city-scale architecture
- **AGENTROPOLIS AGENT MCP** for agent tooling and interfaces
- **MCP RANGER** for permission and risk governance
- **Agent wallets** for controlled commerce and machine payments
- **Simulation districts** before physical-world deployment
- **Audit and memory layers** for traceability and learning

## Operating Principles

1. Human authority stays above machine autonomy.
2. Every physical action needs scope, logging, and rollback planning.
3. Robots start in simulation before touching real environments.
4. Permissions must be explicit, temporary, and revocable.
5. Safety checks are infrastructure, not vibes.
6. Embodied agents need inspections like vehicles, not prompts like chatbots.
7. Open robotics should be accessible, but never lawless.
8. Cloud intelligence must not replace robot-side safety authority.
9. Provider credentials never equal unrestricted authorization.
10. Every live action must be attributable, interruptible, observable, and auditable.

## Roadmap

### Phase 0: Doctrine Lock

- define district mission
- create safety doctrine
- create body registry schema
- create deployment checklist
- create README and build map

### Phase 1: Open Robotics Research Layer

- track open-source humanoid projects
- compare DIY kit options
- build bill of materials templates
- create parts sourcing database
- create operator training outline

### Phase 2: Simulation First

- add simulated robot task flows
- define safe task library
- connect virtual district to Agentropolis city map
- build approval gates for skill deployment
- add `ASIMOV-ADAPTER-SIM`

### Phase 3: ASIMOV Cloud MVP

- deploy ROS 2 edge reference node
- connect Zenoh secure transport
- add FogROS2 cloud offload profile
- register Open-RMF task dispatcher
- launch PostgreSQL registry and audit store
- add Grafana fleet dashboard

### Phase 4: Physical Pilot

- register first robot body
- assemble first kit or prototype
- run safety arena tests
- deploy only non-critical low-risk tasks
- document every failure and improvement

### Phase 5: District Marketplace

- parts marketplace
- repair vendors
- operator certification
- builder profiles
- robotics education portal

## Repository Map

- [`docs/asimov-district-blueprint.md`](docs/asimov-district-blueprint.md)
- [`docs/asimov-cloud-architecture.md`](docs/asimov-cloud-architecture.md)
- [`docs/safety-doctrine.md`](docs/safety-doctrine.md)
- [`registry/asimov-cloud.yaml`](registry/asimov-cloud.yaml)
- [`schemas/body-registry.schema.json`](schemas/body-registry.schema.json)
- [`checklists/deployment-checklist.md`](checklists/deployment-checklist.md)
- [`checklists/build-checklist.md`](checklists/build-checklist.md)

## Canon Lock

ASIMOV is the district. ASIMOV Cloud is its open control plane. Commercial robotics companies are optional adapters. Open ROS 2 hardware enters through BYOH. External providers and cloud accounts enter through BYOK.

**ASIMOV District is where agents get bodies, but only under governance.**
