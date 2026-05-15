# Authentication Review – Password Audit

## Purpose
Evaluate password strength and authentication security for the CMS.

## Steps
- Prepared a small, realistic password list based on weak patterns.
- Performed controlled password guessing using WPScan:
  - `wpscan --url http://<target-ip> --usernames Brian --passwords passwords.txt`
- Successfully authenticated as the user `Brian`.

## Findings
- Weak password policy in place.
- No multi-factor authentication (MFA) enabled.
- Admin interface exposed without rate limiting or lockout controls.
