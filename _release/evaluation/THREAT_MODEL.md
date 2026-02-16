# Threat Model (v0.1.0)

## Assumptions

- Adversarial or accidental file mutation is possible.
- Environmental nondeterminism is a primary failure mode.
- Trust boundaries must be explicit and enforceable.
- Artifact identity must be verifiable by hash.

## In-Scope Threats

- tampered delta bundles
- swapped base artifacts
- unauthorized file replacement
- path traversal attempts
- silent mutation without audit trail
- nondeterministic serialization (timestamps, ordering)

## Out-of-Scope Threats

- encryption or confidentiality guarantees
- network adversaries (system may run offline)
- global identity/authentication systems
- correctness of source documents

## Mitigation Style

- fail-closed validation
- hash verification at boundaries
- explicit trust policy
- deterministic logging and manifests
