# CODSOFT_TASKSNO_3
SECURE CODE ASSESSMENT
# OWASP Juice Shop — Security Source Code Review

A source-code and application security assessment of **OWASP Juice Shop**, performed as an internship project.

## Project Overview

This project examines the intentionally vulnerable OWASP Juice Shop application from both a source-code and runtime security perspective.

The assessment combines static analysis, dependency analysis, secrets scanning, manual source-code review, and dynamic application security testing.

## Methodology

* **SAST** — Static Application Security Testing using Semgrep with JavaScript/TypeScript security rules
* **SCA** — Software Composition Analysis using `npm audit`
* **Secrets Scanning** — Repository and Git history scanning using Gitleaks
* **Manual Review** — Review of authentication, database access, redirect handling, and other security-sensitive code against OWASP Top 10 (2021)
* **DAST** — Dynamic Application Security Testing using OWASP ZAP against a locally running Juice Shop instance

## Live Security Assessment Report

The complete OWASP ZAP HTML report generated during the DAST assessment is available here:

🔗 [View Live OWASP ZAP Report]([Uploading 2026-08-23-ZAP-Report-.html…])

The report contains detailed information about the requests, responses, alerts, risk levels, and findings identified during the security assessment.

## Key Findings

The assessment identified multiple source-level and runtime security issues, including:

* SQL Injection
* Hardcoded cryptographic secrets and weak password hashing
* Server-side code injection through `eval()`
* JWT algorithm confusion
* Broken redirect allowlist logic
* Path traversal risks
* Vulnerable third-party dependencies
* Missing or misconfigured security headers
* Additional runtime security findings identified through DAST

Detailed findings, severity ratings, CWE mappings, evidence, and recommended fixes are documented in the security review report.

## Tools Used

| Tool               | Purpose                                     |
| ------------------ | ------------------------------------------- |
| Semgrep            | Static code analysis / SAST                 |
| npm audit          | Dependency vulnerability analysis / SCA     |
| Gitleaks           | Secrets detection                           |
| OWASP ZAP          | Dynamic application security testing / DAST |
| Manual Code Review | Verification and security analysis          |

## Repository Contents

| File / Folder                 | Description                                |
| ----------------------------- | ------------------------------------------ |
| `Security_Review_Report.docx` | Full security assessment report            |
| `semgrep_raw_output.json`     | Semgrep scan output                        |
| `my_semgrep_results.json`     | Independently generated Semgrep results    |
| `npm_audit_raw_output.json`   | npm audit scan output                      |
| `my_npm_audit_results.json`   | Independently generated npm audit results  |
| `my_gitleaks_results.json`    | Gitleaks scan results                      |
| `screenshots/`                | Evidence screenshots from the assessment   |
| `2026-08-23-ZAP-Report-/`     | OWASP ZAP HTML report and supporting files |

## Assessment Workflow

```text
OWASP Juice Shop
       │
       ├── SAST → Semgrep
       │
       ├── SCA → npm audit
       │
       ├── Secrets → Gitleaks
       │
       ├── Manual Source Review
       │
       └── DAST → OWASP ZAP
                    │
                    ↓
             Findings Verification
                    │
                    ↓
             Security Report
```

## Security Recommendations

The assessment recommends practices including:

* Use parameterized queries and safe database APIs
* Never hardcode cryptographic secrets
* Use modern password hashing algorithms with appropriate configuration
* Avoid dangerous dynamic code execution such as `eval()`
* Validate JWT algorithms and cryptographic configuration securely
* Implement strict redirect allowlists
* Validate and sanitize file paths to prevent traversal
* Keep third-party dependencies updated
* Configure appropriate HTTP security headers
* Perform regular SAST, SCA, secrets scanning, and DAST during development

## Disclaimer

This assessment was performed against the intentionally vulnerable **OWASP Juice Shop** training application for educational and internship purposes.

All testing was performed in a controlled environment. The findings and recommendations are intended for security learning and demonstration.
