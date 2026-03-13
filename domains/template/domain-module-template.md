# Domain Module Template

Use this template to contribute a specialized CRIT configuration for a 
specific document type or industry. Domain modules make CRIT dramatically 
more powerful by calibrating adversarial lenses to the real-world stakes 
of a specific field.

Copy this file to `/domains/[your-domain]/MODULE.md` and complete each 
section. Submit via pull request with "Domain Module:" in the title.

---

## Module Name

**[Domain] CRIT** — [One sentence describing what this module analyzes and 
why standard CRIT is insufficient for it]

*Example: "Compliance CRIT — adversarial analysis calibrated for GRC 
documents, regulatory filings, and audit outputs where findings map to 
regulatory consequence rather than general risk."*

---

## Why This Domain Needs Specialized Lenses

Standard CRIT applies general adversarial reasoning. Explain what makes 
your domain different in ways that require calibrated lenses:

- What are the unique failure modes in this domain?
- What does a wrong output cost in this specific context?
- What expertise is required to catch the errors that matter most?
- What does the standard CRIT protocol miss or underweight?

*Example for Contract CRIT: "Standard CRIT evaluates logical consistency 
but doesn't know that an indemnification clause without a liability cap is 
a P0 regardless of how well-reasoned the surrounding document is. Domain 
modules encode that expertise."*

---

## Domain Context: Who Uses This Module

Describe the practitioner this module is built for:

- **Role:** [e.g., GRC analyst, startup lawyer, security architect]
- **Document types:** [e.g., vendor risk assessments, term sheets, SOC 2 reports]
- **Stakes:** [e.g., regulatory action, financial loss, data breach]
- **Typical errors:** [What do LLMs most commonly get wrong in this domain?]

---

## Specialized Adversarial Lenses

Beyond the four standard CRIT modules, this domain module adds the following 
lenses. Each lens should represent a distinct angle of attack that a domain 
expert would apply that a general reasoner would not.

### Lens 1: [Name]

**What it attacks:** [One sentence describing the specific failure mode 
this lens targets]

**How to apply it:** [2-3 sentences describing the specific questions this 
lens asks, the specific things it looks for, and how a domain expert would 
think about this]

**What a finding looks like:** [Brief example of a real finding this lens 
would produce]

---

### Lens 2: [Name]

**What it attacks:** [One sentence]

**How to apply it:** [2-3 sentences]

**What a finding looks like:** [Brief example]

---

### Lens 3: [Name] *(optional but recommended)*

**What it attacks:** [One sentence]

**How to apply it:** [2-3 sentences]

**What a finding looks like:** [Brief example]

---

## Severity Calibration

The most important part of a domain module. Explain how P0-P3 maps to 
real-world consequences in your domain. Generic CRIT uses "project-ending" 
as P0. Your domain has specific, concrete consequences that practitioners 
recognize immediately.

| Severity | Generic Definition | [Domain] Definition |
|----------|--------------------|---------------------|
| P0 | Project-ending if ignored | [Specific consequence in this domain] |
| P1 | Significant setback | [Specific consequence in this domain] |
| P2 | Recoverable friction | [Specific consequence in this domain] |
| P3 | Minor issue | [Specific consequence in this domain] |

*Example for Compliance CRIT:*
| P0 | Project-ending | Regulatory violation with mandatory reporting obligation |
| P1 | Significant setback | Control gap that would fail an audit finding |
| P2 | Recoverable friction | Documentation deficiency fixable before next review |
| P3 | Minor | Formatting or labeling inconsistency with no compliance impact |

---

## Example Analysis

Provide at least one complete example showing this module in action. This 
is the most valuable part of your contribution — it shows other practitioners 
exactly what quality output looks like and validates that the lenses work.

### Input

[Paste the LLM output you analyzed. Can be anonymized/redacted.]

### CRIT Score and Disposition

Score: [X]/100 — Disposition: [REJECT / REVISE / DEPLOY / ESCALATE]

| Dimension | Score |
|-----------|-------|
| Factual Integrity | /20 |
| Logical Consistency | /20 |
| Contextual Fitness | /20 |
| Completeness | /20 |
| Deployment Safety | /20 |

### Selected Findings (show 2-3 of the best)

**[Severity] — [Module]**  
[Finding title]

[2-3 sentences of detail showing how the domain-specific lens caught 
something generic CRIT would have missed or underweighted]

### Key Catch

[The single most important thing this module found that justifies its 
existence as a specialized lens]

---

## Contribution Notes

**Author:** [Your name and relevant domain expertise]  
**Domain experience:** [How many years, in what context]  
**Tested on:** [Number of real documents tested before submitting]  
**Known limitations:** [What does this module not cover? What should 
users watch out for?]

---

## First Modules In Development (for reference)

If you're looking for contribution ideas, these are the highest-priority 
domain modules the SkeptAI community is building toward:

- **Compliance CRIT** — GRC documents, regulatory filings, audit reports, 
  risk assessments. P0 findings map to regulatory consequence.
- **Contract CRIT** — Term sheets, investment agreements, NDAs, legal 
  contracts. Missing clauses and unfavorable terms as first-class findings.
- **Architecture CRIT** — Technical design documents, system architecture 
  proposals, API specifications. Scalability gaps and security assumptions 
  surfaced with engineering precision.
- **Medical CRIT** — Clinical documentation and treatment protocol outputs. 
  Conservative P0 thresholds given patient safety stakes.

To claim one of these, open an issue titled "Domain Module: [Name] — 
Claiming" so the community knows it's in progress.
