# Agent Nightfall Field Operations — CMD Secure

**Company-specific version for Command Corporation / CMD Secure.**

Temporary on-site multi-agent programming kit for cameras, NVRs/VMS, and IP systems. Includes CompanyCam integration for client-facing completion reports and camera image delivery.

A **Field Supervisor** is the only interface the tech talks to. Specialists handle discovery, configuration, credentials, VMS setup, and as-built documentation (via CompanyCam) under strict human approval.

---

## CompanyCam Integration (Key for CMD Secure)

- The Job Reporter agent designs and maintains the client report template in CompanyCam.
- All camera images and job photos are uploaded to the matching CompanyCam project.
- Completion report is generated in CompanyCam and shared with the client.
- Agents can assist with CompanyCam cleanup (project organization, tagging, archive of completed jobs).

See `agents/job-reporter.md` and `docs/companycam-workflow.md` for details.

## Core Principles

- Cellular-only internet. Local interface locked to the target device subnet.
- Plan → Approve → Execute → Verify.
- Credentials generated, stored in 1Password (or company password manager), then applied.
- ONVIF-first.
- Explicit scope locks.

## Quick Start

1. Create the agents using the prompts in `agents/`.
2. Configure CompanyCam API access (token stored securely).
3. Run Phase 0 isolation tests.
4. On site, talk only to the Field Supervisor.

## Structure

```
agents/          Full system prompts (including CompanyCam-aware Job Reporter)
docs/            Isolation standard, Phase 0, CompanyCam workflow
examples/        CMD Secure company standards and sample job context
```

Private company version. Do not share publicly.
