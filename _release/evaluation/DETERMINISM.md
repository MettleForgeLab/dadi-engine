# Determinism Contract (v0.1.0)

## Claim

DADI-Engine produces byte-identical outputs under a declared toolchain.

## Declared Toolchain

Determinism is defined relative to:

- pinned module artifacts (hashes)
- deterministic wiring (tools.json)
- identical invocation parameters
- identical inputs

## Evidence Standard

A determinism claim is satisfied when:

- two independent runs produce identical SHA256 for canonical outputs
- run manifests show identical module wiring and inputs
- timestamps or environmental entropy are absent from canonical artifacts

## What This Does Not Claim

- universal determinism across arbitrary environments
- correctness of source data
- cryptographic security against all adversaries
