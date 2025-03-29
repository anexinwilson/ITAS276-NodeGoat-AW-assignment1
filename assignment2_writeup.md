# ITAS 276 – Assignment 2 Write-Up (Part 1 Only)

This document contains the write-up for Part 1 of the DevSecOps Assignment 2.

## Part 1: Issue Identification and Reporting

### SAST Finding – Missing CSRF Protection

Tool: Semgrep  
File: server.js  
Issue: Missing CSRF middleware  
CWE: CWE-352  
Severity: Medium  

How I Identified It:  
I used the Semgrep-generated SARIF report and opened it in Visual Studio Code using the SARIF Viewer extension. Line 15 of server.js reported that CSRF protection middleware like `csurf` was not detected in the Express app.

What I Learned:  
I learned that CSRF protection is important for any web app that handles user sessions or form data. Semgrep is useful for detecting such issues early in development, especially in server-side files.

---

### SCA Finding – Vulnerable body-parser@1.18.3

Tool: Snyk  
Package: body-parser@1.18.3  
Issue: Amplification attack vulnerability  
Snyk ID: SNYK-JS-BODYPARSER-7926860  
Severity: High  

How I Identified It:  
I ran the `snyk test` command on my Node.js project. The output flagged body-parser@1.18.3 as vulnerable to amplification attacks. It recommended upgrading to version 1.20.3.

What I Learned:  
Even if I don’t manually install a vulnerable package, it can be included through other libraries. Tools like Snyk are helpful for scanning the entire dependency tree and finding hidden risks.

---

## Advisory Links

- SAST Advisory – Missing CSRF Protection: [https://github.com/anexinwilson/ITAS276-NodeGoat-AW-assignment1/security/advisories/GHSA-5j5h-3fc3-76fg]
- SCA Advisory – body-parser Vulnerability: [https://github.com/anexinwilson/ITAS276-NodeGoat-AW-assignment1/security/advisories/GHSA-4c82-fw7x-8m6w]
