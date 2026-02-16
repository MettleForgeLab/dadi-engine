# DADI-Engine Specifications — Overview

**Status:** Public Release  
**Version:** v0.1.0

This directory contains operational specifications for the DADI-Engine architecture.

The specifications define:

- deterministic toolchain resolution
- staged pipeline execution
- canonical packaging rules
- deterministic query behavior
- trust-governed delta mutation

All specifications are written to support:

- auditability
- fail-closed validation
- byte-stable outputs under a declared toolchain

See:

- `TOOLCHAIN_SPEC.md`
- `PIPELINE_HARNESS_SPEC.md`
- `QUERY_RUNTIME_SPEC.md`
- `DELTA_MERGE_SPEC.md`
