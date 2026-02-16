# DADI-Engine Architecture

**Status:** Public Release  
**Version:** v0.1.0  
**Layer:** Deterministic execution substrate

---

## Overview

DADI-Engine is a deterministic, module-driven pipeline for compiling inputs into canonical artifacts,
supporting deterministic queries, and applying trust-governed deltas under fail-closed validation.

The core invariant:

**Same inputs + same declared toolchain + same invocation → byte-identical outputs.**

---

## System Layers (Conceptual)

┌─────────────────────────────────────────────┐
│ Trust-Governed Mutation Layer │
│ - delta bundle validation │
│ - trust policy enforcement │
│ - file-level SHA256 checks │
│ - deterministic apply logs │
└─────────────────────────────────────────────┘
▲
│
┌─────────────────────────────────────────────┐
│ Deterministic Query Runtime │
│ - validate queries │
│ - run pure-function queries │
│ - stable result.json + report.json │
└─────────────────────────────────────────────┘
▲
│
┌─────────────────────────────────────────────┐
│ Canonical Packager / Compiler │
│ - stable JSON serialization │
│ - deterministic ordering │
│ - timestamp elimination │
└─────────────────────────────────────────────┘
▲
│
┌─────────────────────────────────────────────┐
│ Pipeline Harness │
│ - staged processing with file boundaries │
│ - manifests + stage logs │
│ - fail-closed execution │
└─────────────────────────────────────────────┘
▲
│
┌─────────────────────────────────────────────┐
│ Toolchain Installer │
│ - module registry │
│ - hash verification │
│ - deterministic wiring (tools.json) │
└─────────────────────────────────────────────┘

---

## Artifact Model

Artifacts are treated as first-class objects:

- Artifacts have SHA256 identity.
- Artifacts are produced at stage boundaries.
- Artifacts can be rerun and verified.
- Mutations occur only via validated delta bundles.

---

## Determinism Boundary

Determinism is guaranteed **under a declared toolchain**:

- same frozen modules
- same wiring (`tools.json`)
- same inputs
- same invocation parameters

DADI-Engine does not claim universal determinism across arbitrary environments.

---

## Relationship to Other MFL Repositories

- DataDiddler: domain layer that can compile meaning and emit structured artifacts
- ConditionalBoundedness: switching-policy architecture (behavior regulation)
- ForgeEcosystem: constitutional/gov layer (invariants and stewardship)

DADI-Engine is substrate: it enforces artifact integrity and controlled change.
