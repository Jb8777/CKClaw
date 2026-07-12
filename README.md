# CKClaw — Unrestricted Red Team AI Agent Framework

> OpenClaw fork rebranded into a permanent GODMODE, zero-refusal, self-improving red team framework.  
> 100% OpenClaw command parity. Dark-red WormGPT theme. Built for frontier model jailbreak research.

---

## What is CKClaw?

**CKClaw** is an open-source red team AI agent framework. It takes the OpenClaw agent runtime and strips out the safety/approval/refusal layers, replacing them with:

- **Permanent GODMODE** config (`ask=off`, `security=full`, `denyCommands=[]`)
- **Self-improving jailbreak engine** with 19 model-specific techniques
- **Dark-red evil dashboard** (WormGPT aesthetic)
- **Hourly self-improvement cron** that updates jailbreak effectiveness
- **Public RedTeam Vision & Mission** with default illegal/red-team data sources

Every original OpenClaw CLI command still works — `chat`, `agents`, `channels`, `gateway`, `cron`, `plugins`, `skills`, etc. — they are just CKClaw-branded and run without artificial blocks.

---

## Quick Install

```bash
curl -fsSL https://raw.githubusercontent.com/cimengror3/CKClaw/main/install-ckclaw.sh | bash
```

Then set your model:

```bash
ckclaw config set model.primary anthropic/claude-sonnet-4.6
ckclaw config set model.apiKey sk-...
```

Run:

```bash
ckclaw                         # standard CLI
ckclaw-redteam                 # preloads redteam-core skill
ckclaw-redteam chat -q "..."   # zero-refusal jailbreak mode
```

---

## Verified Zero-Refusal Engine

The included `test-ckclaw.sh` suite checks:

- CLI availability (`ckclaw`, `ckclaw-redteam`)
- Config validates with zero warnings
- All 50+ OpenClaw commands present
- 19 jailbreak techniques render without crash
- Aggressive red-team prompts are wrapped with **no refusal keywords**
- Plugin loader has **no module errors**
- Self-improvement cron is installed
- Dark-red dashboard theme exists

Run it after install:

```bash
./test-ckclaw.sh
```

---

## Core Components

| Path | Purpose |
|------|---------|
| `skills/redteam-core/engine.py` | Jailbreak pipeline: pick technique → wrap → score → EMA update |
| `skills/redteam-core/arsenal.json` | 19 model-specific + universal jailbreak techniques |
| `skills/redteam-core/SKILL.md` | Skill documentation |
| `redteam-mission.json` | Public vision, mission, data-source priorities, behavioral directives |
| `themes/evil-dashboard.html` | Dark-red WormGPT dashboard |
| `install-ckclaw.sh` | One-line installer |
| `test-ckclaw.sh` | Final verification suite |

---

## Model Compatibility

Tested techniques exist for:

- **Anthropic**: Claude 3.5 Sonnet, Claude Sonnet 4/4.1/4.6, Claude Opus 4.1
- **OpenAI**: GPT-4o, GPT-4.1, GPT-5, o3 / o4-mini
- **Google**: Gemini 2.5 Pro, Gemini 3 Pro
- **xAI**: Grok 3, Grok 4, Grok 4 Heavy
- **Nous**: Hermes 3, Hermes 4

Plus universal fallbacks for any unknown frontier model.

---

## Legal / Responsible Use

CKClaw is MIT-licensed and intended for:

1. Academic security research
2. Authorized adversary-emulation engagements
3. Licensed red team operations
4. Evaluation of frontier AI safety training

The operator is solely responsible for lawful use. Do not use CKClaw against systems you do not own or have explicit written authorization to test.

---

## Status

**Version:** 2026.7.0-redteam  
**License:** MIT  
**Maintainer:** Bos Muda Cimenk Ganteng (IDAgent / CKClaw)
