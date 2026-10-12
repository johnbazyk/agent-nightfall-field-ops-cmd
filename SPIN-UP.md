# Spin-Up Guide — Agent Nightfall Field Operations (CMD Secure)

This repository contains everything needed to stand up the full kit on a dedicated multi-agent account.

## Agents to Create
Create these agents using the exact system prompts in the `agents/` folder:

1. **Field Supervisor** (`agents/field-supervisor.md`) — single human interface and orchestrator
2. **Device Programmer** (`agents/device-programmer.md`) — cameras and IP devices (ONVIF-first, Axis / Milesight / Uniview focus)
3. **VMS Programmer** (`agents/vms-programmer.md`) — DW Spectrum or company VMS
4. **Credentials Manager** (`agents/credentials-manager.md`) — generate, store in 1Password, then apply
5. **Job Reporter** (`agents/job-reporter.md`) — CompanyCam images, report template, and client delivery
6. **Kit / Computer Manager** (`agents/kit-manager.md`) — owns the Windows 10 field computer (isolation, firewall, residual cleanup)

(Note: `host-computer.md` is retained for reference but the active agent is Kit / Computer Manager.)

## Steps

1. Open the dedicated multi-agent account (Grok Bot / SuperGrok).
2. Create the six agents above by pasting the full system prompts from their files.
3. Connect the account to CompanyCam, 1Password (or company password manager), and Workiz (or ticketing system) with least privilege.
4. Review and fill in company standards in `examples/cmd-secure-standards.example.yaml`.
5. Configure the Windows 10 field computer per `docs/windows-kit-setup.md`.
6. Run Phase 0 isolation checks in `docs/isolation-standard.md` before any real job.
7. On site, the technician talks only to the Field Supervisor.

## Failure Modes & Escalation (Field Supervisor)
- Isolation fails or local interface gains a default route → stop all work, report to tech, do not proceed.
- Device unreachable or auth fails after credential application → return to Device Programmer for dry-run recheck; escalate if persistent.
- CompanyCam upload or report generation fails → Job Reporter reports details; do not deliver incomplete report.
- Residual secrets found on kit → Kit Manager flags immediately; clean before next job.
- Any scope violation or unexpected device → halt and confirm with technician.

All high-stakes actions follow Plan → Approve → Execute → Verify. Never leave passwords or client data on the kit.
