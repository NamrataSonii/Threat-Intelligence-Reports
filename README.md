# CTI Reports — APT Threat Intelligence Analysis

Threat intelligence reports produced through independent research into three notable Advanced Persistent Threat (APT) groups. Each report includes actor profiling, indicators of compromise (IOCs), MITRE ATT&CK mapping, and defensive recommendations, built using open-source intelligence (OSINT) tools and public threat data.

---

## About This Repository

This repository contains deep-dive intelligence reports on three threat actors with distinct motivations and origins:

| Report | Threat Actor | Attribution | Primary Motivation |
|---|---|---|---|
| [APT40 Intelligent Report](./APT40%20Intelligent%20Report.pdf) | APT40 (aka Leviathan, TEMP.Periscope, TEMP.Jumper) | China-linked (MSS) | Naval/maritime technology espionage |
| [Dark hotel Intelligence Report](./Dark%20hotel%20Intelligence%20Report.pdf) | DarkHotel | Unattributed, highly targeted | Espionage against executives & officials |
| [Equation Group Intelligence Report](./Equation%20Group%20Intelligence%20Report.pdf) | Equation Group | Believed linked to NSA/TAO | Nation-state cyber-espionage |

Each report follows a consistent structure: **Executive Summary → Methodology → Detailed Analysis → Attribution & TTPs → Conclusion & Recommendations → Appendices**.

---

## Report Summaries

### 1. APT40
- **Active since:** 2013
- **Aliases:** Leviathan, TEMP.Periscope, TEMP.Jumper, APT 40
- **Target sectors:** Transportation, Government/Military, Education, IT, Communications, Manufacturing, Enterprise Services
- **Target regions:** Western Europe, North America, South-East Asia
- **Attack vectors:** Spear phishing, spam email, phishing, web shell deployment
- **Notable CVEs exploited:** CVE-2017-0199, CVE-2012-0158, CVE-2017-11882, CVE-2017-8759
- **Key IOC (analyzed sample):**
  - File: RTF payload exploiting CVE-2017-0199 (129.49 KB)
  - SHA-256: `6f6ee01e9dc2d8c4c260ef4131fe88dc152e53ee8afd3e66e92d4e1bf5fd2e92`
  - Malicious domain: `thyssenkrupp-marinesystems.org` (spoofing a German defense contractor)
  - C2 IP: `89.245.139.187`

### 2. DarkHotel
- **Active:** 10+ years
- **Targets:** C-level executives, government officials, high-value individuals
- **Attack vectors:** Hotel Wi-Fi compromise, spear phishing, P2P-distributed backdoors, zero-day exploits
- **Key IOC (analyzed sample):**
  - File: Malicious MS Excel spreadsheet (109.50 KB)
  - SHA-256: `a251ac8cec78ac4f39fc5536996bed66c3436f8c16d377922187ea61722c71f8`
  - Malicious domain: `fsm-gov.com`
  - C2 IP: `23.111.184.119`

### 3. Equation Group
- **Active since:** 1990s (major ops identified 2001–2015)
- **Attribution:** Believed linked to NSA Tailored Access Operations (TAO)
- **Targets:** Governments, military, financial institutions, telecom, energy, aerospace
- **Malware arsenal:** EquationDrug, DoubleFantasy, GrayFish, Fanny, Equestre
- **Notable for:** Hard-drive firmware infection (near-unremovable persistence); tools later leaked by The Shadow Brokers (incl. EternalBlue, which fueled WannaCry)
- **Key IOC (analyzed sample):**
  - File: GrayFish malware, Win32 EXE (560.00 KB)
  - SHA-256: `248c45236a4d4b5aec67b01a1e2e42a15bb6d2de0dee296f345d976ac01c3646`
  - Related domain: `arc.msn.com` (subdomain of msn.com)
  - C2 IP: `20.99.185.48`

---

## MITRE ATT&CK Coverage

| Tactic | APT40 | DarkHotel | Equation Group |
|---|---|---|---|
| Execution (TA0002) | — | PowerShell, Scripting, Native API | Scripting |
| Persistence (TA0003) | Event Triggered Execution | — | — |
| Privilege Escalation (TA0004) | Change Default File Association | Process Injection | Process Injection |
| Defense Evasion (TA0005) | Masquerading | Obfuscation, Masquerading, Sandbox Evasion | Software Packing, Process Injection |
| Discovery (TA0007) | — | — | System Information Discovery |

---

## Methodology & Tools Used

- **Subdomain enumeration:** Sublist3r, Subfinder, crt.sh
- **DNS/NS record analysis:** DNSDumpster, Whois Lookup
- **File & IOC analysis:** VirusTotal
- **Infrastructure pivoting:** Robtex
- **OSINT sourcing:** WHOIS records, public threat intel blogs (Recorded Future, Cyware, Check Point Research, CISA advisories), dark web forum monitoring

---

## Ethical Use Disclaimer

These reports are compiled for **educational and defensive research purposes only**, using publicly available threat intelligence, OSINT sources, and sandboxed malware analysis platforms (e.g., VirusTotal). No offensive tooling, exploit code, or live malware samples are included. IOCs are shared to support blue team detection, threat hunting, and awareness — not to facilitate malicious use.

---

## Author

**Namrata Soni**
Cybersecurity Postgraduate | SOC | Detection Engineering | Threat Intelligence
[LinkedIn](https://linkedin.com/in/namrata-soni-91a620275) · [GitHub](https://github.com/NamrataSonii)

---
If you find this useful for your own CTI learning, consider starring the repo.
