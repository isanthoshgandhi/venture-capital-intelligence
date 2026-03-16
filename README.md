# Venture Capital Intelligence

> **Your complete intelligence layer for venture capital and startups.**
> Built with love & rationality for the venture capital & startup ecosystem.

A Claude plugin with **3 skills · 6 agents · 9 commands** — built from the best open-source VC tools.

Works for: **VCs · Founders · Angels · PE firms · Family offices · Accelerators**

---

## Install

```bash
claude plugin install isanthoshgandhi/venture-capital-intelligence
```

---

## How to Use

You don't need to memorize commands. Just describe what you want — Claude will activate the right tool automatically. Or use a `/command` directly if you prefer.

---

### Evaluating a startup?
**Describe it and get an 8-dimension score with a PASS / CONDITIONAL PASS / DECLINE verdict.**

> *"Here's a B2B SaaS startup I'm looking at: [description]. Should I take a meeting?"*

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
STARTUP SCREENING  ·  Acme AI  ·  Seed  ·  B2B SaaS
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

DIMENSION SCORES
  Team             8/10  [████████░░]  Ex-Stripe + Stanford ML PhD
  Market           9/10  [█████████░]  $18B TAM, 35% CAGR
  Product          7/10  [███████░░░]  Strong moat, early customers
  Traction         6/10  [██████░░░░]  $85K ARR, 20% MoM
  Business Model   8/10  [████████░░]  SaaS, 72% gross margin
  Competition      7/10  [███████░░░]  Clear wedge vs incumbents
  Financials       7/10  [███████░░░]  18 months runway
  Risk Profile     7/10  [███████░░░]  Manageable regulatory risk

  WEIGHTED SCORE   7.7/10

VERDICT:  ✅ PASS
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

- **Quick opinion (claude.ai + Claude Code):** `/venture-capital-intelligence:soft-screening-startup`
- **Reproducible score with audit trail (Claude Code only):** `/venture-capital-intelligence:hard-screening-startup`

---

### Reviewing a pitch deck?
**Share the slides and get slide-by-slide scores, red flags, and specific rewrites.**

> *"Here's our pitch deck. Be brutal — tell me what a VC would hate."*

You'll get: a score for each of the 11 slides, a list of red flags with specific fixes, and a verdict — NOT READY / NEEDS WORK / CLOSE / READY TO SEND.

- `/venture-capital-intelligence:analyze-pitch-deck`

---

### Confused by a term sheet or SAFE?
**Ask any clause in plain English and get the investor and founder perspective.**

> *"What does 'post-money SAFE with a $10M cap and 20% discount' actually mean for my ownership?"*
> *"What's a 1× non-participating liquidation preference and when does it hurt me?"*

You'll get: plain-English explanation, what it means for the investor, what it means for the founder, and when to push back.

- `/venture-capital-intelligence:explain-equity-terms`

---

### Modeling a company's financials?
**Input the numbers and get DCF valuation + SaaS metrics (LTV/CAC, burn multiple, Rule of 40).**

> *"ARR: $2M, growing 15% MoM, gross margin 72%, burn $180K/month. What's this worth?"*

You'll get: DCF valuation, revenue multiple range by stage, LTV/CAC ratio, burn multiple, Rule of 40 score, and a plain-English interpretation.

- `/venture-capital-intelligence:financial-model` *(Claude Code only)*

---

### Figuring out your cap table?
**Input your rounds and SAFEs to see exactly who owns what — and what happens at exit.**

> *"I raised a $500K SAFE at a $5M cap, then a $2M seed at $8M pre. Who owns what? What happens at a $20M exit?"*

You'll get: post-conversion ownership percentages, dilution breakdown by round, and a full waterfall showing how exit proceeds are distributed to each investor class.

- `/venture-capital-intelligence:cap-table-waterfall` *(Claude Code only)*

---

### Sizing a market?
**Describe the opportunity and get TAM/SAM/SOM with a VC viability check.**

> *"We're targeting independent restaurant owners in the US with a $99/month POS add-on. Is this venture-scale?"*

You'll get: top-down and bottom-up TAM/SAM/SOM estimates, CAGR, a VC viability flag (is TAM > $1B?), and competitive landscape context.

- `/venture-capital-intelligence:market-size` *(Claude Code only)*

---

### Sourcing deals?
**Scan any company for 6 signal types: Hiring · Funding · Product · Team · Market · Tech.**

> *"Scan Deel and tell me what signals you see — are they raising again?"*

You'll get: a scored signal report across 6 categories, a composite deal signal score, and a recommendation — MONITOR / ENGAGE / MOVE FAST.

- `/venture-capital-intelligence:deal-sourcing-signals` *(Claude Code only)*

---

### Reporting to LPs?
**Input your fund data and get TVPI, DPI, IRR, MOIC + a ready-to-send quarterly narrative.**

> *"Here's my fund data: [portfolio values, invested capital, distributions]. Write my Q1 LP update."*

You'll get: all standard fund KPIs, carried interest calculation, J-curve position, and a full draft LP narrative ready to send.

- `/venture-capital-intelligence:fund-operations` *(Claude Code only)*

---

## Two Modes — Which One Should You Use?

| | **Skill (Soft Mode)** | **Agent (Hard Mode)** |
|---|---|---|
| **Works on** | claude.ai + Claude Code | Claude Code only |
| **How it runs** | Claude reasoning, instant | Python computation + JSON audit trail |
| **Best for** | Quick opinions, exploration | Reproducible models, investment memos |
| **How to trigger** | Just describe what you want | `/venture-capital-intelligence:[command]` |

---

## What's Under the Hood

This plugin extracts the best ideas, schemas, formulas, and taxonomies from open-source VC tools — so you get institutional-grade methods without the complexity:

| What it does | Open-source it's built on |
|---|---|
| 8-dimension startup scoring | `joelparkerhenderson/startup-assessment` |
| 6-signal deal monitoring | `wizenheimer/subsignal` |
| DCF + SaaS metrics | `JerBouma/FinanceToolkit`, `halessi/DCF` |
| Cap table + waterfall | `Open-Cap-Table-Coalition/OCF` |
| Market sizing | `enthec/webappanalyzer`, `brightdata/competitive-intelligence` |
| SAFE + term sheet knowledge | `YCombinator/safe`, `jlevy/og-equity-compensation` |
| Pitch deck evaluation | `julep-ai/pitch-deck-analyzer`, `rafaecheve/Awesome-Decks` |
| Fund KPIs + LP reporting | `urbantech/musacapital` |

---

## Repository Structure

```
venture-capital-intelligence/
├── .claude-plugin/
│   ├── plugin.json
│   └── marketplace.json
├── skills/
│   ├── soft-screening-startup/SKILL.md
│   ├── analyze-pitch-deck/SKILL.md
│   └── explain-equity-terms/SKILL.md
├── agents/
│   ├── hard-screening-startup.md
│   │   └── scripts/ (verdict_calc.py, report_formatter.py)
│   ├── financial-model.md
│   │   └── scripts/ (financial_calc.py, report_formatter.py)
│   ├── market-size.md
│   │   └── scripts/ (tam_calculator.py, market_formatter.py)
│   ├── cap-table-waterfall.md
│   │   └── scripts/ (captable_calc.py, waterfall_calc.py, waterfall_formatter.py)
│   ├── deal-sourcing-signals.md
│   │   └── scripts/ (signal_scorer.py, sourcing_formatter.py)
│   └── fund-operations.md
│       └── scripts/ (fund_kpi_calc.py, fund_formatter.py)
└── README.md
```

---

## License

MIT — free to use, fork, and extend.

Built with love for the venture capital & startup ecosystem.
