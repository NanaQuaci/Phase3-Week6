# 🛡️ Security Audit and Reporting – Week 6 Lab Activity

This project is part of **Week 6 – Security Testing Lab**, focusing on performing a **security audit** of the [Swag Labs](https://www.saucedemo.com/) web application.  
It demonstrates **security testing techniques** such as vulnerability scanning, input validation checks, and authentication/authorization reviews.

Using **OWASP ZAP (Dockerized)**, the pipeline performs **Dynamic Application Security Testing (DAST)** and publishes an automated security report.

---

## 📌 Application Under Test
- **Target App:** [Swag Labs](https://www.saucedemo.com/)
- **Scope:**
    - User login
    - Product search
    - Product details page
    - Cart functionality
    - Checkout

---

## 🚀 Features
- Automated **OWASP ZAP scans** against Swag Labs.
- Report generated in **HTML format**.
- Reports are:
    - Stored as build artifacts
    - **Deployed to GitHub Pages** → [View Latest Report Here](https://nanaquaci.github.io/Phase3-Week6/zap_report.html)
- **Slack notifications** for CI/CD results.

---

## 📂 Project Structure
```
Phase3-Week6/
│
├── .github/workflows/      # CI/CD workflows (ZAP scan + deployment)
├── reports/                # ZAP reports (generated at runtime)
├── Security_Audit_Report.docx   # Word-based formal report
└── README.md               # Project documentation
```

---

## ⚙️ CI/CD Workflow
The CI/CD pipeline runs on every push to `main`:
1. **Checkout repository**
2. **Run ZAP scan** inside Docker
3. **Generate HTML report** (`reports/zap_report.html`)
4. **Upload as artifact**
5. **Deploy to GitHub Pages**
6. **Send Slack notification** (✅ success / ❌ failure)

---

## 📊 Security Audit Report
The **formal audit report** includes:
- Executive Summary
- Scope
- Methodology
- Vulnerabilities (with evidence)+++
- Test Results
- Risk Assessment & Prioritization
- CI/CD Integration with OWASP ZAP

👉 Download the **Word Report**: `Security_Audit_Report.docx` (in repo)  
👉 View the **Latest Automated ZAP Report**: [GitHub Pages Report](https://nanaquaci.github.io/Phase3-Week6/zap_report.html)

---

## 📝 How to Run Locally (Optional)
If you want to run the ZAP scan locally via Docker:

```bash
docker run --rm -u root -v $(pwd):/zap/wrk/:rw   zaproxy/zap-stable   zap-baseline.py   -t https://www.saucedemo.com   -r local_zap_report.html
```

---

## 🏆 Grading Scheme
| Metric                                           | Score   |
|--------------------------------------------------|---------|
| Executive Summary                                | 10      |
| Scope                                            | 10      |
| Methodology                                      | 15      |
| Vulnerabilities                                  | 15      |
| Test Results                                     | 10      |
| Risk Assessment & Prioritization                 | 10      |
| CI/CD Pipeline, Notification & Report Generation | 30      |
| **Total**                                        | **100** |

---

## 👨‍💻 Author
**Nana Quaci**  
*QA Engineer – Week 6 Security Testing Lab*
