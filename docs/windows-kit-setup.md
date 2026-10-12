# Windows 10 Field Computer Setup — CMD Secure

**Target:** Intel N100 (or similar) mini PC with dual Ethernet preferred, or Ethernet + USB cellular.

## Goals
- Internet only via cellular (USB modem, travel router, or hotspot).
- Local Ethernet reaches only the camera/IP-system subnet for the job.
- Host firewall enforces the boundary.
- Full-disk encryption.
- No residual client data between jobs.

## Baseline Configuration

1. **Network**
   - Cellular interface: sole default route.
   - Local Ethernet: no default route. Metric higher or route explicitly removed.
   - Disable Wi-Fi unless required for a specific approved task.
   - Prefer static IP on the local interface or DHCP only from the isolated switch/VLAN.

2. **Firewall (Windows Defender Firewall or equivalent)**
   - On the local interface: allow only known camera/VMS IPs and required ports (ONVIF 80/443/554/3702, vendor APIs, DW Spectrum ports).
   - Deny all other inbound and outbound on the local interface.
   - Cellular interface: normal outbound allowed; restrict inbound.

3. **Security**
   - BitLocker (or equivalent) full-disk encryption enabled.
   - Local admin account with strong password stored in 1Password.
   - No persistent client credentials on disk.
   - 1Password CLI or browser extension only; tokens cleared after job.

4. **Tools (minimal)**
   - Browser (Edge or Chrome) for fallback computer-use.
   - Optional: ONVIF Device Manager or vendor tools.
   - PowerShell for routing/firewall verification scripts.
   - CompanyCam desktop or browser access.

5. **Verification scripts (recommended)**
   - Check default route points only to cellular.
   - Confirm local interface has no 0.0.0.0/0 route.
   - List firewall rules on the local profile.
   - Residual scan for common secret patterns.

## Pre-Job Checklist (Kit Manager runs this)
- [ ] Cellular is sole default route
- [ ] Local interface has no default route
- [ ] Firewall rules match expected subnet
- [ ] Disk encryption on
- [ ] No residual client data from previous job
- [ ] Required tools present and updated
- [ ] 1Password and CompanyCam access confirmed

## Post-Job Checklist
- [ ] Residual secrets scan clean
- [ ] Temporary files and browser profiles cleared
- [ ] Routing and firewall still correct
- [ ] Kit inventory updated

The Kit / Computer Manager agent owns verification of this checklist and reports status to the Field Supervisor before work begins and after the job ends.
