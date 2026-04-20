# 🎣 Phishing Email Analysis Report – Microsoft Account Credential Harvesting Campaign

## Task Name
**Phishing Email Analysis — Microsoft Account Credential Harvesting Campaign**

---

## 📋 Project Overview

This project documents a complete **Phishing Email Analysis** performed on a captured email sample (`sample2.eml`). The email impersonates Microsoft by sending a fake "Unusual sign-in activity" security alert designed to steal victim credentials through a fraudulent login page.

The analysis follows a structured **seven-step methodology** — from initial sample collection through header authentication analysis, phishing indicator identification, IOC extraction, VirusTotal scanning, and user-facing prevention guidelines.

> **Verdict:** 🔴 `PHISHING — HIGH RISK` — 6 of 6 indicators confirmed.

> ⚠️ **Disclaimer:** This analysis was conducted strictly for educational and academic purposes within a controlled environment. The email sample was obtained from a public repository (GitHub) for training purposes only. No malicious activity was performed or facilitated.

---

## 🛠️ Tools & Environment

| Tool | Purpose |
|------|---------|
| **VS Code** | Manual inspection of raw `.eml` file source and header parsing |
| **MXToolbox** | Email header analysis, SPF/DKIM/DMARC record lookup, blacklist check |
| **Outlook** | Initial receipt and inspection of raw email, header viewing |
| **VirusTotal** | URL and domain reputation scanning, threat intelligence lookup |

---

## 🔍 Methodology

| Step | Phase | Description |
|------|-------|-------------|
| 1 | Collect Email Samples | Obtained `sample2.eml` from GitHub. Preserved full headers and body content for analysis |
| 2 | Analyse Email Headers | Examined SPF, DKIM, DMARC, Return-Path, and Received-SPF fields for authentication failures |
| 3 | Inspect Sender Domain & Links | Queried `microsoftonline-verify.com` via MXToolbox; expanded `bit.ly` shortener to reveal true destination |
| 4 | Identify Phishing Indicators | Catalogued technical and social engineering indicators including typosquatting, urgency language, and mismatched links |
| 5 | Classify Email Risk | Applied a three-tier classification framework (Safe / Suspicious / Phishing) |
| 6 | Document Findings | Recorded all IOCs, tool outputs, and screenshots in this structured report |
| 7 | Prevention & Awareness | Produced practical guidelines, Do's and Don'ts, and user education materials |

---

## 🚨 Phishing Indicators Found

| # | Indicator | Severity |
|---|-----------|----------|
| 1 | Spoofed Sender Domain — `microsoftonline-verify.com` (typosquat) | 🔴 Critical |
| 2 | SPF / DKIM / DMARC — all three authentication checks FAIL | 🔴 Critical |
| 3 | URL Shortener hiding real destination (`bit.ly/3vF9xKz`) | 🟠 High |
| 4 | Urgency & Social Engineering — `[Action Required]`, `X-Priority: 1` | 🟠 High |
| 5 | Fabricated Sign-In Activity Table (fake Russian IP `91.234.99.42`) | 🟠 High |
| 6 | Sender IP (`178.238.225.91`) resolves to Contabo VPS — not Microsoft infrastructure | 🟡 Medium |

---

## 🧩 Extracted IOCs (Indicators of Compromise)

| IOC Type | Value | Description |
|----------|-------|-------------|
| Sender Email | `noreply@microsoftonline-verify.com` | Typosquat of `microsoftonline.com` |
| Domain | `microsoftonline-verify.com` | Fake domain impersonating Microsoft |
| Sender IP | `178.238.225.91` | Contabo VPS, Germany — known phishing infrastructure |
| Shortened URL | `https://bit.ly/3vF9xKz` | Conceals real phishing destination |
| Fabricated IP | `91.234.99.42` | Fake Russian IP displayed in email body |
| Subject Line | `[Action Required] Unusual sign-in activity on your account` | Standard credential phishing lure |

---

## 📁 Repository Structure

```
📦 phishing-email-analysis/
├── 📁 images/                              # Evidence & proof-of-concept screenshots
│   ├── phishing_email_outlook.png          # Actual phishing email as received in Outlook
│   ├── mxtoolbox_header_analysis.png       # MXToolbox full header analysis results
│   ├── mxtoolbox_spf_dkim_dmarc.png        # SPF / DKIM / DMARC failure results
│   ├── vscode_eml_inspection.png           # Manual .eml inspection in VS Code
│   └── virustotal_scan_results.png         # VirusTotal URL & domain scan results
├── 📄 sample2.eml                          # Original phishing email sample
├── 📄 Phishing_report.pdf                  # Full phishing analysis report
└── 📄 README.md                            # This file
```

---

## ⚖️ Scope & Ethics

### ✅ Allowed
- Analysis of publicly available phishing samples from GitHub
- Passive header inspection and authentication checks
- Domain and URL reputation lookups via third-party tools
- Documentation of findings for academic purposes

### ❌ Not Allowed
- Visiting or interacting with the phishing URL
- Submitting credentials on any discovered page
- Using extracted IOCs for offensive purposes
- Distributing the phishing sample to unauthorized parties

> All activities conducted during this analysis strictly adhered to ethical cybersecurity practices and were performed solely within an educational context.

---

## 📄 Email Sample Details

| Field | Value |
|-------|-------|
| **Filename** | `sample2.eml` |
| **From** | `noreply@microsoftonline-verify.com` |
| **Subject** | `[Action Required] Unusual sign-in activity on your account` |
| **Sender IP** | `178.238.225.91` — Contabo VPS, Germany |
| **Embedded URL** | `https://bit.ly/3vF9xKz` |
| **Date** | February 6, 2026 |
| **Classification** | 🔴 PHISHING — HIGH RISK |

---

## 👤 Author

**Samson Budigila**
Cybersecurity Student 

Institute of Finance Management

Dar es Salaam, Tanzania


Internship: Future Interns

📧 [samsonbudigila6@gmail.com](mailto:samsonbudigila6@gmail.com)


📞 +255 757 502 743


🔗 [LinkedIn Profile](https://www.linkedin.com/in/samson-budigila-08112131a?utm_source=share_via&utm_content=profile&utm_medium=member_ios)

---

## 📄 License

This project is intended for **educational purposes only**. All findings are confidential and must not be used for unauthorized or malicious activities.
