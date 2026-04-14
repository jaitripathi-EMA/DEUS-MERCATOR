# DEUS-MERCATOR
# DEUS Trading System

A complete institutional-grade trading system built in Pine Script v6,
combining Smart Money Concepts, multi-timeframe confluence analysis,
volume profile mapping, probabilistic signal scoring, Vedic time filters,
and an astro-macro weighting model.

---

## System Overview

The DEUS system is made up of three independent but complementary indicators
that work together as a complete trading framework:

| Indicator | Role |
|-----------|------|
| MTF Confluence Dashboard | Trend identification & signal confidence scoring |
| Volume Heatmap (DPOCs & NPOCs) | High-probability price level mapping |
| DEUS Sniper Terminal | Precision entry execution |

---

## Indicator 1 — MTF Confluence Dashboard

A multi-timeframe trend analysis and signal execution dashboard that combines
Smart Money Concepts (SMC), ICT methodology, and EMA-based trend filtering
across four timeframes — outputting a single weighted confidence score and
an Ultimate Verdict.

### Timeframes Analysed & Confidence Weights

| Timeframe | Weight |
|-----------|--------|
| Daily | 11% |
| 4 Hour | 25% |
| 1 Hour | 20% |
| 5 Minute | 17% |
| FVG Signal | 19% |
| Astro Macro | 8% |
| **Total** | **100%** |

### Trend Logic & Capital Protection Mode (CPT)
The dashboard does not rely on a single methodology. It combines SMC/ICT
concepts with EMA analysis across all four timeframes. When both align,
the dashboard confirms the trend direction (Bullish / Bearish). When they
conflict, the timeframe enters **Capital Protection Mode (CPT)** — its
contribution to the confidence score is nullified, protecting capital by
preventing false signals during uncertain market conditions.

### Signal Generation
Signals are generated based on Fair Value Gap (FVG) detection with
cross-timeframe confluence confirmation, contributing 19% to the overall
confidence score.

### Astro-Macro Model (8%)
Tracks astronomical and macro cycle events known to historically influence
market sentiment. Each event is weighted positively or negatively,
contributing up to 8% to the overall confidence score. Current events and
their impact are displayed live on the dashboard with expiry dates.

### Rahu Kaal Filter
A Vedic astrology-based time filter that flags inauspicious trading windows
(Rahu Kaal periods). Currently entered manually with the upcoming window
displayed on the dashboard as a caution signal.

### Asset DNA Filter
Tracks instrument-specific macro cycles and sentiment, fed with cycle data
that evolves as time progresses. Displays the current dominant cycle signal
(e.g. "Crypto Q4/Q1 Momentum BUY") along with its expiry date. Updates
dynamically as cycles shift and new data is fed in.

### Ultimate Verdict
A single aggregated output signal that synthesises all confluence factors
into a final actionable verdict — BUY / STRONG BUY / SELL / AVOID etc.
Updates dynamically as market conditions change over time.

### Verdict Log
Timestamps every change in the Ultimate Verdict, providing a full history
of when and how the signal evolved (e.g. "BUY → STRONG BUY at 04-14 06:00").

### Shift Log
Tracks timeframe alignment changes with timestamps, logging every transition
(e.g. "Capital Protection → Bullish") so you can review how each timeframe's
bias evolved over the session.

### Display Options
- Full dashboard or compact toggle view
- Instrument mode selector: **Forex / Gold / Crypto**
- Fully customisable colours and layout

---

## Indicator 2 — Volume Heatmap (DPOCs & NPOCs)

A dynamic volume profile heatmap that identifies high-probability price
levels where institutional activity has historically concentrated.

### Key Concepts
- **DPOC (Developing Point of Control)** — The price level with the highest
  volume in the current developing profile. Displayed as a solid continuous
  line.
- **NPOC (Naked Point of Control)** — A previous POC that has never been
  revisited by price. Displayed as a broken/clustered line, acting as a
  magnet for future price action.

### Visuals
- Draws both **horizontal lines** and **shaded boxes** to mark key volume
  zones
- DPOC and NPOC are visually distinct — solid line vs broken clustered line
- All line and box colours are fully customisable from settings

### Timeframe Behaviour
The heatmap dynamically adapts to whichever timeframe is active on the
chart — no fixed timeframe lock.

---

## Indicator 3 — DEUS Sniper Terminal (CRYPTO)

A precision execution tool that waits for the highest-probability setups
before triggering an entry signal.

### Entry Conditions (All Must Align)
1. **Liquidity Sweep** — Price sweeps PDH or PDL and closes back inside
2. **Displacement** — Triggering candle is significantly larger than the
   20-bar average body (configurable multiplier)
3. **Kill-Zone Session** — London Open (07:00–10:00 UTC) or NY Open
   (12:00–15:00 UTC)
4. **Daily EMA 200 Trend Alignment** — Trade direction aligns with the
   higher timeframe trend

### Confidence Scoring
| Factor | Weight |
|--------|--------|
| Liquidity swept | +40% |
| Displacement confirmed | +20% |
| Active kill-zone | +20% |
| EMA 200 trend aligned | +20% |

**Only enter when confidence reaches 90%+ (all four factors confirmed)**

### Trade Management
- **Stop Loss** — ATR-based, placed beyond the sweep wick
- **Take Profit** — Automatic 1:3 Risk-Reward target
- **Auto-reset** after SL or TP is hit

### Settings
- Displacement Multiplier — adjust candle size sensitivity
- Kill-Zone Toggle — enable/disable session filtering

---

## How to Use the Full System

1. Open the **Volume Heatmap** — identify key DPOCs and NPOCs on your chart
2. Check the **MTF Dashboard** — confirm trend alignment across all four
   timeframes, review the Asset DNA Filter and Astro Macro conditions, and
   wait for the Ultimate Verdict to confirm direction
3. Avoid trading during **Rahu Kaal** windows flagged on the dashboard
4. Else wait for the **Sniper Terminal** to reach 90%+ confidence and trigger
   a signal near a key DPOC/NPOC level
5. Execute only when heatmap and dashboard tools agree
6. Sniper terminal is to be used independently only on crypto currencies

---

## Built With
- Pine Script v6
- TradingView

---

*Built and designed independently. All logic, structure, methodology,
and system architecture conceived and implemented by Jai Tripathi.*
