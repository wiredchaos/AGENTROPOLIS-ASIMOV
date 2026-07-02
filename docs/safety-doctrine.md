# Safety Doctrine

## Prime Rule

Physical agents must remain subordinate to human authority.

Asimov District does not treat robotics safety as a feature. Safety is the foundation.

## Safety Model

Every robot must have:

- a human operator
- an emergency stop method
- a remote shutdown method
- an operating boundary
- task permissions
- speed limits
- proximity rules
- deployment logs
- maintenance records
- inspection status

## Approval Gates

A robot task can only move forward through the following gates:

```text
Concept -> Simulation -> Controlled Test -> Human Review -> Limited Pilot -> Logged Deployment
```

No robot should skip simulation and controlled testing.

## Permission Classes

### Class 0: Display Only

The robot is powered off or used as a static display.

### Class 1: Demonstration Mode

The robot performs scripted movements under close human supervision.

### Class 2: Teleoperated Mode

A human operator directly controls movement and actions.

### Class 3: Assisted Autonomy

The robot can perform limited approved tasks with human supervision.

### Class 4: Restricted Autonomy

The robot performs scoped tasks in a defined environment with logging, geofencing, and human override.

### Class 5: Prohibited Without Advanced Review

Any task involving weapons, restraint, medical decisions, law enforcement, child supervision, unsupervised elder care, or hazardous environments.

## Required Shutdown Controls

Every embodied agent must support:

- local emergency stop
- remote stop
- operator override
- power isolation procedure
- network disconnect procedure
- safe posture or safe idle state

## Risk Review Questions

Before deployment, ask:

1. Could this robot injure a person?
2. Could it damage property?
3. Could it access private data?
4. Could it make a financial transaction?
5. Could it leave its assigned area?
6. Could it continue operating after losing connection?
7. Could a malicious actor take control?
8. Is the operator trained?
9. Is there a rollback plan?
10. Are logs captured?

## Deployment Rule

If the answer to any risk question is unknown, the robot does not deploy.

## Anti-Moloch Protocol

Do not optimize for speed over safety.

Do not ship physical autonomy just because it is impressive.

Do not allow demo pressure to override operator judgment.

Do not hide failures. Failures are district intelligence.

## Final Doctrine

**Robots earn trust through logs, tests, inspections, and restraint.**
