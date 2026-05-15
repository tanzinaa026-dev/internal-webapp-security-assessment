# Reconnaissance Notes

## Purpose
Identify externally exposed services and map the initial attack surface.

## Scan Results
- SSH (22/tcp) – Remote access service detected.
- HTTP (80/tcp) – Web application detected.
- SMB (445/tcp) – File sharing service exposed.

## Observations
- Multiple externally exposed services increase the attack surface.
- A workstation appears to be hosting services that should be on a hardened server.
- Further enumeration is required before moving to vulnerability analysis.
