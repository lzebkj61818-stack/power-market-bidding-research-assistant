# Privacy And Sanitization

Use this before publishing the skill, sharing examples externally, or copying outputs into public documents.

## Never Publish These

- database URLs, usernames, passwords, tokens, cookies, private keys
- hostnames, internal domains, server names, VPN addresses
- internal system names, project codenames, source-system names
- raw table names, schema names, field names, SQL text tied to private systems
- raw market data files, screenshots, dashboards, exports, or production outputs
- file paths that reveal user names, machine names, or internal directory structure
- region-specific or entity-specific identifiers when they can reveal proprietary positioning
- thresholds, heuristics, or rule variants that are not meant to be public

## Rewrite Rules

Replace sensitive content with neutral placeholders:

- region or market area -> `region_x`
- company or participant -> `entity_y`
- data source -> `source_a`
- internal table -> `table_feature_hourly`
- exact path -> `data/...` or `outputs/...`
- live date tied to production workflow -> `YYYY-MM-DD`

When a sensitive value does not matter for understanding, remove it instead of masking it.

## Safe Example Policy

- use toy examples, not production extracts
- use generic column names when exact names are private
- summarize patterns instead of quoting raw rows
- avoid screenshots from real systems
- avoid examples that can be joined back to known public events

## Release Checklist

1. Search for `password`, `token`, `secret`, `key`, `mysql`, `postgres`, `mongodb`, `jdbc`, `host`, `server`.
2. Search for real region names, organization names, and system names.
3. Search for raw paths such as `C:\`, `/home/`, `/Users/`, network shares, or mounted drives.
4. Confirm there are no `.csv`, `.xlsx`, `.parquet`, `.db`, or notebook outputs with real data.
5. Confirm all examples are illustrative and all identifiers are generic.

## Decision Rule

If you are unsure whether a term is sensitive, generalize it.
