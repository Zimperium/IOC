# Technical Fingerprints & Behavioral Profiling

This document details the behavioral telemetry, host environment checks, backend collector software fingerprints, and binary patching artifacts observed across the Coruna exploit kit corpus.

---

## 1. Tracking Collector Software Fingerprints

Analysis of the configured tracking collectors (specifically `ips[.]ipnewadminshop[.]shop`) reveals commercial and open-source administration tooling commonly deployed across Chinese hosting services. These fingerprints characterize the server environment rather than the threat actors themselves.

| Fingerprint Element | Observed Value / Behavior | Analytical Context |
| :--- | :--- | :--- |
| **Control Panel Cookies** | `bt_route`, `server_name_session` | Characteristic of aaPanel / BaoTa (宝塔面板) Linux server management software. |
| **Admin Framework Routes** | `/api/getInfo`<br>`/api/captchaImage`<br>`/api/system/user/list` | Standard administration and user management routes of the RuoYi (若依) open-source enterprise management framework. |
| **Authentication Response** | `{"msg":"请求访问:/api/getInfo,认证失败,无法访问系统资源","code":401}` | Default RuoYi Spring Security 401 unauthenticated response payload. |
| **CORS Policy** | Tested `Origin: https://evil.test` reflected in `Access-Control-Allow-Origin` | Permissive/misconfigured CORS handling on collector beacon endpoints. |

---

## 2. Browser Profiling & Environment Checks

Before triggering the multi-stage WebKit chain, the browser loader profiles the client execution context to detect virtualization, automated analysis, and unsupported rendering environments.

### Tested DOM & Engine Properties
- `navigator.webdriver`: Validates that the browser is not being automated via WebDriver, Puppeteer, or headless automation frameworks.
- `IndexedDB Blob Handling`: Evaluates engine-level Blob serialization behavior within IndexedDB.
- `WebRTC Interfaces`: Probes `RTCPeerConnection` and related WebRTC APIs to inspect ICE candidate leakage and media stack availability.

*(Note: These checks do not establish reliable detection of iOS Lockdown Mode.)*

### Parent-Page Reload Intervals
Loader configurations employ periodic refresh timers on parent lure pages to sustain session presence or re-engage visitor state:
- **120,000 ms (2 minutes):** Default short-cycle rotation.
- **500,000 ms (8 minutes 20 seconds):** Configured on `pty[.]qm1[.]shop`, `pty[.]sxjk[.]shop`, `lelom[.]cc`, `tk[.]15xl[.]shop`, and `a[.]zq222[.]shop`.
- **6,000,000 ms (100 minutes):** Configured on adult-content portals `kjkp[.]com[.]cn` and `qcsh[.]com[.]cn`.

*(These timers operate independently of the 10-second beacon cadence sent to `/api/ip-sync/sync`.)*

---

## 3. Native Bootstrap Binary Diff & Patch Offsets

A modified bootstrap variant associated with `17k7k[.]live` (`9d47c97290af...embedded-native.bin`, 90,112 bytes) was identified alongside the reference `native_loader.dylib` (`e04fcb2b674e...`, 89,327 bytes). Binary diffing identified two instruction patches and a customized interception URL:

```
Offset 0x84ec:  01 04 00 54  ->  1f 20 03 d5   (B.NE bypassed via NOP: nop)
Offset 0x8bb0:  e1 03 00 aa  ->  41 81 01 70   (ARM64 register assignment modification)
Offset 0xbbdb:  Embedded string replacement:
                https://ubigdan69741536.icu/api/qqtime-native-intercept
```

Additionally, variant `c391bce7b09a0ea263e4b2c1d1bde0327c180723fa3299b006485429564c61ee` (89,328 bytes) displays 20 modified bytes and a trailing zero-byte relative to reference `native_loader.dylib`.

---

## 4. Native Container Architecture (19 Containers, 90 Entries)

Recovered Stage 3 payload archives wrap compiled Mach-O components in structured container bundles:

```
Container Format:
  [ Header Magic: 0xF00DBEEF ]
    └─► [ LZMA Compressed Payload: 0x0BEDF00D ]
          └─► [ Descriptor 1: 0xDEADD00F ]
                └─► [ Descriptor 2: 0x12345678 ]
```

### Module Distribution:
- **Type `0x09` (16 entries):** Kernel read/write primitives and AMFI policy relaxation (`developer_mode_status`, `allows_security_research`). Comprises 12 version-specific builds.
- **Type `0x0f` (14 entries):** Injects/checks system security daemons (`keybagd`, `CloudKeychainProxy`, `GSSCred`).
- **Type `0x08` (19 entries):** Orchestration engine, task-port memory reading (`mach_vm_read_overwrite`), and HTTPS C2 communications.
- **Type `0x0a` (11 entries):** Forensics scrubbers unlinking `ExcUserFault_com.apple.WebKit.WebContent*`, `JetsamEvent*`, `launchd.log`, and calling `deleteSafariWebsiteDataRecord:completionHandler:`.
- **Type `0x05` (2 entries):** Shellcode stagers.
- **Type `0x07` (28 entries):** Encrypted operational configuration blobs.
