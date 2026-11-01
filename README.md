# DeployCrew — Shree Sanitary (Laalwani) Software Releases

This repository is the official public release and automatic software update distribution channel for **Shree Sanitary (Laalwani Business Software)** developed by **DeployCrew**.

---

## 📦 Latest Release: `v1.0.0`

- **Software Name:** Shree Sanitary Commercial ERP
- **Release Date:** November 01, 2026
- **Architecture:** Windows 10 / Windows 11 (64-bit)
- **Installer Executable:** `Laalwani-Setup.exe`
- **Integrity Check (SHA-256):** `919FE5C33DE368B32EA1C7164E1CB7406734776566AEB3506D59A1DD069D5E3D`

---

## 🔄 Automatic Update Channel Protocol

The client desktop software running at Shree Sanitary counter periodically polls this repository's authoritative manifest [`latest.json`](latest.json):

1. **Manifest File:** [`latest.json`](latest.json) contains current version, semantic tags, release notes in Gujarati/English, and signed binary download URLs.
2. **Zero-Interrupt Policy:** The desktop application never interrupts active counter billing; updates are staged in the background and applied safely on user confirmation.
3. **Zero Data Loss Guarantee:** Only compiled desktop binaries are updated; all 10,000+ products, customer ledgers, and past invoice records remain untouched.

---
*Maintained by DeployCrew Engineering Directorate.*
