# Venture Capital Intelligence

> **The intelligence layer for anyone making or raising capital.**

A Claude plugin with **3 skills · 6 agents · 9 commands** built from the best open-source VC tools. Screen startups, analyze pitch decks, explain equity terms, model financials, compute cap table waterfalls, size markets, scan deal signals, and generate LP fund reports.

Works for VCs, founders, angels, PE firms, and family offices.

---

## Install

```bash
claude plugin install isanthoshgandhi/venture-capital-intelligence
```

---

## Two Modes

| Mode | How to invoke | Works on | What it does |
|------|--------------|----------|-------------|
| **Skill** (soft) | Describe a company or ask a question | claude.ai + Claude Code | Claude reasoning, instant response |
| **Agent** (hard) | `/venture-capital-intelligence:[command]` | Claude Code only | Python computation + audit trail |

---

## Skills — Works on claude.ai + Claude Code

| Skill | Command | Triggers automatically when you... |
|-------|---------|-------------------------------------|
| **Soft Screening** | `/venture-capital-intelligence:soft-screening-startup` | Describe a startup and ask for an opinion |
| **Deck Analysis** | `/venture-capital-intelligence:analyze-pitch-deck` | Share a pitch deck and ask for feedback |
| **Equity Terms** | `/venture-capital-intelligence:explain-equity-terms` | Ask about a SAFE, term sheet, or equity clause |

### Startup Screen Output (soft mode)
```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
STARTUP SCREEN  ·  Acme AI  ·  Seed  ·  B2B SaaS
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

---

## Agents — Claude Code Only

| Agent | Command | What it computes |
|-------|---------|-----------------|
| **Hard Screen** | `/venture-capital-intelligence:hard-screen-startup` | Deterministic weighted scoring with JSON audit trail |
| **Financial Model** | `/venture-capital-intelligence:financial-model` | DCF + revenue multiples + SaaS metrics (LTV/CAC, burn multiple, Rule of 40) |
| **Market Size** | `/venture-capital-intelligence:market-size` | TAM/SAM/SOM top-down + bottom-up, competitive landscape, tech stack analysis |
| **Cap Table** | `/venture-capital-intelligence:cap-table-waterfall` | SAFE conversion math, dilution simulation, exit waterfall (OCF standard) |
| **Deal Signals** | `/venture-capital-intelligence:deal-sourcing-signals` | 6-signal scan: Hiring · Funding · Product · Team · Market · Tech |
| **Fund Operations** | `/venture-capital-intelligence:fund-operations` | TVPI · DPI · IRR · MOIC · carry calculation · LP quarterly narrative |

---

## What's Inside

### Open-Source Foundations

This plugin is built by extracting the best ideas, schemas, formulas, and taxonomies from these open-source tools:

| Category | Tools Used | What Was Extracted |
|----------|-----------|-------------------|
| Startup Scoring | `joelparkerhenderson/startup-assessment`, `virattt/ai-hedge-fund` | 8-dimension rubric, multi-investor lens (Buffett/Wood/Risk/Technical) |
| Signal Monitoring | `wizenheimer/subsignal` | 6-signal taxonomy: Hiring/Funding/Product/Team/Market/Tech |
| Financial Modeling | `JerBouma/FinanceToolkit`, `halessi/DCF`, `groveco/cohort-analysis` | DCF formulas, SaaS metrics, cohort/LTV curves |
| Cap Table | `Open-Cap-Table-Coalition/OCF`, `foresighthq/cap-table-tool` | OCF JSON schema, SAFE conversion math, waterfall logic |
| Market Research | `enthec/webappanalyzer`, `brightdata/competitive-intelligence` | Tech stack taxonomy, competitive intel agent pattern |
| Legal/Equity | `YCombinator/safe`, `seriesseed/equity`, `jlevy/og-equity-compensation` | SAFE variants, Series Seed docs, ISO/NSO/vesting guide |
| Pitch Decks | `julep-ai/pitch-deck-analyzer`, `joelparkerhenderson/pitch-deck`, `rafaecheve/Awesome-Decks` | Red flag taxonomy, 11-slide structure, real deck benchmarks |
| Fund Ops | `urbantech/musacapital`, `simonmichael/hledger` | LP KPI taxonomy, chart of accounts structure |

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
│   ├── hard-screen-startup.md
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

## Who This Is For

| User | Primary use cases |
|------|------------------|
| **VC Analyst** | Screen 50 startups/week with `/soft-screening-startup`, run hard models on top candidates |
| **VC Partner** | Quick deck reviews with `/analyze-pitch-deck`, fund performance with `/fund-operations` |
| **Founder** | "Is my deck ready?" with `/analyze-pitch-deck`, "What am I signing?" with `/explain-equity-terms` |
| **Angel Investor** | Fast startup screen + cap table scenarios before writing a check |
| **PE Analyst** | Financial modeling + market sizing for deal evaluation |
| **Accelerator** | Batch screen 100 demo day companies using the soft screening skill |

---

## License

MIT — free to use, fork, and extend.

Built with love for the startup ecosystem.
