# Agent Nightfall Field Operations — CMD Secure

**Company-specific version for Command Corporation / CMD Secure.**

This is the internal Agent Nightfall Field Operations kit for temporary on-site programming of cameras and IP systems. It includes CompanyCam for completion documentation and camera image uploads, plus a dedicated agent that tracks the Windows 10 field computer itself.

A Field Supervisor is the only interface the technician uses. Specialists handle devices, VMS, credentials, documentation, and the host computer under strict approval.

---

## Agents

Create these from the prompts in `agents/`:
- **Field Supervisor** — orchestrator and single human interface
- **Device Programmer** — cameras (Axis, Milesight, Uniview + others; ONVIF-first)
- **VMS Programmer** — DW Spectrum and similar
- **Credentials Manager** — generate → store in 1Password → then apply
- **Job Reporter** — CompanyCam project, image uploads, client report design and delivery
- **Kit / Computer Manager** — owns the Windows 10 host (isolation, firewall, residual cleanup)

## Quick Start

1. Follow `SPIN-UP.md`.
2. Configure the Windows computer per `docs/windows-kit-setup.md`.
3. Run Phase 0 isolation checks before any real job.
4. On site, talk only to the Field Supervisor.

## Core Principles

- Cellular sole default route; local interface locked to the device subnet.
- Plan → Approve → Execute → Verify for every high-stakes write.
- Generate credential → store immediately → then apply. Nothing left on the kit.
- CompanyCam reports require explicit approval before client delivery.

See `docs/` for isolation, Windows setup, and CompanyCam workflow details.

---

*Internal use for Command Corporation / CMD Secure.*