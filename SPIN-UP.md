# Spin-Up Guide — Agent Nightfall Field Operations (CMD Secure)

This repository contains everything needed to stand up the full kit on a dedicated multi-agent account.

## Steps

1. Create or open the dedicated multi-agent account (Grok Bot / SuperGrok or equivalent).
2. Create five agents using the exact prompts in the `agents/` folder:
   - Field Supervisor (`agents/field-supervisor.md`)
   - Device Programmer (`agents/device-programmer.md`)
   - VMS Programmer (`agents/vms-programmer.md`)
   - Credentials Manager (`agents/credentials-manager.md`)
   - Job Reporter (`agents/job-reporter.md`) — includes CompanyCam responsibilities
3. Connect the account to CompanyCam, the password manager, and any ticketing system as required.
4. Review and fill in the company standards in `examples/`.
5. Run the Phase 0 isolation checks in `docs/isolation-standard.md` before any real job.
6. On site, the technician talks only to the Field Supervisor.

The Job Reporter is responsible for CompanyCam project setup, camera image uploads, report template design, and client report delivery after approval.

All high-stakes actions follow Plan → Approve → Execute → Verify.