# Zimperium IOC Repository 🔐

A public collection of **Indicators of Compromise (IOCs)** extracted from mobile malware research conducted by the Zimperium zLabs team. These IOCs are intended to support threat intelligence, hunting, and detection efforts across security tools.

---

## 🗂 Repository Structure

Each subdirectory corresponds to a malware campaign or variant, named by date and threat identifier:

- `YYYY-MM-<Campaign name>`

### Example folder contents (`2024-07-OTP-Stealer/`):
```
C2.txt              – List of command‑and‑control domains/IPs
package-names.csv   – Targeted package IDs
sha256.txt          – Malware sample hashes
urls.txt            – Malicious download URLs
```

---

## 📥 How to Use

You can download and integrate IOCs for:

- **SIEM / EDR ingestion** – configure alerts and detection rules
- **Mobile threat hunting** – check for given hashes, domains, or apps
- **IOCs enrichment** – add context to historic or active investigations

Files (CSV, TXT) contain one IOC per line—easy to parse or import.

> ⚠️ Remember: IOCs are only part of the defense strategy. Real-time, behavioral-based detection remains critical.

---

## 🔄 Updates & Maintenance

New IOC directories are added with each zLabs disclosure. To stay up to date:

- ⭐ **Star** the repo
- 🔔 **Watch** for notifications
- Follow our technical publications at **zimperium.com/blog**

---

## 📚 Additional Resources

- Live mobile threat insights: [zimperium.com/blog](https://www.zimperium.com/blog)  
- Zimperium Mobile Threat Defense (MTD) solution: [MTD](https://zimperium.com/mtd/mobile-threat-defense)  
- Zimperium Mobile Runtime Protection (zDefend) solution: [zDefend](https://zimperium.com/maps/zDefend)

---

## 📨 Get In Touch

If you wish to contribute, report new IOCs, or have questions:

**Create an Issue** on GitHub

---

## ⚖️ Legal Disclaimer

This repository is provided “as‑is” for threat intel and defensive use only. Zimperium makes no guarantees regarding completeness or accuracy. Users assume full responsibility for how these IOCs are used.

---

© 2025 Zimperium, Inc. All rights reserved.

