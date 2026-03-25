# 🛡️ Phishing Detection & Awareness Report
### Cybersecurity Task 2 — Future Interns (2026)

> **Author:** Omoding innocent— Cybersecurity Intern  
> **Date:** 25 March 2026  
> **Classification:** Educational — For Training Purposes Only

---

## 📋 Table of Contents

- [About the Project](#about-the-project)
- [Repository Structure](#repository-structure)
- [Tools Used](#tools-used)
- [Analysis Approach](#analysis-approach)
- [Key Findings](#key-findings)
- [Sample Analyzed](#sample-analyzed)
- [Risk Classification](#risk-classification)
- [Prevention Guidelines](#prevention-guidelines)

---

## 📌 About the Project

This repository contains the deliverables for **Cybersecurity Task 2** focused on **Phishing Email Detection & Security Awareness**.

The goal is to work like a real **SOC / Security Analyst**:
- Analyze real-world phishing email samples
- Identify phishing indicators using technical header analysis
- Classify email risk levels
- Produce a professional awareness report usable in corporate training

> ⚠️ All email samples used are from **public phishing repositories** for **educational purposes only**.

---

## 📁 Repository Structure

```
📦 phishing-detection-task2/
├── 📄 README.md        
├── 📄 Phishing_Detection_Awareness_Report_Task2.docx  ← Full report (Word)
├── 📁 evidence/
│   ├── 🖼️ email_header_raw.png           ← Raw .eml source code (sample-1101)
│   └── 🖼️ email_header_toolbox.png       ← Google Admin Toolbox analysis result
└── 📁 samples/
    └── 📎 sample-1101.eml                ← Phishing email sample (source: rf-peixoto/phishing_pot)
```

---

## 🛠️ Tools Used

| Tool | Purpose | Link |
|------|---------|-------|
| **Google Admin Toolbox — Messageheader** | Parse and analyze raw email headers (SPF, DKIM, DMARC, routing) | [toolbox.googleapps.com](https://toolbox.googleapps.com/apps/messageheader/) |
| **MXToolbox Email Header Analyzer** | Secondary header verification and IP reputation check | [mxtoolbox.com](https://mxtoolbox.com/EmailHeaders.aspx) |
| **GitHub — rf-peixoto/phishing_pot** | Public repository of real collected phishing email samples | [github.com/rf-peixoto/phishing_pot](https://github.com/rf-peixoto/phishing_pot) |
| **Browser (Developer Tools)** | Safe URL inspection and domain verification without clicking | Built-in |
| **Microsoft Word / LibreOffice Writer** | Report documentation and formatting | — |

---

## 🔍 Analysis Approach

The analysis followed a structured **5-step methodology** used by real SOC analysts:

### Step 1 — Sample Collection
- Retrieved phishing email `sample-1101.eml` from the public repository [rf-peixoto/phishing_pot](https://github.com/rf-peixoto/phishing_pot/blob/main/email/sample-1101.eml)
- Selected based on its impersonation of a major corporate brand (Microsoft)

### Step 2 — Email Header Analysis
- Copied the raw `.eml` header content
- Submitted to **Google Admin Toolbox Messageheader** for automated parsing
- Identified all routing hops, timestamps, and authentication results

### Step 3 — Authentication Protocol Verification
Checked three critical email security protocols:

| Protocol | Checks | Result in Sample |
|----------|--------|-----------------|
| **SPF** (Sender Policy Framework) | Is the sending IP authorized by the domain? | ❌ NONE |
| **DKIM** (DomainKeys Identified Mail) | Is the email digitally signed? | ❌ NONE |
| **DMARC** | Does the domain have a security policy? | ❌ PERMERROR |

### Step 4 — Indicator Identification
- Compared **display name** vs **actual From address**
- Analyzed the **Reply-To** field for anomalies
- Verified the **sending IP** and its associated hostname
- Identified **social engineering tactics** in the email subject/body

### Step 5 — Risk Classification & Documentation
- Assigned a risk level based on cumulative indicators
- Documented findings in a professional report
- Created employee-facing prevention guidelines

---

## 🔎 Key Findings

### Sample: `sample-1101.eml` — Microsoft Account Spoofing

| Indicator | Finding | Risk |
|-----------|---------|------|
| Display Name | "Microsoft account team" | Spoofed |
| Actual Sender | `no-reply@access-accsecurity.com` | ❗ Fake domain |
| Reply-To | `solutionteamrecognizd03@gmail.com` | ❗ Free Gmail address |
| Sending IP | `89.144.9.87` (nonkfrgr.co.uk) | ❗ Unrelated to Microsoft |
| SPF | `none` | ❌ Unauthorized sender |
| DKIM | `none` | ❌ No digital signature |
| DMARC | `permerror` | ❌ No security policy |
| Subject | "Microsoft account unusual signin activity" | ⚠️ Fear/urgency tactic |
| Greeting | "Dear User" | ⚠️ Generic — not personalized |

---

## 🚨 Risk Classification

```
┌─────────────────────────────────────────────────┐
│                                                 │
│   ⚠  RISK LEVEL: CRITICAL                      │
│                                                 │
│   Type:   Credential Harvesting (Phishing)      │
│   Target: Microsoft Account Users               │
│   Method: Display Name Spoofing                 │
│   Confidence: 100%                              │
│                                                 │
└─────────────────────────────────────────────────┘
```

**Why CRITICAL?**
- All three email authentication protocols fail simultaneously
- The domain `access-accsecurity.com` is a typosquatting attempt against Microsoft
- The Reply-To redirects responses to a free Gmail account — a 100% red flag for fraud
- Social engineering via urgency and authority impersonation is present

---

## 🛡️ Prevention Guidelines

### For Employees — The 4 STOP Reflexes

| Letter | Reflex | Action |
|--------|--------|--------|
| **S** | Suspicion | Does this email create urgency or fear? |
| **T** | Test the link | Hover over links — check the real URL at the bottom of your browser |
| **O** | Origin | Read the full email address, not just the display name |
| **P** | Prudence | Never enter passwords or OTP codes from an email link |

### ✅ DO's
- ✔ Verify the sender's full email address (not just the name)
- ✔ Report suspicious emails via the "Report Phishing" button
- ✔ Navigate to official sites via browser bookmarks, not email links
- ✔ Contact IT immediately if you are unsure

### ❌ DON'Ts
- ✘ Click links in emails from unknown or unverified senders
- ✘ Open attachments from external/unexpected sources
- ✘ Enter credentials on any site reached from an email link
- ✘ Reply to or interact with the attacker

---

## 📚 References & Data Sources

> Used **for learning and study only** — content was not copied or reproduced.

- [rf-peixoto/phishing_pot](https://github.com/rf-peixoto/phishing_pot) — Real phishing email samples
- [autinerd/phishing-mail-examples](https://github.com/autinerd/phishing-mail-examples) — Header + body text samples
- [Google Admin Toolbox Messageheader](https://toolbox.googleapps.com/apps/messageheader/)
- [MXToolbox Email Header Analyzer](https://mxtoolbox.com/EmailHeaders.aspx)

---

## 🏷️ Tags

`cybersecurity` `phishing` `email-analysis` `soc-analyst` `security-awareness` `header-analysis` `spf` `dkim` `dmarc` `future-interns` `internship` `2026`

---

*This project was completed as part of the Future Interns Cybersecurity Internship Program (2026).*  
*All analysis is for educational purposes. No illegal activity was performed.*

