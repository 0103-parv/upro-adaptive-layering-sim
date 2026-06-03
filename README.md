# UPRO Adaptive Layering Simulator

Interactive trading terminal styled web widget that simulates a 4 layer VIX driven adaptive layering strategy for UPRO (3x leveraged SPX ETF).

## Concept

UPRO compounds beautifully in calm markets but is brutal in high vol drawdowns due to volatility decay on leveraged ETFs. Naive buy and hold gets destroyed in 2008 / 2020 style events.

The sim tests whether scaling UPRO exposure by VIX regime preserves the upside while cutting tail risk.

## Layers

Four entry layers defined by VIX ranges, with corresponding UPRO drawdown ranges, capital allocation sizes, VIX rate of change thresholds, and mean reversion probability scores:

| Layer | VIX Range | UPRO Drawdown | Allocation |
|-------|-----------|----------------|------------|
| L1 | 20 to 30 | 5 to 15% | 15% |
| L2 | 30 to 40 | 15 to 28% | 25% |
| L3 | 40 to 55 | 28 to 45% | 35% |
| L4 | 55 to 80 | 45 to 60% | 25% |

A composite signal strength bar aggregates VIX level, drop magnitude, reversion score, and rate of change into a 0 to 100 signal.

## Interactive features

- Sliders for live VIX level, UPRO drop %, mean reversion signal strength, VIX 1 day rate of change
- 60 day animated simulation playback with buy signal markers
- Real time signal log showing which layers trigger and why
- Pseudocode block with syntax highlighting

## Stack

HTML, JavaScript, Chart.js (trading terminal themed)
