# Market Context Template

Use this before discussing any strategy.

## Minimum Context To Lock

- market stage: spot, medium-term, long-term, or mixed workflow
- bidding object: quantity, price, curve, spread, or adjustment action
- participant role: generator, load, retailer, trader, aggregator, or analyst
- target period: exact date or date range
- submission deadline: exact cutoff time for the decision
- settlement reference: what outcome later determines whether the idea worked
- operational limits: ramping, volume cap, contract obligations, neutrality or imbalance constraints
- risk objective: maximize expected return, reduce downside, stabilize execution, or diagnose failure

## Questions To Answer

1. What is being decided?
2. By what exact time must it be decided?
3. What information was available before that time?
4. What hard constraints limit the action space?
5. What benchmark or baseline should this strategy be compared against?

## Output Skeleton

```text
Market Context
- Market stage:
- Bidding object:
- Participant role:
- Target period:
- Submission deadline:
- Settlement reference:
- Operational limits:
- Risk objective:
```

If any field is missing, mark it as an assumption instead of silently filling it in.
