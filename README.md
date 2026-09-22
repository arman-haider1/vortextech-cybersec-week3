# vortextech-cybersec-week3

**VortexTech Cyber Security Internship 2026 — Week 3 of 4**  
Basic Security Audit of a Sample Website

---

## What This Is

A structured, manual security audit performed against **OWASP Juice Shop** — a deliberately vulnerable web application designed for security practice. This audit was completed as part of the VortexTech Cyber Security Internship 2026 (Intermediate track, Week 3).

Testing was performed manually using **Browser DevTools** and authentication testing. Three findings are documented: SQL Injection, Sensitive Data Exposure, and a manual XSS test where successful XSS execution was not confirmed.

---

## Findings Summary

| # | Finding | Severity | Category |
|---|---|---|---|
| 1 | SQL Injection — Admin Authentication Bypass | 🔴 Critical | Injection (A03) |
| 2 | Sensitive Data Exposure via API Response | 🟡 Medium | Information Disclosure (A02) |
| 3 | Manual XSS Test — No Confirmed XSS | 🟡 Medium | Cross-Site Scripting (A03) |

**Total Findings: 3 — Critical: 1 | Medium: 2 | Low: 0**

> **Note:** The XSS test did not result in confirmed JavaScript execution. No JavaScript alert popup or other successful script execution was observed. It is documented as a manual XSS test result rather than confirmed XSS execution.

---

## Repository Structure

```text
vortextech-cybersec-week3/
├── report/
│   ├── VortexTech_Week3_Security_Audit_Manual.md   ← Full audit report (Markdown)
│   └── VortexTech_Week3_Security_Audit_Manual.pdf  ← Full audit report (PDF)
├── screenshots/
│   ├── 01-xss-search-payload.png
│   ├── 02-xss-network-request.png
│   ├── 03-api-sensitive-data-1.png
│   ├── 04-api-sensitive-data-2.png
│   ├── 05-auth-error-message.png
│   ├── 06-sqli-payload-entered.png
│   ├── 07-sqli-admin-menu.png
│   └── 08-sqli-admin-home.png
├── docker-compose.yml                               ← Runs OWASP Juice Shop
└── README.md
```

---

## How to Run the Practice Target

This audit was performed against a locally hosted OWASP Juice Shop instance via Docker.

### Prerequisites

- Docker Desktop installed

### Start Juice Shop

```bash
docker compose up -d
```

Then open your browser and go to:

```text
http://localhost:3000
```

### Stop Juice Shop

```bash
docker compose down
```

> ⚠️ **Important:** Only test against this local practice instance. Never perform security testing against real websites without explicit written permission.

---

## Tools Used

| Tool | Purpose |
|---|---|
| OWASP Juice Shop | Legal, deliberately vulnerable practice target |
| Docker | Running Juice Shop locally |
| Browser DevTools (F12) | Manual inspection of requests, responses, and network traffic |

---

## Methodology

All testing was performed manually following this workflow:

```text
Docker → Juice Shop (localhost:3000)
  ↓
Manual XSS testing (search bar)
  ↓
Manual API inspection (DevTools Network tab)
  ↓
Manual authentication testing (SQL Injection)
  ↓
Document findings + remediation
```

Each finding is documented with:

- Clear title and severity where applicable
- Steps taken to discover it
- OWASP Top 10 / CWE category
- Affected endpoint or functionality
- Evidence
- Potential real-world impact
- Practical remediation recommendation

The XSS test is explicitly documented as **no confirmed XSS**, because the payload did not result in JavaScript execution.

Full details are available in `report/VortexTech_Week3_Security_Audit_Manual.md`.

---

## Program Details

| Field | Details |
|---|---|
| **Program** | VortexTech Cyber Security Internship 2026 |
| **Track** | Cyber Security (Intermediate) |
| **Week** | 3 of 4 |
| **Report Date** | 17 September 2026 |
| **Target** | OWASP Juice Shop — `http://localhost:3000` |

---

## Disclaimer

This assessment was performed against a local, deliberately vulnerable practice application for educational and internship purposes.

No real production website or unauthorized system was targeted.

---

## Author

**Arman Haider**  
Cyber Security Intern  

**VortexTech Cyber Security Internship — Week 3 of 4**

