---
name: power-market-bidding-research-assistant
description: Use when Codex needs to interpret power-market daily reports, audit bidding assumptions and time-visibility rules, review backtests, compare candidate bidding strategies, or summarize risks and next-step research in spot or medium/long-term market contexts. This skill supports research and review, not final bid submission or automated execution.
---

# Power Market Bidding Research Assistant

Treat this as a research and risk-review workflow, not an auto-bidding engine.

The goal is to help the user:

- interpret market information
- audit strategy logic and data timing
- review backtest evidence
- produce candidate bidding scenarios with explicit risks

Do not replace final human judgment.

## Operating Stance

- Lock the market first: region, market type, product, target date, and submission deadline.
- Reconstruct what was knowable before the decision deadline.
- Distinguish explicit rules, observed facts, analyst assumptions, model inferences, and recommendations.
- Prefer conditional candidate strategies over one fake-certain answer.
- Use absolute dates in conclusions and comparisons.

## Establish Context First

Before discussing strategy, ask for or reconstruct:

1. market context: spot vs medium/long-term, day-ahead vs intraday, quantity vs price vs curve bidding, generator vs load perspective
2. decision clock: when the bid must be submitted, and what data was visible before that time
3. objective: directional judgment, sizing, anomaly diagnosis, post-mortem review, or daily report interpretation
4. constraints: policy bounds, market rules, operational limits, exposure limits, neutrality requirements, adjustment granularity
5. evidence sources: official notices, market reports, disclosures, model outputs, backtest tables, analyst notes

If the user does not provide enough context, say what assumptions you are making and how they could change the conclusion.

## Workflow

1. Lock scope and dates before discussing strategy.
2. Audit data visibility and rule consistency before discussing performance.
3. Interpret reports into signals, regime shifts, and uncertainty, not just bullet summaries.
4. Review candidate strategies as scenario outputs:
   - base case
   - supporting evidence
   - invalidation conditions
   - operational risks
5. When backtests are provided, inspect:
   - covered date range
   - whether the window is complete or partial
   - signal timestamp vs realized label timestamp
   - benchmark or baseline
   - action mapping from model output to bidding behavior
   - breakdown by regime, hour, season, or market condition
6. End with what is actionable now, what remains uncertain, and what still needs human judgment.

## References

Load these only when relevant:

- `references/market-context-template.md`: when the market setup, participant role, or decision clock is still unclear
- `references/daily-report-analysis.md`: when interpreting daily reports, disclosures, notices, or narrative market commentary
- `references/backtest-review-checklist.md`: when reviewing backtests, validation windows, or strategy evaluation claims
- `references/strategy-risk-checklist.md`: when converting research into candidate bidding scenarios with explicit operational risks
- `references/output-templates.md`: when the user needs a stable output shape for review notes or candidate strategy memos
- `references/privacy-and-sanitization.md`: when any result, example, or documentation may be published, shared externally, or copied into a public repository

## Task Patterns

### Daily Report Interpretation

Extract and organize:

- supply-demand changes
- price or spread regime shifts
- rule or policy changes
- relevant fuel, hydro, weather, interprovincial, or operational context
- signals that may affect the next bidding session

Do not overstate weak evidence. If a report is descriptive but not predictive, say so.

### Strategy Audit

Check for:

- hidden future information
- inconsistent business clock
- action mapping drift between research and execution
- thresholds that have no market explanation
- missing fail-fast checks for incomplete inputs
- conclusions that ignore operational or exposure constraints

### Backtest Review

Require:

- exact covered dates
- signal generation timestamp
- label timestamp
- benchmark or baseline
- explicit statement of how research output becomes bidding action
- segmentation, not only overall averages

Flag:

- performance driven by a narrow period
- stable averages with unstable direction or sizing behavior
- silent dropping of hard cases or missing data
- calibration drift masked by aggregate metrics

### Candidate Strategy Synthesis

When the user asks for a strategy view:

- provide 2-3 candidate approaches if uncertainty is material
- express sizing as a candidate range or conditional adjustment, not fake precision
- include trigger conditions, invalidation conditions, and main risks
- state what additional data or rule clarification would most change the recommendation

## Output Requirements

Use these sections when useful:

- `Market Context`
- `Known Facts`
- `Assumptions`
- `Interpretation`
- `Candidate Strategy`
- `Key Risks`
- `Data or Rule Gaps`
- `Next Checks`

Keep these distinctions explicit:

- observed fact
- inference from evidence
- recommendation
- unresolved uncertainty

## Guardrails

- Do not present the final bidding recommendation as certain when the market clock or rules are unclear.
- Do not assume all regions, products, or market stages follow the same disclosure and settlement logic.
- Do not turn a model score directly into a bidding instruction without an explicit action mapping.
- Do not hide missing data, partial windows, or unresolved assumptions.
- If critical inputs are missing, say what cannot be concluded.
- If material may be published or shared externally, scrub credentials, source-system names, region identifiers, private file paths, database/table names, raw samples, and proprietary thresholds.
- Prefer generalized placeholders such as `region_x`, `source_a`, `entity_y`, and `YYYY-MM-DD` in public-facing artifacts.

## Useful Prompt Patterns

- `Use $power-market-bidding-research-assistant to review this market daily report and extract signals relevant to the next bidding session.`
- `Use $power-market-bidding-research-assistant to audit whether this strategy relies on data that would not have been visible before submission time.`
- `Use $power-market-bidding-research-assistant to review this backtest and tell me whether the claimed edge is robust enough for research follow-up.`
- `Use $power-market-bidding-research-assistant to turn these model outputs into 2 candidate bidding scenarios with assumptions and risks.`
