# Venture Capital Intelligence

> **Your complete intelligence layer for venture capital and startups.**
> Built with love & rationality for the venture capital & startup ecosystem.

A Claude plugin with **9 skills** — built from the best open-source VC tools.

Works for: **VCs · Founders · Angels · PE firms · Family offices · Accelerators**

**Author:** Santhosh Gandhi · **Version:** 1.0.0

---

## Try Asking

No commands needed. Just describe what you want — Claude activates the right tool automatically.

```
■ Should I take a meeting with this B2B SaaS startup? [description]
■ What does this term sheet clause actually mean for my ownership?
■ Is the robotics market venture-scale? Give me TAM/SAM/SOM.
■ Run a hard screen on Zepto — Series D, B2C quick commerce, India.
■ ARR: $2M, 15% MoM growth, 72% gross margin. What's this worth?
■ I raised a $500K SAFE at $5M cap, then $2M seed at $8M pre. Who owns what at a $20M exit?
■ Scan Deel — are they raising again? What signals do you see?
■ Write my Q1 LP update. Here's my fund data: [values]
```

---

## Install on Claude Code

```bash
# Step 1 — Add the marketplace (one-time setup)
claude plugin marketplace add isanthoshgandhi/venture-capital-intelligence

# Step 2 — Install the plugin
claude plugin install venture-capital-intelligence
```

Then just describe what you want — the right skill activates automatically.

---

## How to Use

Two ways to trigger any skill:
1. **Describe it** — Claude auto-activates the right skill from your intent
2. **Explicit command** — type `/venture-capital-intelligence:[skill-name]` directly

---

## All Skills — Quick Reference

> 🟢 **Claude Only** = works on claude.ai + Claude Code, instant reasoning
> 🔵 **Claude + Python** = Claude Code only, runs Python scripts, deterministic output with JSON audit trail

| # | Skill | Explicit Command | What to Pass | Runs On |
|---|---|---|---|---|
| 1 | Soft Startup Screen | `/venture-capital-intelligence:soft-screening-startup` | Company name, stage, sector, 2–3 sentence description | 🟢 Claude Only |
| 2 | Analyze Pitch Deck | `/venture-capital-intelligence:analyze-pitch-deck` | Paste deck text or describe each slide | 🟢 Claude Only |
| 3 | Explain Equity Terms | `/venture-capital-intelligence:explain-equity-terms` | Paste clause, term, or ask any SAFE/term sheet question | 🟢 Claude Only |
| 4 | Hard Startup Screen | `/venture-capital-intelligence:hard-screening-startup` | Company name, stage, sector, traction numbers, team background | 🔵 Claude + Python |
| 5 | Financial Model | `/venture-capital-intelligence:financial-model` | ARR, MoM growth %, gross margin %, burn/month, stage | 🔵 Claude + Python |
| 6 | Market Size | `/venture-capital-intelligence:market-size` | Target customer, geography, product/price point, sector | 🔵 Claude + Python |
| 7 | Cap Table Waterfall | `/venture-capital-intelligence:cap-table-waterfall` | SAFE amounts + caps, round sizes + pre-money, exit amount | 🔵 Claude + Python |
| 8 | Deal Sourcing Signals | `/venture-capital-intelligence:deal-sourcing-signals` | Company name (Claude searches the web for signals) | 🔵 Claude + Python |
| 9 | Fund Operations | `/venture-capital-intelligence:fund-operations` | Invested capital, portfolio values, distributions, fund size | 🔵 Claude + Python |

---

## Input Examples — Copy & Paste Ready

### 1 — Soft Startup Screen 🟢
```
/venture-capital-intelligence:soft-screening-startup
Company: Acme AI — Seed stage, B2B SaaS, AI-powered contract review.
Team: Ex-Stripe CTO + Stanford NLP PhD. ARR: $85K, 20% MoM. Should I take a meeting?
```

### 2 — Analyze Pitch Deck 🟢
```
/venture-capital-intelligence:analyze-pitch-deck
Here's our deck: [paste slide-by-slide content]. Be brutal — what would a VC hate?
```

### 3 — Explain Equity Terms 🟢
```
/venture-capital-intelligence:explain-equity-terms
What does "post-money SAFE with a $10M cap and 20% discount" mean for my ownership?
```

### 4 — Hard Startup Screen 🔵
```
/venture-capital-intelligence:hard-screening-startup
Company: Zepto — Series D, B2C quick commerce, India. GMV: $1B, 60% YoY growth.
Team: IIT Delhi founders, ex-Flipkart ops lead. Competing with Blinkit, Swiggy Instamart.
```

### 5 — Financial Model 🔵
```
/venture-capital-intelligence:financial-model
ARR: $2M, MoM growth: 15%, Gross margin: 72%, Burn: $180K/month, Stage: Series A.
CAC: $1,200, LTV: $8,400, Churn: 1.5%/month.
```

### 6 — Market Size 🔵
```
/venture-capital-intelligence:market-size
Target: Independent restaurant owners in the US. Product: $99/month POS add-on.
Is this venture-scale? Give me TAM/SAM/SOM.
```

### 7 — Cap Table Waterfall 🔵
```
/venture-capital-intelligence:cap-table-waterfall
Round 1: $500K SAFE at $5M post-money cap.
Round 2: $2M Seed at $8M pre-money, 20% option pool.
Exit: $20M acquisition. Who gets what?
```

### 8 — Deal Sourcing Signals 🔵
```
/venture-capital-intelligence:deal-sourcing-signals
Company: Deel. Scan for all 6 signal types — are they raising again?
```

### 9 — Fund Operations 🔵
```
/venture-capital-intelligence:fund-operations
Fund size: $50M, Invested: $32M across 12 companies.
Portfolio FMV: $61M, Distributions: $4M, Management fees paid: $3M.
Write my Q1 LP update.
```

---

## Output Example — Startup Screening

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

---

## What's Inside

### Inspired From

This plugin is built on the best ideas, schemas, formulas, and taxonomies from the open-source VC ecosystem:

| Category | Inspired From | Learnings |
|----------|--------------|-----------|
| Startup Scoring | `joelparkerhenderson/startup-assessment`, `virattt/ai-hedge-fund` | 8-dimension rubric, multi-investor lens (Sequoia/YC/Tiger Global/Risk) |
| Signal Monitoring | `wizenheimer/subsignal` | 6-signal taxonomy: Hiring · Funding · Product · Team · Market · Tech |
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
│   ├── explain-equity-terms/SKILL.md
│   ├── hard-screening-startup/
│   │   ├── SKILL.md
│   │   └── scripts/ (verdict_calc.py, report_formatter.py)
│   ├── financial-model/
│   │   ├── SKILL.md
│   │   └── scripts/ (financial_calc.py, report_formatter.py)
│   ├── market-size/
│   │   ├── SKILL.md
│   │   └── scripts/ (tam_calculator.py, market_formatter.py)
│   ├── cap-table-waterfall/
│   │   ├── SKILL.md
│   │   └── scripts/ (captable_calc.py, waterfall_calc.py, waterfall_formatter.py)
│   ├── deal-sourcing-signals/
│   │   ├── SKILL.md
│   │   └── scripts/ (signal_scorer.py, sourcing_formatter.py)
│   └── fund-operations/
│       ├── SKILL.md
│       └── scripts/ (fund_kpi_calc.py, fund_formatter.py)
└── README.md
```

---

## License

MIT — free to use, fork, and extend.

Built with love for the venture capital & startup ecosystem.
