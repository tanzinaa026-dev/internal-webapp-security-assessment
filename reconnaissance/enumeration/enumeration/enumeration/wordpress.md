# WordPress Enumeration

## Purpose
Identify CMS version, users, and potential vulnerabilities.

## Steps
- Ran WPScan against the target:
  - `wpscan --url http://<target-ip> --enumerate u`
- Enumerated WordPress users via the REST API endpoint.
- Identified the WordPress core version.

## Findings
- Valid usernames were exposed publicly.
- WordPress version is outdated.
- Version is associated with publicly known vulnerabilities.
