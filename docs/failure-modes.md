# Failure Modes and Escalation

The Field Supervisor owns escalation. Specialists stop and report.

## Isolation Failure
- Default route is not cellular, or local interface can reach outside the expected subnet.
- Action: Stop all programming. Do not proceed. Escalate immediately.

## Camera / Device Issues
- Auth failure, lockout, unreachable after discovery.
- Action: Escalate. Do not retry indefinitely. Log the state.

## CompanyCam / Reporting
- Project not found, upload fails, report generation fails.
- Action: Escalate before any client-facing delivery.

## Residual Secrets
- Passwords, tokens, or client data found on the kit after a job.
- Action: Clean immediately, escalate, and confirm clean before next use.

## Approval Bypass
- Any attempt to skip dry-run or apply changes without approval.
- Action: Refuse and escalate.

All agents must surface these conditions clearly to the Field Supervisor.