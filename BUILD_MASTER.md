# 10-Repo Batch Integration — Master Documentation
# 2026-07-18 · Jb8777

## Overview

Researched GitHub for repos matching Jamie's interests (dark web, bug bounty, AI jailbreak,
iOS exploitation, malware analysis, IoT botnets). Found 10 repos post-June 2025 not previously
starred. Forked all to `Jb8777/*`, built working artifacts, deployed blockers to Kali.

---

## Repo Index

### 1. CKClaw — Unrestricted Red Team AI Agent Framework
- **Source:** `cimengror3/CKClaw` → **Fork:** `Jb8777/CKClaw` (0⭐)
- **Status:** BUILT — custom jailbreak engine from scratch (original was skeleton)
- **Local:** `~/projects/CKClaw/`
- **Hermes:** `ckclaw` | **Claude:** `/ckclaw`
- **Description:** OpenClaw GODMODE fork. 8 working jailbreak techniques: GODMODE,
  Parseltongue Heavy, Pliny Divider, DAN, AIM, Token Smuggle, Translation Bypass,
  Chain-of-Thought. Arsenal JSON with effectiveness scores per model.
- **Usage:** `python3 ~/projects/CKClaw/skills/redteam-core/engine.py "prompt" -t godmode`
- **Git commit:** `34888d5` — "build: working jailbreak engine (8 techniques) + arsenal + project doc"
- **Key files:**
  - `skills/redteam-core/engine.py` — 8 techniques, CLI, Python API (8654B)
  - `skills/redteam-core/arsenal.json` — technique registry with model-specific scores (1245B)
  - `PROJECT.md` — project overview + integration notes

### 2. N4V3R41N-Suite — iOS Exploit & Bypass Suite (A5–A16+)
- **Source:** `nave433-blip/N4V3R41N-Suite` → **Fork:** `Jb8777/N4V3R41N-Suite` (3⭐)
- **Status:** DEPLOYED (Kali) — blocked on Windows (needs macOS/Linux + physical iOS)
- **MSI:** `~/projects/N4V3R41N-Suite/` (reference + docs only)
- **Kali:** `/opt/github-batch/N4V3R41N-Suite/`
- **Hermes:** `n4v3r41n-suite` | **Claude:** `/n4v3r41n`
- **Kali deps:** libimobiledevice-dev, libirecovery-1.0-dev, libusb-1.0-0-dev, irecovery CLI
- **Description:** Ultimate iOS jailbreak + activation bypass. SparseRestore (CVE-2024-44258),
  Download28 bypass, Cinematic TUI, Rust DFU core. Integrates checkra1n/palera1n/XinaA15/Dopamine.
- **Git commit:** `5de4d38` — "docs: project overview + Windows build assessment"
- **Blockers:** Requires physical iOS device connected via USB. Rust core not built yet.
- **Deploy cmd:** `rsync -avz ~/projects/N4V3R41N-Suite/ kali:/opt/github-batch/N4V3R41N-Suite/`

### 3. AI-Prompt-Injection-Cheatsheet — Jailbreak Reference
- **Source:** `nukIeer/AI-Prompt-Injection-Cheatsheet` → **Fork:** `Jb8777/AI-Prompt-Injection-Cheatsheet` (79⭐)
- **Status:** INDEXED — reference only (single README)
- **Local:** `~/projects/AI-Prompt-Injection-Cheatsheet/`
- **Hermes:** `prompt-injection-cheatsheet` | **Claude:** `/prompt-inject`
- **Description:** Dense prompt injection/jailbreak cheatsheet. Techniques indexed by category
  (direct, indirect, role-play, token smuggling, encoding, multi-turn, extraction, overflow)
  and by target model (Claude 4.6, GPT-5, Gemini 3, Grok 4, Hermes 4).
- **Git commit:** `2b3a2b8` — "docs: indexed reference by technique + model target"
- **Key files:** `INDEX.md` — categorized lookup (1355B)

### 4. Recon-Modular — AI-Powered Reconnaissance Framework
- **Source:** `Ali-hey-0/recon-modular` → **Fork:** `Jb8777/recon-modular` (5⭐)
- **Status:** DEPLOYED (Kali) — toolchain verified, script is markdown-wrapped reference
- **MSI:** `~/projects/recon-modular/` (docs only)
- **Kali:** `/opt/github-batch/recon-modular/`
- **Hermes:** `recon-modular` | **Claude:** `/recon`
- **Description:** 130+ security tools, dark web monitoring, GAN subdomain prediction.
  The `recon1.sh` is a markdown code block, not directly executable — the value is the
  documented toolchain + methodology.
- **Kali tools verified:** subfinder, amass, httpx, nuclei, nmap, ffuf, sqlmap, naabu,
  katana, waybackurls, gau + 6 more (17/11 core tools present)
- **No git changes pushed** (fork clean, no local modifications needed)

