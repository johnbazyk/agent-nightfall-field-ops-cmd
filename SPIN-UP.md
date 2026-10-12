# Spin-Up Guide — Agent Nightfall Field Operations (CMD Secure)

This repository contains everything needed to stand up the full kit on a dedicated multi-agent account and configure the Windows 10 field computer.

## Steps

1. Create or open the dedicated multi-agent account (Grok Bot / SuperGrok or equivalent).
2. Create the following agents using the exact system prompts from the files in `agents/`:
   - Field Supervisor (`agents/field-supervisor.md`)
   - Device Programmer (`agents/device-programmer.md`)
   - VMS Programmer (`agents/vms-programmer.md`)
   - Credentials Manager (`agents/credentials-manager.md`)
   - Job Reporter (`agents/job-reporter.md`) — CompanyCam focused
   - Kit / Computer Manager (`agents/kit-manager.md`) — owns the Windows 10 host
3. Connect the account to CompanyCam, 1Password (or equivalent), and Workiz as required. Use least privilege.
4. Configure the Windows 10 field computer according to `docs/windows-kit-setup.md`.
5. Review and fill in the company standards in `examples/cmd-secure-standards.example.yaml`.
6. Run the Phase 0 isolation checks in `docs/isolation-standard.md` and the host checklist in `docs/windows-kit-setup.md` before any real job.
7. On site, the technician talks only to the Field Supervisor.

The Kit / Computer Manager tracks and verifies the host machine. The Job Reporter handles CompanyCam image uploads, report template design, and client report delivery after explicit approval.

All high-stakes actions follow Plan → Approve → Execute → Verify.

## Failure Modes (Supervisor handles)
- Isolation fails (wrong default route or local interface reachable beyond subnet): stop all work, escalate, do not proceed.
- Camera auth failure or lockout: escalate; do not retry indefinitely.
- CompanyCam upload or report generation fails: escalate before any client delivery.
- Residual secrets found: clean before next job and escalate.