# Threat Intelligence Indicators of Compromise: Coruna iOS Exploit Kit

This repository provides structured threat intelligence and Indicators of Compromise (IOCs) associated with the **Coruna iOS exploit kit** research published by zLabs.

The indicators catalog the entire attack chain—from disposable drive-by lures and supply-chain staging hosts to the browser-side profiling runtime, pointer authentication (PAC) bypasses, and post-sandbox native Mach-O payload modules.

## Threat Overview

Coruna is an advanced, modular iOS drive-by exploit framework capable of executing multi-stage WebKit exploits, bypassing Pointer Authentication Codes (PAC), and deploying native ARM64 payloads outside the browser sandbox without user interaction or profile installation.

Key operational findings:
- **Reusable Core Engine:** Across dozens of ephemeral lures (dating, AI companions, crypto, streaming), the decoded JavaScript loader runtime is byte-for-byte identical (29,924 bytes, SHA-256 `bbe0aa67e3d9d968220cd57f8f0ad4e676a4e968031b8ad2697fac40b1a68008`).
- **Decoupled Telemetry:** The kit separates affiliate/campaign tracking (beacons sent every 10 seconds) from browser-side exploit delivery logic.
- **Kernel & Integrity Manipulation:** Native payload modules manipulate Apple Mobile File Integrity (AMFI) kernel flags (`developer_mode_status` and `allows_security_research`) to relax system-wide code signing enforcement.
- **Anti-Forensics:** Deploys dedicated log-wiping modules targeting `ExcUserFault_com.apple.WebKit.WebContent*`, `JetsamEvent*`, `launchd.log`, and Safari website data records.

---

## Repository Structure

```text
├── README.md
├── network_indicators.csv       # Tracking collectors, C2s, staging domains, and IP pivots
├── lure_websites.csv            # 67 analyzed lure websites mapped to collectors & themes
├── loader_delivery_paths.csv    # Hidden frame paths, script injection URIs, and IP lookup APIs
├── native_payloads.csv          # Mach-O binaries, kernel drivers, and bootstrap SHA-256 hashes
├── native_module_inventory.csv  # Granular inventory of 90 extracted entries across 19 containers
├── code_markers.json            # Runtime namespaces, loader constants, regex, and beacon schema
├── native_signatures.json       # Memory magics, AMFI patch targets, TLS configs, and wiper paths
├── exploit_matrix.json          # Multi-stage WebKit and PAC bypass exploit version matrix
└── technical_fingerprints.md    # Collector software fingerprints, browser checks, and binary diffs
```

---

## Indicator Catalogs & Usage Guidelines

### 1. Network Infrastructure & Staging (`network_indicators.csv`)
Contains hostnames, domains, wildcard certificate pivots, and infrastructure IPs identified across campaigns.
* **Usage:** Ingest domains into DNS firewalls, Secure Web Gateways (SWG), and perimeter blocklists. Note that shared IP addresses (e.g., `5.255.61.234`) and certificate pivots represent investigation leads rather than standalone automated block indicators.

### 2. Front-End Lure Domains (`lure_websites.csv`)
A mapping of 67 identified lure websites, page themes (dating, AI companion, crypto giveaways, adult content), language localizations, and their associated backend tracking collectors.
* **Usage:** Useful for hunting affiliate-driven traffic redirection and analyzing localized social-engineering campaigns.

### 3. Native Mach-O Payloads & Hashes (`native_payloads.csv`)
Cryptographic SHA-256 hashes for reference ARM64 bootstrap binaries, orchestration modules (type `0x08`), kernel drivers (type `0x09`), credential service setup modules (type `0x0f`), and log-wipers (type `0x0a`).
* **Usage:** Add directly to EDR, Mobile Threat Defense (MTD), and file reputation blocklists.

### 4. Native Module Inventory (`native_module_inventory.csv`)
Itemized structural distribution of the 90 extracted entries across the 19 recovered payload containers (Table 8).
* **Usage:** Architectural assessment and signature verification across staged Mach-O modules.

### 5. Technical Fingerprints & Offsets (`technical_fingerprints.md`)
Narrative and reverse-engineering reference detailing:
* Server fingerprints for aaPanel/BaoTa and RuoYi management frameworks observed on collectors.
* DOM-level environment checks (`navigator.webdriver`, IndexedDB Blobs, WebRTC).
* Disassembly patch offsets (`0x84ec`, `0x8bb0`, `0xbbdb`) for custom native bootstrap binaries.

### 6. Code Markers & Telemetry Schema (`code_markers.json`)
Hierarchical signatures of the browser-side exploit loader:
* **Namespace:** `globalThis.obChTK`
* **Static Loader Key:** `cecd08aa6ff548c2`
* **Decoded Runtime SHA-256:** `bbe0aa67e3d9d968220cd57f8f0ad4e676a4e968031b8ad2697fac40b1a68008`
* **Beacon Signature:** `POST /api/ip-sync/sync` transmitting `{channelCode, ip, deviceVersion, domain}`.
* **Usage:** Write custom Suricata/Snort signatures or client-side DOM inspection rules.

### 7. Native Signatures & Anti-Forensics (`native_signatures.json`)
Machine-readable constants and system artifacts useful for host forensics and memory inspection:
* **Container & Frame Magics:** `0xF00DBEEF`, `0x0BEDF00D`, `0xDEADD00F`, `0x12345678`.
* **Kernel AMFI Hooks:** Target offsets for `developer_mode_status` and `allows_security_research`.
* **Host Forensics Clean-up Targets:** Diagnostic log patterns targeted for unlinking post-exploitation.
* **Usage:** Threat hunting across iOS diagnostic collections (`sysdiagnose`) and endpoint telemetry.

### 8. Exploit Targeting Matrix (`exploit_matrix.json`)
Documents the WebKit WebContent R/W primitives (CVE-2022-48503, CVE-2023-43000, CVE-2024-23222), PAC bypass modules (`breezy`, `seedbell`), and supported iOS ranges (iOS 13.0 through 17.2.1).
* **Usage:** Vulnerability risk modeling and fleet patch prioritization.

---

## Defensive Recommendations

1. **Prioritize Prompt OS Updates:** All identified WebKit vulnerabilities target known, patched security flaws. Keeping iOS devices updated to the latest minor/major builds disrupts the initial execution chain.
2. **Deploy Mobile Threat Defense (MTD):** Ensure corporate and BYOD endpoints have device-level telemetry to detect anomalous WebContent crashes, unexpected reboots, and AMFI code-signing state anomalies.
3. **Inspect Crash Logs Promptly:** Coruna actively unlinks crash records (`ExcUserFault_com.apple.WebKit.WebContent*`, `launchd.log`). Continuous or event-triggered log collection is necessary to retain evidence before wipers execute.
4. **Implement Content-Security-Policy (CSP):** Enforce strict script allowlists to prevent unauthorized nested iframes and typo-squatted CDNs (e.g., `ajax.googleapls.com`).

---

## Citation & References

* **Google Threat Intelligence Group (GTIG):** Initial analysis of Coruna iOS exploit kit (March 2026).
* **SafeDep:** Analysis of compromised `art-template` npm package (May 2026).
* **zLabs:** *Inside Coruna: From Web Lures to iOS Exploitation* (Santiago Rodriguez, Nico Chiaraviglio).
