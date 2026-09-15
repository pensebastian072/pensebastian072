# Hi, I'm Sebastian

I'm a self-directed developer and quantitative-research enthusiast focused on
finance, macroeconomics, market structure, and data-driven decision tools. From
home, I build practical research systems that combine financial data
engineering, statistical testing, machine learning, local AI tooling, and clear
operational safeguards.

These repositories document hands-on work in Python, GPU computing, financial
data pipelines, research design, dashboards, and automation. Each project uses
pre-defined evaluation criteria, reproducible experiments, and transparent
results so that the next decision is guided by evidence rather than hindsight.

## Start here

**[company_lab](https://github.com/pensebastian072/company_lab)** is an S&P 500
quality and valuation research platform built on SEC EDGAR XBRL data and a local
judgement model. It is the most complete project here, with nine
pre-registered evaluation runs that examine the methodology from multiple
angles:

- The entry methodology has been tested under nine documented conditions, with
  results used to define appropriate decision boundaries and future research.
- Sector analysis led to a sector-neutral headline score and more precise
  comparisons across companies.
- A detailed field-level audit improved data quality by identifying and fixing
  four silent measurement issues across the scorecard.
- Controlled model comparisons quantify how different judgement models affect
  rankings, citations, and coverage, creating a stronger foundation for future
  model selection.

## Research approach

A few principles I apply across every project:

- **Assert the inputs before interpreting any score.** Every real defect I've
  found was in the *measured* half and silent — a flow proxy permanently reading
  zero, a volatility term ratio quietly comparing two different dates for five
  weeks, the revenue fragment above. A range and null-rate sweep over every field
  catches all of those; a good-looking backtest doesn't.
- **One variable per arm**, and the confound gets named in the same breath as the
  headline number.
- **No verdict from one example or one pooled number.** Same-date entries are one
  cluster, not *n* independent observations.
- **Pre-register the search before running it.** Sign-flipping a discovered
  effect to harvest it is p-hacking with extra steps.
- **Nothing model-shaped goes on a decision hot path.** Models communicate
  through flag files that fail safe to neutral when missing, stale or corrupt.
- **Safety controls live in a process that runs before the call and defaults to
  no** — not in a config file the agent can read.

## Research benches

| | |
|---|---|
| [**research_ledger**](https://github.com/pensebastian072/research_ledger) | A structured, pre-registered research ledger that records conclusions, supporting metrics, and data availability across the project portfolio. |
| [**stock_xsect_lab**](https://github.com/pensebastian072/stock_xsect_lab) | Single-stock cross-section over 1-minute US OHLCV, 1992–2026. |
| [**alpaca_gpu_lab**](https://github.com/pensebastian072/alpaca_gpu_lab) | A GPU-accelerated alpha-research framework covering 23 assets and nine documented evaluation batteries. |
| [**qlib_lab**](https://github.com/pensebastian072/qlib_lab) | Microsoft Qlib walk-forward bench behind the canonical gate. |
| [**macro_gpu_lab**](https://github.com/pensebastian072/macro_gpu_lab) | CUDA bench over a macro feature brain. |
| [**futures_intelligence**](https://github.com/pensebastian072/futures_intelligence) | Point-in-time ES futures-curve engine. Research-only by construction — no broker, account, position, or order code exists in it. |

## Engines and desks

| | |
|---|---|
| [**confluence_trader**](https://github.com/pensebastian072/confluence_trader) | Multi-timeframe confluence engine across seven signal families. The decision brain only; broker integration deliberately out of scope. |
| [**options_desk_public**](https://github.com/pensebastian072/options_desk_public) | Sanitized mirror of a pre-open advisory options desk. |
| [**copper_brain**](https://github.com/pensebastian072/copper_brain) | Advisory copper regime model, weekly, flag-file output. |
| [**fx_hermes_trader**](https://github.com/pensebastian072/fx_hermes_trader) | Paper-only FX harness with an LLM supervisor kept off the hot path. |

## Tooling

| | |
|---|---|
| [**research_rag**](https://github.com/pensebastian072/research_rag) | Fully local RAG over a personal research library. Ollama embeddings, SQLite vector store, citation-carrying answers, no cloud calls and no API keys. |
| [**skill_forge**](https://github.com/pensebastian072/skill_forge) | Mines my own coding-agent session transcripts for evidence that a skill needs work, then writes a **proposed** edit. Propose-only by design — it never edits a skill itself. |
| [**world_monitor_bridge**](https://github.com/pensebastian072/world_monitor_bridge) | An OSINT event-data feasibility study for evaluating cross-asset market context. |

---

**None of this is investment advice.** It is research code, paper and advisory
only, with no live broker path. See the `DISCLAIMER.md` in any of the trading
repos.
