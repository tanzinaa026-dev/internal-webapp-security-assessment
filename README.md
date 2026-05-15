# Internal Web Application Security Assessment 

## Overview
This repository documents a full internal security assessment performed on a WordPress‑based blog hosted on an employee workstation. The goal of this assessment was to evaluate exposed services, identify misconfigurations, validate vulnerabilities, and demonstrate the potential impact of exploitation within a corporate environment.

All testing was performed in a controlled environment following approved scope and methodology.

---

## Assessment Scope
- Identify externally exposed services  
- Enumerate SMB, web, and CMS components  
- Assess authentication and password strength  
- Validate vulnerabilities in WordPress  
- Perform controlled exploitation to confirm risk  
- Conduct post‑exploitation analysis  
- Provide remediation recommendations  

---

## Repository Structure
```
/reconnaissance
notes.md

/enumeration
smb.md
web.md
wordpress.md

/authentication
password-audit.md

/vulnerability-analysis
findings.md

/exploitation
exploit-steps.md

/post-exploitation
database-access.md
config-review.md

/report
executive-summary.md
recommendations.md
```
## Summary of Work Performed

### Reconnaissance
Initial network scanning identified SSH, HTTP, and SMB services exposed from a workstation, indicating an expanded attack surface.

### Enumeration
- SMB share accessible without authentication  
- WordPress directories discovered  
- Usernames enumerated via REST API  
- Outdated WordPress version identified  

### Authentication Review
Weak password allowed login to the WordPress admin panel.  
No MFA, rate limiting, or lockout controls were present.

### Vulnerability Analysis
The WordPress version was vulnerable to a known remote code execution (RCE) exploit.

### Exploitation
A controlled Metasploit module was used to obtain a reverse shell on the host.

### Post‑Exploitation
- Extracted database credentials from `wp-config.php`  
- Accessed MySQL database  
- Identified plaintext credentials and sensitive data exposure  

### Reporting
Documented findings and provided actionable remediation steps.

---

## Tools Used
- Nmap  
- SMBClient  
- Gobuster  
- WPScan  
- Metasploit  
- MySQL  
- Linux command‑line utilities  

---

## Key Findings
- Weak authentication controls  
- Outdated WordPress installation  
- Exposed SMB share with no access restrictions  
- Sensitive configuration files accessible  
- No patch management or monitoring  
- Workstation hosting public‑facing services  

---

## Recommendations

### Authentication
- Enforce strong password policies  
- Enable MFA  
- Add rate limiting and lockout controls  

### System Hardening
- Move public-facing services off workstations  
- Restrict SMB access and apply ACLs  

### Patch Management
- Regularly update WordPress and plugins  
- Apply OS-level patches  

### Monitoring
- Enable logging for admin logins and suspicious activity  
- Forward logs to SIEM  

### Network Segmentation
- Limit workstation access to internal services  
- Reduce lateral movement paths  

---

## Conclusion
This assessment demonstrates how misconfigured services, weak authentication, and outdated software can lead to full system compromise. The project highlights the importance of proper hardening, patch management, and monitoring within an enterprise environment.
