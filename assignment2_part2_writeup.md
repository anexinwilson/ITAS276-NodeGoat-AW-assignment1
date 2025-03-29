# ITAS 276 – Assignment 2 Write-Up (Part 2)

This document contains the brief write-up for Part 2 of the DevSecOps Assignment 2.

## SAST Finding – Missing CSRF Protection

- Tool: Semgrep  
- File: server.js  
- CWE: CWE-352  
- Severity: Medium  
- Action Taken: Risk Accepted  
- Justification:  
  The application is still in development and not accessible to external users. There are no login sessions or form inputs to protect. CSRF protection will be added before production deployment. This is documented in `SECURITY_NOTE.md`.

## SCA Finding – body-parser@1.18.3 Vulnerability

- Tool: Snyk  
- Package: body-parser  
- Snyk ID: SNYK-JS-BODYPARSER-7926860  
- Severity: High  
- Action Taken: Risk Accepted  
- Justification:  
  The vulnerable version is included indirectly through other dependencies. The app is not live and doesn’t receive real traffic. Fixing it now may break compatibility. This will be handled before production. Justification is included in `SECURITY_NOTE.md`.
