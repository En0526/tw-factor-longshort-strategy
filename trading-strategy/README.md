# Trading Strategy

Simple thesis-driven multi-factor framework for Taiwan equities.

## What this project does

- Uses financial-report factors to score stocks.
- Rebalances monthly with a long/short portfolio.
- Default setup is market-neutral style: long top `N`, short bottom `N` (e.g., `5/5`).
- Supports model comparison (EW, Random Forest, Lasso, GBM).

## Core idea

1. Prepare factor data and next-period returns.
2. Score/rank stocks each rebalance date.
3. Build long/short positions and apply transaction-cost assumptions.
4. Track net value and risk metrics over time.

## Quick start

```bash
cd trading-strategy
pip install -r requirements.txt
```

Then adjust parameters in `src/config.py` (capital, top/bottom N, costs, rebalance frequency) and run the strategy pipeline.

## Project layout

- `src/data/`: load and preprocess input data
- `src/models/`: scoring/model logic
- `src/strategy/`: signal and portfolio construction
- `src/utils/`: helper functions
- `tests/`: basic tests for data/model/strategy modules

## Output (expected)

- Monthly positions (long/short holdings)
- Backtest performance series
- Summary metrics (return, volatility, Sharpe, max drawdown, win rate)