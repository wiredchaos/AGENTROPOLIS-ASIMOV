# Deployment Checklist

Use this before any robot body moves from lab mode into a real environment.

## Identity

- [ ] Robot has a registered body ID
- [ ] Robot model is documented
- [ ] Operator is documented
- [ ] Owner is documented
- [ ] Active firmware version is documented
- [ ] Parts manifest is current

## Safety Controls

- [ ] Local emergency stop tested
- [ ] Remote shutdown tested
- [ ] Operator override tested
- [ ] Safe idle posture tested
- [ ] Power isolation procedure documented
- [ ] Network disconnect procedure documented
- [ ] Battery safety reviewed

## Environment

- [ ] Deployment location documented
- [ ] Geofence defined
- [ ] Floor hazards checked
- [ ] People proximity risk reviewed
- [ ] Pets and children risk reviewed
- [ ] Weather risk reviewed if outdoors
- [ ] Network reliability checked

## Task Scope

- [ ] Task is listed as allowed
- [ ] Task has been simulated
- [ ] Task has passed controlled test
- [ ] Task does not involve prohibited activity
- [ ] Robot speed limits are set
- [ ] Payload or lifting limits are set
- [ ] Human approval requirement is configured

## Data and Privacy

- [ ] Cameras are disclosed if active
- [ ] Microphones are disclosed if active
- [ ] Data retention is documented
- [ ] Private areas are excluded
- [ ] Logs are enabled

## Agent and Wallet Permissions

- [ ] Agent identity is known
- [ ] Tool permissions are scoped
- [ ] Network permissions are scoped
- [ ] Wallet access is disabled unless explicitly approved
- [ ] Spending limits are set if wallet access exists
- [ ] Transaction approvals require human confirmation

## Human Oversight

- [ ] Primary operator is present or reachable
- [ ] Backup operator is assigned
- [ ] Shutdown authority is clear
- [ ] Deployment window is time-limited
- [ ] Failure escalation path is known

## Final Gate

- [ ] Operator signs off
- [ ] Safety status is current
- [ ] Deployment log created
- [ ] Rollback plan exists
- [ ] Robot is cleared only for this specific task and environment

## Deployment Rule

If any required item is unchecked, deployment is blocked.
