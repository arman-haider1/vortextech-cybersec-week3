# vortextech-cybersec-week3

**VortexTech Cyber Security Internship 2026 — Week 3 of 4**  
Basic Security Audit of a Sample Website

---

## What This Is

A structured, manual security audit performed against **OWASP Juice Shop** — a deliberately vulnerable web application designed for security practice. This audit was completed as part of the VortexTech Cyber Security Internship 2026 (Intermediate track, Week 3).

Testing was done entirely manually using **browser DevTools** (no automated scanner). Three vulnerabilities were discovered and documented across three distinct OWASP Top 10 categories.

---

## Findings Summary

| # | Finding | Severity | Category |
|---|---|---|---|
| 1 | SQL Injection — Admin Authentication Bypass | 🔴 Critical | Injection (A03) |
| 2 | Sensitive Data Exposure via API Response | 🟡 Medium | Info Disclosure (A02) |
| 3 | XSS Input Accepted in Search Bar | 🟡 Medium | Cross-Site Scripting (A03) |

**Total: 3 findings — Critical: 1 | Medium: 2 | Low: 0**

---

## Repository Structure

```
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
- [Docker Desktop](https://www.docker.com/products/docker-desktop/) installed

### Start Juice Shop

```bash
docker compose up -d
```

Then open your browser and go to:

```
http://localhost:3000
```

### Stop Juice Shop

```bash
docker compose down
```

> ⚠️ **Important:** Only test against this local instance. Never perform security testing against real websites without explicit written permission.

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

```
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
- Clear title and severity
- Steps taken to discover it
- OWASP Top 10 / CWE category
- Potential real-world impact
- Practical remediation recommendation

Full details in [`report/VortexTech_Week3_Security_Audit_Manual.md`](report/VortexTech_Week3_Security_Audit_Manual.md)

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

*VortexTech · Cyber Security Internship 2026 · vortextechnologies77@gmail.com*

