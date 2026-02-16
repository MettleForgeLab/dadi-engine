# Query Runtime Specification (v0.1.0)

## Purpose

Provide deterministic query execution over canonical artifacts.

## Supported Operations (Minimal Subset)

- count (single collection)
- filter (exact match / equality on scalar fields)
- project (field whitelist)
- sort (single field; deterministic tie-breaker)
- limit

## Determinism Contract

Same dataset + same query → byte-identical result artifacts.

## Fail-Closed Conditions

- invalid dataset schema (or missing required fields)
- unsupported operation
- unknown keys
- malformed query
- execution error

## Outputs

- `result.json` — deterministic query output
- `report.json` — deterministic execution report (timestamps suppressed or null)
