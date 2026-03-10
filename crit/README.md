# CRIT Framework

CRIT is SkeptAI's adversarial reasoning protocol. It runs 
four structured passes on any LLM output before you act on it.

## The Four Modules

| Module | Name | Function |
|--------|------|----------|
| 01 | Assumption Excavator | Surfaces implicit assumptions by type and volatility |
| 02 | Pressure Test | Three adversarial lenses attack the output |
| 03 | Blind Spot Auditor | Finds what the output never considered |
| 04 | Rate & Report | Scores, verdicts, and priority actions |

## Severity Scale

| Level | Name | Definition |
|-------|------|------------|
| P0 | Critical | Project-ending if ignored |
| P1 | High | Significant setback, costly to recover |
| P2 | Medium | Meaningful friction, recoverable |
| P3 | Low | Minor issue, low consequence |

## Dispositions

| Signal | Meaning |
|--------|---------|
| 🔴 REJECT | Do not act. Restart with better context. |
| 🟡 REVISE | Has value but needs targeted fixes first. |
| 🟢 DEPLOY | Reliable enough to act on. |
| ⚪ ESCALATE | Too consequential for AI analysis alone. |

## Using CRIT

The prompts in `/crit/prompts/` are the complete system 
prompts for each module. You can use them directly with 
any LLM API or through the SkeptAI playground.
