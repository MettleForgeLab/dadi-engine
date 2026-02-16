# Pipeline Harness Specification (v0.1.0)

## Purpose

Run a declared sequence of stage tools against an input directory and produce canonical artifacts.

## Core Properties

- Stages run in strict order.
- Each stage consumes explicit file inputs and emits explicit file outputs.
- Stage boundaries produce artifacts suitable for hashing and audit.
- Harness produces a run manifest and stage status log.

## Determinism Contract

Given:

- identical inputs
- identical toolchain (modules + wiring)
- identical invocation parameters

Then:

- resulting compiled artifacts are byte-identical.

## Fail-Closed Conditions

- missing required input artifact for a stage
- non-zero stage exit code
- missing required output artifact
- unresolved wiring for required stage

## Optional Stages

Some stages may be optional if explicitly disabled or if required inputs are absent by design.
Optionality must be explicit; ambiguity must fail closed.
