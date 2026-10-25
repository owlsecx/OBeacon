# 🦉 OBeacon

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Linux-0a0c10?style=flat-square"/>
  <img src="https://img.shields.io/badge/Category-Security-blue?style=flat-square"/>
  <img src="https://img.shields.io/badge/License-MIT-green?style=flat-square"/>
  <img src="https://img.shields.io/badge/Part%20of-OwlSec%20Toolkit-7b5ea7?style=flat-square"/>
  <img src="https://img.shields.io/badge/Version-1.0-cyan?style=flat-square"/>
</p>

> **OBeacon** — part of the OwlSec Toolkit.

---

> ⚠️ **AUTHORISED USE ONLY** — Use only on systems you own or have explicit written permission to test. Unauthorised use is illegal.

---

## 📌 Overview

OBeacon finds malware beaconing: hosts that contact a command-and-control server at regular intervals. It reads common log formats or watches live connections, groups traffic by destination, and scores each group on timing regularity, periodicity and payload consistency. Each score comes with an explanation and an estimate of the sleep and jitter values.

---

## ✨ Features

- Reads plain text, syslog, Apache/Nginx/proxy, Zeek conn.log (TSV and JSON), CSV and JSON-lines logs
- Groups by destination, src→dst pair or dst:port; analyzes whole log directories
- Multi-factor beacon score: interval regularity (MAD), harmonic periodicity, Bowley skew, count and payload-size consistency
- Cobalt Strike-style sleep/jitter estimate, interval histogram and timeline sparkline
- Live monitor of /proc/net/tcp that names and scores the process behind each connection
- Allow-list (IPs, CIDRs, domains), private-IP filter, sample generator and --json output for SIEM pipelines

---

## ⚙️ Requirements

- **Linux**
- **No Python installation needed** — runs as a standalone executable

---

## 🚀 Usage

```bash
./OBeacon                                    # interactive menu
./OBeacon --file conn.log --group pair --min 10
./OBeacon --dir /var/log/proxy --ignore-private
./OBeacon --live -t 600
```

Run `./OBeacon --help` for the full list of options.

---

## 📦 Part of OwlSec Toolkit

This tool is part of the **OwlSec** suite — a collection of 300+ security and privacy tools.

🔗 [owlsec.org](https://owlsec.org)

---

## ©️ License

MIT License — © Khaled S. Haddad

*Tools are distributed as pre-built executables. Source code is proprietary.*
