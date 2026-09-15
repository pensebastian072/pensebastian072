# Hi, I'm Sebastian

I build quantitative research benches and then try very hard to prove them wrong.

Most of what's here is trading and market-structure research. Almost none of it
is a strategy that works — and that's the honest headline rather than a
disclaimer. Every model on these benches is held behind the same pre-registered
gate (Probability of Backtest Overfitting < 0.5 **and** Deflated Sharpe
Ratio > 0), everything ships SHADOW until it clears, and so far nothing has
cleared it. The failures are published with their numbers attached.

If you're looking for a repo that claims a Sharpe of 3, this isn't the profile.

## Start here

**[company_lab](https://github.com/pensebastian072/company_lab)** — an S&P 500
quality and valuation ranking over SEC EDGAR XBRL plus a local judgement model.
It's the most complete piece of work here, and the interesting part is what the
experiments found:

- Three pre-registered studies say **the entry rule doesn't work**, and it has
  never been validated out of sample.
- The score turned out to be **substantially a sector bet**, so the headline
  became a sector-neutral one.
- A per-sector audit found **four silent bugs in the *measured* half** — a
  balance-sheet component dead in all eleven sectors, and revenue read as a
  *fragment* of the true figure for one company in twenty-two (a health insurer
  ranked on \$6.18bn of a true \$137.2bn). Fixing all four moved sector medians
  by about a point, which told us the gap was neither the rubric nor the data.
- Swapping the judgement model produced a **different book, not a better one** —
  37% band agreement — and the newer model cited text that wasn't in the filing
  **9.7% of the time** against 0.5% for the incumbent.

## How these are built

A few rules I keep across every repo, learned mostly by getting them wrong first:

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
| [**research_ledger**](https://github.com/pensebastian072/research_ledger) | A pre-registered answer layer over the other repos. Publishes YES / NO / NO-DATA with the number and the cause. The first run answered three questions and all three were NO. |
| [**stock_xsect_lab**](https://github.com/pensebastian072/stock_xsect_lab) | Single-stock cross-section over 1-minute US OHLCV, 1992–2026. |
| [**alpaca_gpu_lab**](https://github.com/pensebastian072/alpaca_gpu_lab) | 23-asset GPU alpha bench. Nine batteries, nine honest FAILs. |
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
| [**world_monitor_bridge**](https://github.com/pensebastian072/world_monitor_bridge) | Small probe asking whether a free OSINT event feed carries any signal. Registered before it ran, and expected to come back NO. |

---

**None of this is investment advice.** It is research code, paper and advisory
only, with no live broker path. See the `DISCLAIMER.md` in any of the trading
repos.
