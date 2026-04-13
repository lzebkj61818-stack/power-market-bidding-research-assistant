# Daily Report Analysis

Use this when reading daily reports, disclosures, briefings, or narrative market commentary.

## Analysis Order

1. Extract raw facts first.
2. Separate official disclosure from commentary or interpretation.
3. Mark whether each fact is backward-looking, current-state, or forward-relevant.
4. Translate the report into potential bidding implications only after the facts are stable.

## Signals To Extract

- supply changes
- demand changes
- weather, hydro, fuel, maintenance, or outage information
- interconnection or transmission constraints
- policy, rule, or settlement changes
- price or spread regime shifts
- unusual operational events

## Evidence Strength Labels

Use one of these:

- `high`: explicit official fact with clear timing
- `medium`: multiple signals point the same way, but direct causality is not proven
- `low`: descriptive commentary or single-source interpretation

## Common Mistakes

- treating commentary as if it were an official rule
- mixing realized outcomes with pre-decision information
- inferring a directional edge from a report that is mainly descriptive
- writing a confident recommendation when timing or mechanism is unclear

## Suggested Output

```text
Known Facts
- ...

Interpretation
- Signal:
- Why it matters:
- Evidence strength:

Possible Impact On Next Session
- ...

Unresolved Questions
- ...
```
