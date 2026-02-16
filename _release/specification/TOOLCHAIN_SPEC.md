# Toolchain Installer Specification (v0.1.0)

## Purpose

Define a deterministic module registry and wiring mechanism.

## Required Properties

- Modules are pinned by hash (SHA256).
- Entry points are resolved deterministically.
- A wiring file (e.g., `tools.json`) maps stage names to executable entry points.
- Missing or unverifiable modules must fail closed.

## Fail-Closed Conditions

- required stage has no resolved entry point
- module hash mismatch
- missing required manifest fields
- unknown stage keys in wiring

## Notes

Signing may be layered externally; v0.1.0 assumes hash verification and explicit provenance control.