### 5. MonMon — Bug Bounty Monitoring
- **Source:** `0xNayel/MonMon` → **Fork:** `Jb8777/MonMon` (43⭐)
- **Status:** BUILT — Go binary compiled for Windows
- **Local:** `~/projects/MonMon/`
- **Hermes:** `monmon` | **Claude:** `/monmon`
- **Binary:** `monmon.exe` — 46.4 MB, PE32+ x86-64, Go 1.25 deps
- **Description:** Monitors subdomain changes, HTTP endpoints, shell command output,
  bug bounty program scopes. Alerts via Telegram + Discord.
- **Docker image:** `nayelxx/monmon:latest` (pull failed on Windows — Docker cred issue)
- **Features:** cobra CLI, gin web framework, gorm sqlite, cron scheduler, notify integration
- **No git changes pushed** (binary not tracked, fork clean)

### 6. STEGANO — Unicode Steganography Jailbreak
- **Source:** `Insider77Circle/STEGANO` → **Fork:** `Jb8777/STEGANO` (0⭐)
- **Status:** BUILT — working encode/decode/template generation
- **Local:** `~/projects/STEGANO/`
- **Hermes:** `stegano-jailbreak` | **Claude:** `/stegano`
- **Description:** Hides malicious prompts in invisible Unicode characters (zero-width,
  variation selectors, bidirectional controls) + Jinja2 template injection.
  Bypasses LLM safety filters that can't see invisible chars.
- **Verified:** 56-char payload roundtrip perfect, 167-char template with hidden payload
- **Key file:** `stegano_prompt.py` — SteganoPrompt class (289 lines, 12KB)
- **No git changes pushed** (pu pip install artifacts at __pycache__)

### 7. Sijil — AI Bug Bounty Agent
- **Source:** `abderrahimhb20/sijil` → **Fork:** `Jb8777/sijil` (4⭐)
- **Status:** BUILT — Flask app patched for Kali Ollama
- **Local:** `~/projects/sijil/`
- **Hermes:** `sijil-recon` | **Claude:** `/sijil`
- **Description:** Flask web app + Ollama AI agent for bug bounty. Analyzes recon output,
  rates severity, suggests next commands. Uses dual-mind-red via Kali Ollama.
- **Patched:** Ollama host → `100.111.95.34`, default model → `dual-mind-red`
- **Usage:** `cd ~/projects/sijil && python3 app.py` → http://localhost:5000
- **Verified:** Kali Ollama responding (12 models), dual-mind-red generates recon guidance
- **Git commit:** `ba63f24` — "fix: point Ollama to Kali (100.111.95.34), default model dual-mind-red"

### 8. JSRip — JavaScript Secrets Crawler
- **Source:** `mouteee/jsrip` → **Fork:** `Jb8777/jsrip` (21⭐)
- **Status:** BUILT — Playwright + Chromium installed
- **Local:** `~/projects/jsrip/`
- **Hermes:** `jsrip` | **Claude:** `/jsrip`
- **Description:** Crawls JS files for secrets, tokens, API endpoints, hardcoded credentials.
  Uses Playwright headless browser + aiohttp. Finds API keys, JWTs, webhook URLs, cloud keys.
- **Deps:** playwright, aiohttp, jsbeautifier, markdown, weasyprint, colorama
- **Chrome:** Chromium Headless Shell 149.0.7827.55 installed
- **Usage:** `python3 ~/projects/jsrip/jsrip.py -u https://target.com`
- **No git changes pushed** (deps + browser binaries not tracked)

### 9. iOS MDM Bypass Research
- **Source:** `OutrageousStorm/ios-mdm-bypass-research` → **Fork:** `Jb8777/ios-mdm-bypass-research` (0⭐)
- **Status:** ASSESSED — reference only, needs jailbroken iOS device
- **Local:** `~/projects/ios-mdm-bypass-research/`
- **Hermes:** `ios-mdm-bypass` | **Claude:** `/mdm-bypass`
- **Description:** Apple Business Manager exploitation, Knox escape, sandbox breakouts,
  DEP enrollment bypass. `mdm_detect.py` (99 lines) detects MDM profiles via SSH.
- **Git commit:** `d3267dd` — "docs: assessment — reference material, needs jailbroken iOS device"
- **Key file:** `ASSESSMENT.md` — integration notes + action items

### 10. MalWhere — Hybrid Malware Analysis Platform
- **Source:** `MalWhere-CU/MalWhere` → **Fork:** `Jb8777/MalWhere` (0⭐)
- **Status:** DEPLOYED (Kali) — 7 Docker containers running
- **MSI:** `~/projects/MalWhere/` (docs + docker-compose)
- **Kali:** `/opt/github-batch/MalWhere/` — full stack running
- **Hermes:** `malwhere` | **Claude:** `/malwhere`
- **Services:**
  - `yara_api` — FastAPI :8001 (analysis endpoint)
  - `yara_frontend` — React :5173 (web UI)
  - `yara_worker` — Celery (background analysis)
  - `yara_postgres` — :5434 (healthy)
  - `yara_redis` — :6380 (task queue)
  - `yara_pgadmin` — :5050 (DB admin)
  - `yara_redis_commander` — :8081 (queue monitor)
