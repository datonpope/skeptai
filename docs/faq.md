# SkeptAI — Frequently Asked Questions

---

## The Framework

**Why not just ask the LLM to critique its own output?**

This is the most common question and the answer is the core reason SkeptAI 
exists. When you ask an LLM to critique its own output, you are asking it to 
evaluate reasoning using the same reasoning patterns that produced the 
original response. The model will defend its own logic, soften its own 
errors, and miss its own blind spots — not because it's dishonest, but 
because it is structurally incapable of independently evaluating its own 
outputs.

CRIT solves this two ways. First, it uses a different model for the critique 
pass — Claude output gets critiqued by GPT-4o, and vice versa. Second, the 
CRIT protocol forces a structured adversarial stance rather than a balanced 
review. The Pressure Test module explicitly instructs the critique model to 
argue that the output is fundamentally wrong. That adversarial framing 
produces findings that self-critique never surfaces.

---

**Why is the original prompt optional? Shouldn't CRIT know what was asked?**

You're right that knowing the original prompt improves the Contextual Fitness 
and Completeness analysis. When provided, CRIT can evaluate whether the output 
actually answered what was asked — a gap that matters enormously in practice.

But requiring the prompt would create friction that breaks the use case. Most 
of the time, people are evaluating an output that emerged from a long 
conversation, multiple iterations, or a context they've already moved past. 
The prompt isn't cleanly accessible. More importantly, CRIT is designed to 
evaluate the output as a standalone decision-making artifact — the thing 
people will actually act on — regardless of how it was generated.

Even without the original prompt, CRIT catches factual errors, pressure-tests 
claims against adversarial lenses, surfaces blind spots across four categories, 
and scores deployment safety across five dimensions. None of that requires 
knowing the prompt.

The optional prompt field improves the analysis when provided. It does not 
gate the analysis when absent.

---

**What does CRIT actually do differently than just reading the output carefully?**

CRIT forces three things that careful reading doesn't:

1. **Structured adversarial stance.** Reading carefully tends toward charitable 
   interpretation. The Pressure Test module is explicitly instructed to build 
   the strongest possible case that the output is wrong. That framing surfaces 
   findings that a balanced reading misses.

2. **Blind spot enumeration.** The Blind Spot Auditor specifically looks for 
   what the output never considered — perspective gaps, temporal gaps, 
   dependency gaps, completeness gaps. These are invisible to a reader 
   evaluating what the output says rather than what it doesn't say.

3. **Cross-model critique.** The model critiquing the output is different from 
   the model that produced it. This isn't a stylistic choice — it prevents the 
   structural bias where a model evaluates its own reasoning patterns.

---

**What's the difference between P0, P1, P2, and P3?**

| Level | Name | Definition | Example |
|-------|------|------------|---------|
| P0 | Critical | Project-ending if ignored | A factual claim that is verifiably false and would cause the user to build on a nonexistent foundation |
| P1 | High | Significant setback, costly to recover | An assumption about market dynamics that is plausible but unvalidated and shapes the entire recommendation |
| P2 | Medium | Meaningful friction, recoverable | A timeline estimate that is optimistic but not catastrophically wrong |
| P3 | Low | Minor issue, low consequence | A framing preference or stylistic choice with no substantive impact |

A REJECT disposition typically means multiple P0 findings. A REVISE means 
P0/P1 findings that are addressable. A DEPLOY means findings are P2/P3 only. 
An ESCALATE means the stakes are too high for AI analysis alone.

---

**How accurate is the CRIT score?**

The score is a structured signal, not an objective measurement. Two CRIT 
analyses on the same output may produce scores that differ by 5-10 points 
depending on which model is critiquing and how the prompt conditions the 
adversarial stance. What remains consistent is the finding quality — the 
specific claims about specific problems with specific severity ratings.

Use the score as a directional indicator. Use the findings as your 
decision-making input.

---

## Technical

**What models does CRIT use?**

The Playground currently routes between Claude (Anthropic) and GPT-4o 
(OpenAI) depending on which source model you select. The routing logic 
ensures the critique model is always different from the source model.

The CRIT prompt modules in `/crit/prompts/` are model-agnostic — they work 
with any capable frontier model. If you're running CRIT locally, you can 
use any model pair you have access to.

---

**Can I run CRIT on my own infrastructure?**

Yes, with some assembly required. The complete prompt modules are in 
`/crit/prompts/`. You can use them directly with any LLM API. Call each 
module in sequence, passing prior module outputs as context into subsequent 
ones. The Rate & Report module synthesizes all prior findings into the 
final score and disposition.

Self-hosted packaging with a Docker container and configurable model 
routing is on the v0.3 roadmap.

---

**Is there an API?**

Not yet. The SDK is in active development for v0.2. To follow progress, 
watch the repository or follow [@getskeptai](https://twitter.com/getskeptai).

---

**What are the rate limits on the Playground?**

5 analyses per IP address per hour. This keeps the Playground free and 
accessible for everyone. For unlimited usage, run CRIT directly using the 
prompt modules with your own API key.

---

**Can I use my own API key?**

Yes. Enter your Anthropic API key in the optional field above the input area. This removes the rate limit for your session and uses your own token quota. Your key is used in-session only and is never stored, logged, or transmitted anywhere except directly to the Anthropic API.

---

## The Project

**Why open source?**

Two reasons. First, the CRIT framework only improves with scrutiny — 
which means it should be subject to the same adversarial reasoning it 
applies to LLM outputs. Open sourcing the prompts means practitioners 
can identify gaps, challenge the methodology, and contribute improvements.

Second, community is the moat. Domain modules — specialized CRIT 
configurations for specific industries — require domain expertise that 
no single team has. Open sourcing creates the contribution mechanic that 
lets the framework grow into compliance, legal, medical, architecture, 
and every other domain where AI output quality has high-stakes consequences.

---

**What's the roadmap?**

| Version | Status | What's included |
|---------|--------|-----------------|
| v0.1 | ✅ Live | CRIT four-pass protocol, Playground, CRIT Actions |
| v0.2 | 🔧 In development | SDK (Python + JavaScript), optional prompt field |
| v0.3 | 📋 Planned | Self-hosted deployment, Docker packaging |
| v0.4 | 📋 Planned | Domain modules, specialized industry configurations |

---

**Who built this?**

Daton Pope — risk management professional turned agentic AI builder. 
8+ years in GRC and enterprise risk. 
The adversarial reasoning patterns in CRIT are directly derived from 
how risk professionals evaluate information before making consequential 
decisions.

[@getskeptai](https://twitter.com/getskeptai) · 
[skeptai.dev](https://skeptai.dev) · 
[github.com/datonpope/skeptai](https://github.com/datonpope/skeptai)
