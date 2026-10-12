# Isolation Standard

Agent Nightfall Field Operations requires a dual-homed host:

- **Cellular interface**: sole default route for all internet traffic.
- **Local Ethernet interface**: connected only to the isolated camera / device network or VLAN.
- Host firewall rules that allow the local interface to reach only the expected device subnet and ports.
- No bridging, no proxying of client network traffic, and no residual routes after the job.

## Phase 0 Checks (must pass before any programming)

1. Confirm default route is the cellular interface.
2. Confirm local interface has no default route.
3. Confirm firewall limits local traffic to the target subnet.
4. Successful discovery of a known test device on the local interface.
5. Failed attempt to reach an address outside the target subnet from the local interface.
6. No residual credentials or configuration left from previous jobs.

Document the results before proceeding.