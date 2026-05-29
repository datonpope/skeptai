# skeptai
The adversarial reasoning agent for LLM outputs.
CRIT runs four structured passes on any LLM response — 
surfacing assumptions, pressure testing claims, auditing 
blind spots, and delivering a scored verdict — before 
you act on it.
<img width="1913" height="867" alt="Screenshot 2026-03-07 190537" src="https://github.com/user-attachments/assets/98c6dc96-7d86-48a7-ae7f-e8e134fccb60" />
## Why SkeptAI

LLMs optimize for confidence. CRIT optimizes for honesty.

Every LLM output you act on without adversarial scrutiny 
is a risk you inherited without knowing it. SkeptAI is 
the agent that challenges the output before you do.

## The CRIT Framework

CRIT runs four passes on every output:

**S — Surface Assumptions**  
Excavates every implicit assumption the model treated 
as true without stating it. Classifies by type and 
volatility.

**P — Pressure Test**  
Three adversarial lenses attack the output: The Skeptic, 
The Edge Case Hunter, The Adversarial User. Each finding 
is severity-rated P0 through P3.

**A — Audit Blind Spots**  
Four blind spot checks: perspective gaps, temporal gaps, 
dependency gaps, completeness gaps.

**R — Rate & Report**  
Five-dimension scoring, disposition verdict, priority 
actions, and what to salvage.

## Try It

→ [SkeptAI Playground](your-url-here)

## Integrate It

SDK coming in v0.2 — currently in active development.

In the meantime, use the playground at [skeptai.app](your-url) 
or call the CRIT engine directly via the API.

## Contribute

SkeptAI grows through domain modules — specialized CRIT 
configurations for specific document types and industries.

The first modules in development:
- Compliance CRIT — for GRC and regulatory documents  
- Contract CRIT — for term sheets and legal agreements
- Architecture CRIT — for technical design documents

To contribute a domain module, open an issue describing 
your domain and the specific adversarial lenses it needs.

## What's New — v0.2

- **Bring your own API key** — Paste your Anthropic API 
  key for unlimited analyses. Session-only, never stored.
- **Original prompt field** — Provide your original 
  request for sharper Completeness and Contextual 
  Fitness scoring.
  
## Roadmap

- [x] CRIT v0.1 — Core four-pass adversarial protocol
- [x] Playground — Browser-based analysis tool
- [x] CRIT Actions — Automated remediation layer
- [x] CRIT v0.2 — Optional prompt field + API key support
- [ ] Browser Extension — Chrome and Firefox
- [ ] SDK — Python and JavaScript packages
- [ ] Self-hosted — Run CRIT on your own infrastructure
- [ ] Domain Modules — Specialized industry configurations

## Data & Privacy

The SkeptAI playground stores no analyzed output content, no finding
text, and no user-identifying data.

To power pattern memory, it stores anonymized **structural metadata**
about the failure categories detected across analyses — categorical
tags only (failure type, severity, source/critique model, date) plus
counts. None of it can reconstruct any analyzed output, and only
Fact-Gate-verified findings contribute to displayed rates.

Rate limiting stores request IP addresses only. Row-level security
restricts all of the above to backend services; no public read or
write access exists.

## Built by

Daton Pope — Risk management professional 
turned agentic AI builder. 8+ years in GRC and enterprise 
risk. Building the adversarial layer that enterprises 
actually need.
