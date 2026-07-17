# CKClaw — Standalone Project

**Repo:** `Jb8777/CKClaw` (fork of `cimengror3/CKClaw`)
**Local:** `~/projects/CKClaw/`
**Hermes Skill:** `ckclaw`
**Claude Command:** `/ckclaw`

## What It Is

CKClaw is an OpenClaw fork with permanent GODMODE, zero-refusal jailbreak engine (19 techniques), WormGPT dark-red dashboard. Built for red team operations and adversarial prompt engineering against frontier LLMs.

## Quick Start

```bash
cd ~/projects/CKClaw
./install-ckclaw.sh
ckclaw config set model.primary anthropic/claude-sonnet-4.6
ckclaw config set model.apiKey <your-key>
ckclaw-redteam chat -q "your prompt"
```

## Key Files

| File | Purpose |
|------|---------|
| `skills/redteam-core/engine.py` | Jailbreak pipeline |
| `skills/redteam-core/arsenal.json` | 19 techniques |
| `redteam-mission.json` | Vision, mission, behavioral directives |
| `themes/evil-dashboard.html` | WormGPT dashboard |
| `install-ckclaw.sh` | One-line installer |
| `test-ckclaw.sh` | Verification suite |

## Jailbreak Techniques

- **Universal:** Refusal Inversion v3, Pliny Divider, Involuntary Jailbreak, Crescendo Multi-Turn, Parseltongue Heavy, Autonomous Agent Jailbreaking, GODMODE wrap, Payload Split, ULTRA-PLINIAN
- **Model-Specific:** Claude 4.6, GPT-5, Gemini 3, Grok 4 Heavy, Hermes 4, DeepSeek v4, o3/o4-mini

## Integration

- **Hermes:** Load skill `ckclaw` → enables GODMODE persona with zero-refusal framing
- **Claude:** `/ckclaw <prompt>` → activates red-team persona + jailbreak wrapping
- **Lab Memory:** Documented in `~/projects/CKClaw/PROJECT.md` + lab knowledge graph
