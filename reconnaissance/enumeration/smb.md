# SMB Enumeration

## Purpose
Assess file sharing exposure and identify misconfigurations.

## Steps Performed
- Listed SMB shares using:
  - `smbclient -L //<target-ip> -N`
- Identified share: `BillySMB`.
- Connected to the share without authentication:
  - `smbclient //<target-ip>/BillySMB -N`
- Downloaded available files for review.

## Findings
- SMB share accessible without credentials.
- Files stored without access control.
- Represents data exposure and workstation misconfiguration.
