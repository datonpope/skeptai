# Contributing to SkeptAI

## The Fastest Way To Contribute

Build a domain module.

SkeptAI's CRIT framework is domain-agnostic by default. 
Domain modules are specialized configurations that make 
CRIT dramatically more powerful for specific document 
types and industries.

## Domain Modules We Need

These are the highest-priority modules we're looking for:

**Compliance CRIT** — Adversarial lenses calibrated for 
GRC documents, regulatory filings, audit reports, and 
risk assessments. P0 findings mapped to regulatory 
consequence rather than general risk.

**Contract CRIT** — For term sheets, investment agreements, 
NDAs, and legal contracts. Missing clauses, unfavorable 
terms, and ambiguous language surfaced as structured findings.

**Architecture CRIT** — For technical design documents, 
system architecture proposals, and API specifications. 
Scalability gaps, security assumptions, and dependency 
fragility as first-class findings.

**Medical CRIT** — For clinical documentation, treatment 
protocols, and medical advice outputs. Conservative P0 
thresholds given patient safety stakes.

## How To Submit A Domain Module

1. Fork the repository
2. Create a new folder: /domains/[your-domain]/
3. Add a CRIT configuration following the template in 
   /domains/template/
4. Include at least 3 example analyses showing the module 
   in action
5. Open a pull request with "Domain Module:" in the title

## Other Ways To Contribute

- Run CRIT on interesting outputs and share findings 
  as GitHub issues tagged "analysis-example"
- Improve the core prompt modules with findings from 
  real-world usage
- Translate the playground interface
- Build integrations (VS Code extension, Slack bot, 
  CI/CD plugin)
