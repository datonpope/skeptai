# SkeptAI Playground

The SkeptAI Playground is a browser-based interface for running CRIT 
analysis on any LLM output. No account required. No setup. Paste and run.

**Live:** [skeptai.lovable.app](https://skeptai.lovable.app) *(update with 
your production URL)*

---

## What It Does

The Playground runs the full four-module CRIT protocol on any text you 
paste into it:

1. **Assumption Excavator** — Surfaces every implicit assumption by type 
   and volatility
2. **Pressure Test** — Three adversarial lenses attack the output from 
   different angles
3. **Blind Spot Auditor** — Finds what the output never considered
4. **Rate & Report** — Scores the output across five dimensions and delivers 
   a disposition verdict

Analysis takes approximately 30-60 seconds depending on input length.

---

## Multi-Model Architecture

CRIT never uses the same model that produced the output to critique it. 
When you select your source model, the Playground automatically routes to 
a different model for the critique pass:

| Source Model | Critique Model |
|--------------|----------------|
| Claude | GPT-4o |
| GPT-4o | Claude |
| Gemini | Claude |
| Other | Claude |

This prevents the self-referential bias where a model defends its own 
reasoning patterns. The critique model is displayed in every CRIT report 
under "CRITIQUED BY."

---

## CRIT Actions

After every analysis, three actions are available:

**01 REMEDIATE** — Generates a revised version of the original output 
with all P0 and P1 findings addressed. Displayed side-by-side with the 
original so you can see exactly what changed and why.

**02 VERIFY** — Runs web search to confirm or refute factual claims 
inline. Each finding gets a ✓ CONFIRMED or ⚠ DISPUTED badge based on 
current information.

**03 ESCALATE** — Formats the full CRIT report as a GitHub issue template, 
ready to paste directly into any repository.

---

## Severity Scale

| Level | Name | Meaning |
|-------|------|---------|
| P0 | Critical | Project-ending if ignored |
| P1 | High | Significant setback, costly to recover |
| P2 | Medium | Meaningful friction, recoverable |
| P3 | Low | Minor issue, low consequence |

---

## Rate Limits

The Playground is free and open to use. To keep it accessible for everyone, 
each IP address is limited to 5 analyses per hour. For unlimited usage, 
use the CRIT framework directly via the prompt modules in `/crit/prompts/` 
with your own API key.

---

## Built With

- [Lovable](https://lovable.dev) — Frontend and Edge Functions
- [Anthropic Claude API](https://anthropic.com) — Primary reasoning model
- OpenAI GPT-4o — Cross-model critique pass

---

## Self-Hosting

The Playground is not currently packaged for self-hosting, but the complete 
CRIT prompts in `/crit/prompts/` can be used directly with any LLM API. 
Self-hosted deployment is on the v0.3 roadmap.

To follow progress: [github.com/datonpope/skeptai](https://github.com/datonpope/skeptai)
