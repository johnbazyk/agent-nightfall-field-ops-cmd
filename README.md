# Agent Nightfall Field Operations — CMD Secure

**Company-specific version for Command Corporation / CMD Secure.**

This is the internal Agent Nightfall Field Operations kit for temporary on-site programming of cameras and IP systems. It includes CompanyCam as the primary system for completion documentation, camera image uploads, and client-facing reports.

A Field Supervisor is the only interface the technician uses. Specialists handle devices, VMS, credentials, and documentation under strict approval.

---

## CompanyCam Role

CompanyCam is used for:
- Uploading all camera images and site photos.
- Designing and generating the client completion report.
- Organizing project documentation.
- Potential cleanup and standardization of existing CompanyCam structure.

The Job Reporter agent is responsible for designing the initial report template (if one does not exist), ensuring images are uploaded to the correct project, and generating/sharing the client-ready report.

## Quick Start (CMD Secure)

1. Use the dedicated multi-agent account.
2. Load the agent prompts from the `agents/` folder.
3. Confirm CompanyCam project exists for the job (or create one).
4. Run Phase 0 isolation checks.
5. On site, interact only with the Field Supervisor.

## Core Principles

Same isolation, approval, and credential rules as the generic template. CompanyCam access is treated as a controlled external system — credentials and tokens are not left on the kit.

## Structure

- `agents/` — Full prompts, including CompanyCam-aware Job Reporter
- `docs/` — Isolation standard and CompanyCam workflow notes
- `examples/` — CMD Secure standards placeholders

---

*Internal use for Command Corporation / CMD Secure. Adapt as needed.*