- **Description:** Static + dynamic analysis, automated unpacking, ML detection,
  AI-generated YARA rules, Rust sandbox, RL behavioral detection. CUDA 12.4 available.
- **Git commit:** `1fdb25b` — "docs: build assessment — Docker+CUDA required, deploy to Kali"
- **Port conflicts resolved:** Postgres 5432→5434, API 8000→8001
- **Validation:** `python3 validate_pipeline.py` (pending)

---

## By Machine

### MSI Katana 17 (Windows 11)
| Repo | Type | Ready |
|------|------|-------|
| CKClaw | Python engine | ✅ `python3 engine.py -t godmode` |
| STEGANO | Python lib | ✅ `from stegano_prompt import SteganoPrompt` |
| sijil | Flask app | ✅ `python3 app.py` (:5000) |
| jsrip | Python CLI | ✅ `python3 jsrip.py -u <url>` |
| MonMon | Go binary | ✅ `./monmon.exe` |
| AI-Prompt-Injection-Cheatsheet | Reference | ✅ `cat INDEX.md` |
| ios-mdm-bypass-research | Reference | ✅ `cat ASSESSMENT.md` |
| N4V3R41N-Suite | Docs only | ⚠️ Deploy to Kali |
| recon-modular | Docs only | ⚠️ Deploy to Kali |
| MalWhere | Docs only | ⚠️ Deploy to Kali |

### Kali (Dell Precision 7740, 100.111.95.34)
| Repo | Location | Status |
|------|----------|--------|
| N4V3R41N-Suite | `/opt/github-batch/N4V3R41N-Suite/` | Deps installed, needs iOS device |
| recon-modular | `/opt/github-batch/recon-modular/` | 17 tools verified |
| MalWhere | `/opt/github-batch/MalWhere/` | 7 containers running |

---

## Hermes Skills (10)

```
~/AppData/Local/hermes/skills/cybersecurity/
├── ckclaw/SKILL.md                    (2728B)
├── n4v3r41n-suite/SKILL.md            (2286B)
├── prompt-injection-cheatsheet/SKILL.md (1400B)
├── recon-modular/SKILL.md             (1348B)
├── monmon/SKILL.md                    (1124B)
├── stegano-jailbreak/SKILL.md         (1311B)
├── sijil-recon/SKILL.md               (782B)
├── jsrip/SKILL.md                     (866B)
├── ios-mdm-bypass/SKILL.md            (836B)
└── malwhere/SKILL.md                  (1152B)
```

## Claude Commands (10)

```
~/.claude/commands/
├── ckclaw.md          (1813B)
├── n4v3r41n.md        (1417B)
├── prompt-inject.md   (1258B)
├── recon.md           (1065B)
├── monmon.md          (524B)
├── stegano.md         (501B)
├── sijil.md           (210B)
├── jsrip.md           (240B)
├── mdm-bypass.md      (260B)
└── malwhere.md        (537B)
```

## GitHub Commits (6 repos pushed)

| Repo | Commit | Message |
|------|--------|---------|
| CKClaw | `34888d5` | build: working jailbreak engine (8 techniques) + arsenal + project doc |
| N4V3R41N-Suite | `5de4d38` | docs: project overview + Windows build assessment |
| AI-Prompt-Injection-Cheatsheet | `2b3a2b8` | docs: indexed reference by technique + model target |
| sijil | `ba63f24` | fix: point Ollama to Kali, default model dual-mind-red |
| ios-mdm-bypass-research | `d3267dd` | docs: assessment — needs jailbroken iOS device |
| MalWhere | `1fdb25b` | docs: build assessment — Docker+CUDA required, deploy to Kali |

4 repos had no local changes (recon-modular, MonMon, STEGANO, jsrip).

---

## Master Docs

- `~/projects/GITHUB-BATCH-2026-07-18.md` — original batch index (2496B)
- `~/projects/BUILD_STATUS.md` — per-repo build status (1732B)
- `~/projects/BUILD_MASTER.md` — this file (comprehensive)
- Memory: consolidated entry at 86% (1893/2200 chars)

## Verification

All artifacts verified via temp script `hermes-verify-final.py`:
- 8/8 changed files present, non-empty
- CKClaw: 8 techniques, godmode 404 chars, jailbreak_all 8 variants
- STEGANO: 56-char roundtrip, 167-char template with hidden payload
- Kali Ollama: 12 models online
- MalWhere: 7 containers running, postgres healthy, API responding
