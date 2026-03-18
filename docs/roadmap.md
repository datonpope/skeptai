[skeptai-roadmap.md](https://github.com/user-attachments/files/26101929/skeptai-roadmap.md)
# SkeptAI — Product Roadmap

---

## v0.1 — SHIPPED ✅
*Core adversarial reasoning engine*

- CRIT four-pass protocol (Assumption Excavator, Pressure Test, 
  Blind Spot Auditor, Rate & Report)
- Browser-based playground at skeptai.dev
- Multi-model routing (Claude output → GPT-4o critique, vice versa)
- CRIT Actions: REMEDIATE, VERIFY, ESCALATE
- Try An Example demo flow (23/100 REJECT moment)
- Open source framework — prompts published at github.com/datonpope/skeptai
- Rate limiting (5 analyses/hour per IP)
- Share Report functionality
- GitHub issue export template

---

## v0.2 — IN DEVELOPMENT 🔧
*Depth and personalization layer*

### Original Prompt Field (optional)
- Add optional "What did you ask?" input above the output textarea
- When provided: feeds into Contextual Fitness and Completeness 
  scoring in Module 4
- When absent: CRIT evaluates output as standalone artifact (current behavior)
- UI label: "Original prompt (optional) — improves Completeness scoring"
- FAQ update: document how this affects the analysis

### Bring Your Own API Key
- Optional field: "Use your own Anthropic API key for unlimited analyses"
- Stored in session only — never persisted, never logged
- Removes rate limit for that session when key is provided
- UI note: "Your key is used client-side only and never stored"
- Fallback to shared pool if key is invalid or omitted

### SDK — Python Package
- `pip install skeptai`
- Core function: `crit.analyze(output, source_model, prompt=None)`
- Returns structured JSON with score, disposition, findings array
- Each finding: title, detail, severity, module, trigger_condition
- Async support for pipeline integration
- Full documentation with examples

### SDK — JavaScript/TypeScript Package
- `npm install skeptai`
- Same interface as Python SDK
- TypeScript types for all CRIT output objects
- Browser and Node.js compatible

---

## v0.3 — PLANNED 📋
*Distribution and integration layer*

### Browser Extension (Chrome + Firefox)
- Highlight any LLM output on any page
- Right-click → "Run CRIT Analysis"
- Popup shows score, disposition, and top 3 findings
- Works on ChatGPT, Claude.ai, Gemini, Perplexity, any web interface
- Links back to full report in playground
- This is the highest-leverage distribution feature on the roadmap

### VS Code Extension
- Command palette: "CRIT: Analyze selected text"
- Inline findings displayed as diagnostics (squiggles)
- P0/P1 findings show as errors, P2/P3 as warnings
- Sidebar panel for full CRIT report
- Targeted at developers using Copilot, Cursor, or any AI coding assistant

### Self-Hosted Deployment
- Docker container with configurable model routing
- Environment variables for API keys
- No rate limits on self-hosted instances
- Deploy on any infrastructure
- Documentation for Railway, Render, and bare VPS

### Shareable Report URLs
- Every CRIT report gets a unique URL
- Share a specific analysis with a team member or client
- Reports expire after 30 days unless saved
- Foundation for the team/enterprise tier

---

## v0.4 — PLANNED 📋
*Domain module layer*

### Compliance CRIT
- Built by Daton — direct GRC expertise
- Calibrated for: vendor risk assessments, audit reports, 
  regulatory filings, policy documents, SOC 2 reports
- P0 = regulatory violation with mandatory reporting obligation
- P1 = control gap that would fail an audit finding
- Specialized lenses: Regulatory Exposure, Control Gap Hunter, 
  Audit Trail Auditor
- First domain module — sets the template for community contributions

### Contract CRIT
- Calibrated for: term sheets, NDAs, investment agreements, 
  service contracts, legal opinions
- P0 = missing clause with significant legal exposure
- Specialized lenses: Missing Clause Scanner, Liability Exposure, 
  Ambiguity Hunter
- Community contribution target — invite a lawyer to co-build

### Architecture CRIT
- Calibrated for: system design documents, API specifications, 
  technical proposals, infrastructure plans
- P0 = single point of failure or security assumption that breaks 
  the entire design
- Specialized lenses: Scalability Pressure Test, Security Assumption 
  Auditor, Dependency Fragility Scanner
- Community contribution target — invite a senior engineer to co-build

### Domain Module Marketplace
- Community-contributed modules listed in playground
- Module selector in the UI (default: General CRIT)
- Contribution pipeline documented in GitHub
- Attribution to module authors in the UI

---

## v0.5 — FUTURE 🔭
*Team and enterprise layer*

### Team Workspace
- Shared CRIT history across a team
- Saved reports with search
- Custom severity calibration per workspace
- Usage analytics — which outputs your team is running CRIT on most

### API with Authentication
- REST API with API key auth
- Rate limits by tier
- Webhook support for CI/CD pipeline integration
- Run CRIT automatically on every AI-generated output before it 
  ships to a user

### Compliance CRIT Enterprise
- White-label deployment for GRC teams
- Custom domain modules per organization
- Audit log of every analysis run
- SOC 2 compliant infrastructure
- This is the monetization path — Daton's GRC background makes 
  this the highest-credibility enterprise motion

### Feedback Loop / Fine-Tuning Pipeline
- When users accept or reject REMEDIATE output, log the signal
- Accepted remediations = positive training signal
- Rejected remediations = negative training signal
- Over time: fine-tuned critique model that gets sharper from 
  real-world usage
- This is the compounding moat that makes SkeptAI harder to 
  replicate over time

---

## Prioritization Logic

The sequencing above is deliberate:

v0.2 adds depth for existing users — gives them more control and 
opens the developer integration path with the SDK.

v0.3 is distribution — the browser extension especially is the 
highest-leverage growth feature because it puts CRIT directly 
inside every AI workflow without requiring anyone to navigate 
to skeptai.dev.

v0.4 is differentiation — domain modules are where Daton's 
background becomes an unfair advantage and where the community 
moat starts compounding.

v0.5 is monetization — the enterprise compliance tier is the 
natural revenue path given the founder's background and the 
domain module investment.

---

## Metrics To Track

As SkeptAI grows, these are the numbers that matter:

- Weekly active analyses (primary health metric)
- REJECT rate across all analyses (product quality signal — 
  if CRIT never REJECTs anything it's not being adversarial enough)
- REMEDIATE acceptance rate (action layer quality signal)
- GitHub stars (community health)
- SDK downloads (developer adoption)
- Return usage rate (are people coming back?)

---

*Last updated: March 2026 — v0.1 launch*
*Built by Daton Pope — skeptai.dev*
