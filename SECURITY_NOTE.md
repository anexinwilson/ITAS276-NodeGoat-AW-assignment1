# SECURITY NOTE

This file documents the reasons for accepting identified security vulnerabilities found in the DevSecOps pipeline scans.

---

##  1. SAST Finding – Missing CSRF Middleware

- **File**: `server.js`
- **Tool**: Semgrep
- **CWE**: CWE-352
- **Severity**: Medium
- **Reason for Accepting Risk**:
  The application is currently in development and not publicly deployed.
  No forms or user sessions exist in the app at this time.
  CSRF protection will be added before production deployment.
  Fixing it now is not urgent due to the non-production context.

---

##  2. SCA Finding – Vulnerable body-parser@1.18.3

- **Tool**: Snyk
- **Package**: body-parser
- **Version**: 1.18.3
- **Snyk ID**: SNYK-JS-BODYPARSER-7926860
- **Severity**: High
- **Reason for Accepting Risk**:
  This vulnerability comes from a transitive dependency.
  The application is not exposed to public traffic and does not handle large external requests.
  Upgrading could introduce breaking changes, so the risk is temporarily accepted and tracked for future resolution.
