# Changelog

All notable changes to Venture Capital Intelligence are documented here.

---

## [1.0.0] — 2026-03-16

### Initial Release

**3 Skills (claude.ai + Claude Code)**

- **`soft-screening-startup`** — Startup screening with 8-dimension scorecard (team, market, product, traction, business model, competition, financials, risk), 4 investor lenses (Sequoia, YC, Tiger Global, Risk Management), weighted scoring, and 1-page investment memo output. Stage-calibrated benchmarks for Pre-Seed through Series B+.

- **`analyze-pitch-deck`** — Slide-by-slide pitch deck analysis against the 11-slide winning structure. Detects 10 common red flags, benchmarks against famous decks (Airbnb, Uber, LinkedIn, Dropbox, Facebook), generates specific rewrite suggestions for lowest-scoring slides. Outputs an investor readiness rating.

- **`explain-equity-terms`** — Plain-English explanations of any equity term, clause, or document. Covers: SAFE variants (post-money, pre-money, MFN, pro-rata), convertible notes, priced rounds (Series Seed documents), liquidation preferences, anti-dilution provisions, pro-rata rights, drag-along, employee equity (ISO/NSO/RSU/vesting/83(b)), and fund terms (carry, hurdle, waterfall).

**6 Agents (Claude Code only, Python 3.x)**

- **`hard-screening-startup`** — Deterministic startup screening with Python-computed weighted scores, JSON audit trail, and reproducible verdict. Produces `company_profile.json` + `verdict_output.json` for record-keeping.

- **`financial-model`** — Three-method valuation: DCF intrinsic value (5-year projections with terminal value), revenue multiple (stage-calibrated ARR multiples), and SaaS health metrics (LTV/CAC, CAC payback, burn multiple, NRR, Rule of 40, runway). Stage benchmarks embedded for Seed through Series B.

- **`market-size`** — TAM/SAM/SOM computed using both top-down (industry report fractions) and bottom-up (unit count × ARPU) methods. Competitive landscape mapping with tech stack classification using webappanalyzer taxonomy. VC rule check: TAM > $1B flag.

- **`cap-table-waterfall`** — SAFE conversion math (post-money SAFE, cap vs discount method), round-by-round dilution modeling, and exit waterfall under multiple scenarios. Uses OCF (Open Cap Format) JSON schema — the industry standard backed by Carta, Cooley, and NVCA. Supports participating and non-participating preferred.

- **`deal-sourcing-signals`** — 6-dimension signal scan using subsignal taxonomy: Hiring · Funding · Product · Team · Market · Tech. Exponential scoring per signal type, investment readiness classification (MONITOR / ENGAGE / MOVE FAST), and sourcing brief output.

- **`fund-operations`** — Fund KPI computation: TVPI, DPI, RVPI, IRR (Newton-Raphson XIRR), MOIC per company and fund-level. European waterfall carried interest calculation (return capital → preferred return → carry catch-up → 80/20 split). Management fee projection. J-curve position assessment. LP quarterly narrative generation.

**9 Commands**

`/soft-screening-startup` · `/analyze-pitch-deck` · `/explain-equity-terms` · `/hard-screening-startup` · `/financial-model` · `/market-size` · `/cap-table-waterfall` · `/deal-sourcing-signals` · `/fund-operations`

**Open-Source Tools Incorporated**

Built by extracting and embedding the best ideas from: `joelparkerhenderson/startup-assessment` (8-dimension rubric), `virattt/ai-hedge-fund` (multi-investor lens approach), `wizenheimer/subsignal` (signal taxonomy), `JerBouma/FinanceToolkit` (financial formulas), `halessi/DCF` (DCF methodology), `groveco/cohort-analysis` (LTV curves), `Open-Cap-Table-Coalition/OCF` (cap table schema), `foresighthq/cap-table-tool` (waterfall logic), `enthec/webappanalyzer` (tech stack taxonomy), `YCombinator/safe` (SAFE variants), `seriesseed/equity` (priced round documents), `jlevy/og-equity-compensation` (equity comp guide), `julep-ai/pitch-deck-analyzer` (red flag taxonomy), `joelparkerhenderson/pitch-deck` (slide structure), `rafaecheve/Awesome-Decks` (benchmark decks), `urbantech/musacapital` (fund manager tools), `simonmichael/hledger` (accounting taxonomy).
