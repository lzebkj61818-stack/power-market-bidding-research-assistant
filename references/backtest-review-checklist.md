# Backtest Review Checklist

Use this when reviewing research claims, validation results, or strategy backtests.

## Mandatory Checks

- exact covered dates
- whether the test window is complete or partial
- signal timestamp
- label timestamp
- benchmark or baseline
- data availability assumptions
- action mapping from model output to bidding behavior
- missing-data handling
- segmentation by regime, hour, season, or market condition

## Leakage And Timing Questions

- Could any feature have been known only after the decision deadline?
- Does the backtest use revised or finalized data that would not have been visible live?
- Are labels or actuals shifted correctly, or only renamed to look correct?
- Are samples dropped in a way that removes hard cases?

## Robustness Questions

- Is performance concentrated in a short period?
- Does average performance hide unstable direction or sizing behavior?
- Does the result survive when reviewed by regime or stress period?
- Is the claimed edge still meaningful after operational constraints?

## Output Skeleton

```text
Backtest Scope
- Covered dates:
- Window completeness:
- Baseline:

Method Risks
- ...

Observed Strengths
- ...

Observed Weaknesses
- ...

Decision
- Research follow-up warranted / not warranted
- Why:
```
