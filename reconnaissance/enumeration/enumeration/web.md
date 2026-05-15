# Web Enumeration

## Purpose
Identify web application structure and potential entry points.

## Steps
- Accessed `http://<target-ip>` in a browser.
- Observed a simple landing page indicating a blog or CMS behind it.
- Ran directory enumeration using Gobuster:
  - `gobuster dir -u http://<target-ip> -w /usr/share/wordlists/dirb/common.txt`

## Findings
- Discovered `/admin` and other relevant paths.
- Identified WordPress-related directories (`/wp-admin`, `/wp-content`, `/wp-includes`).
- Confirmed the application is WordPress-based.
