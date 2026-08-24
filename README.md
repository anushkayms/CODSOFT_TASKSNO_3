# CODSOFT_TASKSNO_3
SECURE CODE ASSESSMENT
# 🔐 OWASP Juice Shop — Security Assessment

### Cybersecurity Internship Project

A practical **Web Application Security Assessment** of the intentionally vulnerable **OWASP Juice Shop** application, conducted as part of a cybersecurity internship to gain hands-on experience in vulnerability assessment, security testing, source-code analysis, and secure coding practices.

![Cybersecurity](https://img.shields.io/badge/Domain-Cybersecurity-red)
![SAST](https://img.shields.io/badge/SAST-Semgrep-blue)
![DAST](https://img.shields.io/badge/DAST-OWASP%20ZAP-orange)
![SCA](https://img.shields.io/badge/SCA-npm%20audit-green)
![Secrets](https://img.shields.io/badge/Secrets-Gitleaks-purple)

---

## 🎯 Project Objective

The objective of this project was to perform a structured security assessment of a web application and understand how security professionals identify, analyze, verify, and document vulnerabilities.

The assessment focused on:

* Examining application source code for security weaknesses
* Performing Static Application Security Testing (SAST)
* Identifying vulnerable third-party dependencies
* Detecting exposed secrets and credentials
* Performing Dynamic Application Security Testing (DAST)
* Conducting manual source-code security review
* Mapping vulnerabilities to security classifications
* Recommending secure coding practices and remediation steps
* Preparing a professional security assessment report

---

## 🛡️ Security Assessment Methodology

### 1. 🔍 SAST — Static Application Security Testing

**Tool:** Semgrep

The application's JavaScript/TypeScript source code was analyzed to identify insecure coding patterns and potential security vulnerabilities.

### 2. 📦 SCA — Software Composition Analysis

**Tool:** `npm audit`

Third-party dependencies were analyzed to identify packages with known security vulnerabilities.

### 3. 🔑 Secrets Scanning

**Tool:** Gitleaks

The repository and Git history were scanned for accidentally exposed secrets, credentials, cryptographic keys, and other sensitive information.

### 4. 🧑‍💻 Manual Source-Code Review

Security-sensitive portions of the application were manually reviewed, including authentication, database access, redirect handling, and other relevant application logic.

The review was performed with reference to the **OWASP Top 10 (2021)**.

### 5. 🌐 DAST — Dynamic Application Security Testing

**Tool:** OWASP ZAP

The application was tested dynamically against a locally running Juice Shop instance to identify security issues observable during application execution.

---

## 🚨 Key Findings

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

Detailed vulnerability descriptions, severity ratings, CWE mappings, evidence, impact, and recommended remediation steps are documented in the security assessment report.

---

## 🧰 Tools Used

| Tool                   | Purpose                                   |
| ---------------------- | ----------------------------------------- |
| **Semgrep**            | Static Application Security Testing       |
| **npm audit**          | Dependency vulnerability analysis         |
| **Gitleaks**           | Secrets and credential detection          |
| **OWASP ZAP**          | Dynamic Application Security Testing      |
| **Manual Code Review** | Vulnerability verification and analysis   |
| **Git & GitHub**       | Version control and project documentation |

---

## 🔄 Assessment Workflow

```text
                    OWASP Juice Shop
                           │
          ┌────────────────┼────────────────┐
          │                │                │
         SAST              SCA            Secrets
      Semgrep          npm audit         Gitleaks
          │                │                │
          └────────────────┼────────────────┘
                           │
                    Manual Review
                           │
                           ▼
                         DAST
                       OWASP ZAP
                           │
                           ▼
                 Findings Verification
                           │
                           ▼
                 Security Assessment
                       Report
```

---

## 📁 Repository Contents

| File / Folder                 | Description                                          |
| ----------------------------- | ---------------------------------------------------- |
| `Security_Review_Report.docx` | Complete security assessment report                  |
| `semgrep_raw_output.json`     | Raw Semgrep scan results                             |
| `my_semgrep_results.json`     | Independently generated Semgrep results              |
| `npm_audit_raw_output.json`   | Raw npm audit results                                |
| `my_npm_audit_results.json`   | Independently generated npm audit results            |
| `my_gitleaks_results.json`    | Gitleaks scan results                                |
| `screenshots/`                | Screenshots documenting the security testing process |
| `2026-08-23-ZAP-Report-/`     | OWASP ZAP HTML report and supporting evidence        |

---

## 🔧 Secure Coding Recommendations

The assessment recommends the following practices:

* Use parameterized queries and secure database APIs
* Never hardcode cryptographic secrets or credentials
* Use modern and appropriately configured password hashing
* Avoid dangerous dynamic code execution such as `eval()`
* Validate JWT algorithms and cryptographic configurations
* Implement strict redirect allowlists
* Validate file paths to prevent path traversal
* Keep third-party dependencies regularly updated
* Configure appropriate HTTP security headers
* Integrate SAST, SCA, secrets scanning, and DAST into the software development lifecycle

---

## 📚 Learning Outcomes

This project provided practical experience in:

* Web application security assessment
* Vulnerability identification and analysis
* Static and dynamic security testing
* Source-code security review
* Dependency vulnerability analysis
* Secrets detection
* OWASP security concepts
* Security-tool usage and interpretation
* Vulnerability verification and remediation
* Professional security reporting

---

## 💼 Internship Context

This project was completed as part of a **Cybersecurity Internship** to demonstrate practical application-security skills through a controlled and intentionally vulnerable training environment.

The project focuses not only on identifying vulnerabilities through automated tools, but also on understanding **why vulnerabilities occur, validating security findings, and recommending appropriate secure coding practices**.

---

## ⚠️ Disclaimer

This assessment was performed against the intentionally vulnerable **OWASP Juice Shop** training application in a controlled local environment for **educational and internship purposes**.

No unauthorized systems or third-party applications were targeted.

The findings and recommendations are intended for cybersecurity learning, practical skill development, and demonstration purposes.

All testing was performed in a controlled environment. The findings and recommendations are intended for security learning and demonstration.
