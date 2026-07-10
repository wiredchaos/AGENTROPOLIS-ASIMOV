# ASIMOV Cloud Architecture

## Identity

ASIMOV Cloud is the open-source, hardware-neutral cloud robotics control plane for the Agentropolis robotics district.

It separates the intelligence layer from the robot vendor so builders can connect commercial robots through BYOK or open hardware through BYOH without surrendering governance to either.

> Intelligence may be distributed. Authority must remain explicit.

## Core Stack

```text
HERMES / Agent Runtime
        -> ASIMOV Task API
        -> Governance and Approval Layer
        -> Open-RMF Fleet and Task Dispatch
        -> Zenoh Secure Data Fabric
        -> ROS 2 Edge Runtime
        -> Robot, Arm, Hand, Sensor Rig, or Simulator
```

Heavy workloads can branch into cloud compute:

```text
Robot sensors
   -> Zenoh transport
   -> FogROS2 cloud node
   -> perception / planning / simulation / policy inference
   -> validated action envelope
   -> robot-side safety controller
   -> physical execution
```

## Open-Source Components

| Layer | Default component | Responsibility |
|---|---|---|
| Robot middleware | ROS 2 | Drivers, topics, services, actions, local execution |
| Cloud offload | FogROS2 | Launch selected ROS 2 nodes on remote compute |
| Fleet orchestration | Open-RMF | Task dispatch, fleet adapters, traffic, charging |
| Secure transport | Zenoh | Robot-to-cloud and cross-network data fabric |
| Motion planning | MoveIt 2 | Manipulation and trajectory planning |
| Simulation | Gazebo / MuJoCo | Simulation-first testing and digital twins |
| Container platform | Kubernetes | Deployment, scaling, tenancy, recovery |
| Telemetry | OpenTelemetry | Traces, metrics, and execution evidence |
| Dashboards | Grafana | Fleet health, task status, and audit views |
| Logs | Loki | Searchable operational logs |
| Database | PostgreSQL | Registry, permissions, jobs, and metadata |
| Object storage | MinIO | Sensor artifacts, reports, models, and recordings |
| Secrets | Vault-compatible store | Scoped provider and robot credentials |

## Access Models

### BYOK — Bring Your Own Key

Used for commercial providers and external cloud accounts.

The user supplies:

- provider API credentials
- cloud credentials
- robot or fleet identifiers
- billing relationship
- allowed scopes

ASIMOV stores secrets encrypted, issues short-lived access where possible, and never treats possession of a provider credential as permission to perform every supported action.

### BYOH — Bring Your Own Hardware

Used for open or custom ROS 2 hardware.

The user owns:

- robot body
- firmware
- controller computer
- model weights
- telemetry
- maintenance history
- network policy

No commercial robotics API is required.

## Deployment Modes

### Managed Control Plane

```text
ASIMOV-hosted console
   + customer-owned provider keys
   + customer-owned robot hardware
   + customer-selected cloud compute
```

### Sovereign Deployment

```text
Customer Kubernetes
   - ASIMOV API
   - Open-RMF
   - FogROS2
   - Zenoh
   - PostgreSQL
   - MinIO
   - OpenTelemetry
   - Grafana and Loki
```

In sovereign mode, robotics telemetry can remain entirely inside the customer environment.

## Safety Boundary

Cloud intelligence must never become the final physical safety authority.

Required robot-side controls:

- emergency stop
- safe-state behavior on disconnect
- local velocity and force limits
- collision avoidance
- command expiry
- signed command envelopes
- operator-visible autonomy state
- local refusal of invalid or stale commands

## Teleoperation

Teleoperation is a declared execution mode, not a hidden fallback.

Every teleoperation session must record:

- operator identity
- start and stop time
- reason autonomy stopped
- granted camera and sensor access
- commands issued
- objects or zones touched
- session outcome

## Provider Neutrality

Commercial vendors are adapters inside ASIMOV, not owners of the district.

Initial adapter classes:

- `ASIMOV-ADAPTER-1X` — commercial humanoid robotics through BYOK
- `ASIMOV-ADAPTER-ROS2` — generic open ROS 2 hardware through BYOH
- `ASIMOV-ADAPTER-RUKA` — open dexterous hand profile
- `ASIMOV-ADAPTER-ORCA` — open dexterous hand profile
- `ASIMOV-ADAPTER-SIM` — simulator-only embodiment node

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

## Canon Lock

ASIMOV Cloud is the district's open control plane.

FogROS2 provides cloud compute offload. Open-RMF coordinates fleets and tasks. Zenoh carries secure robot traffic. ROS 2 owns the edge runtime. ASIMOV governs identity, permissions, approvals, adapters, and auditability.
