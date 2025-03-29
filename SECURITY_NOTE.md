# SECURITY NOTE

## Accepted Risks

### 1. SAST Finding – Missing CSRF Middleware (Semgrep)
- **File**: server.js
- **Tool**: Semgrep
- **CWE**: CWE-352
- **Reason for Accepting Risk**:
  The application is currently under development and not exposed to real users.
  There are no user forms or sessions at this stage.
  CSRF protection will be implemented before production release.

---

### 2. SCA Finding – Vulnerable body-parser (Snyk)
- **Package**: body-parser
- **Version**: 1.18.3
- **Snyk ID**: SNYK-JS-BODYPARSER-7926860
- **Reason for Accepting Risk**:
  The vulnerable version is a legacy dependency.
  No public access or heavy traffic is expected.
  Risk is accepted temporarily, and the package will be updated in the future.
