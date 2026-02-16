# Delta Merge Specification (v0.1.0)

## Purpose

Apply controlled change to artifact sets using explicit delta bundles under trust policy.

## Allowed Operations (v0.1.0 conceptual set)

- add_file
- replace_file (requires expected_old_sha256)
- delete_file (requires expected_old_sha256)
- noop

## Trust Policy Requirements

A trust policy must explicitly define:

- allowed authors
- allowed path prefixes
- allowed operations
- size limits (per-delta and total)

## Integrity Requirements

- content hash must match declared sha256
- replace/delete must verify expected_old_sha256 before action
- path traversal must be rejected
- apply must be logged deterministically
- base input must not be mutated in place (write to `--out`)

## Fail-Closed Conditions

- schema violations
- trust policy violations
- hash mismatch
- unsafe paths
- unknown keys
