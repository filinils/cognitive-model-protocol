# Cognitive Model Protocol (CMP)

An experimental open protocol for explicit, evidence-based, uncertainty-aware working models of human-AI collaboration.

## For LLMs

LLMs and agentic systems should start with:

- [docs/llms.txt](docs/llms.txt)
- [docs/cmp.v0.1.md](docs/cmp.v0.1.md)
- [schema/cmp.schema.json](schema/cmp.schema.json)
- [examples/minimal-example.yaml](examples/minimal-example.yaml)
- [examples/systems-synthesist-example.yaml](examples/systems-synthesist-example.yaml)

Use CMP to model collaboration with a user, not the user's identity. Treat all model elements as hypotheses with evidence, confidence, uncertainty, and possible falsifiers.

## Problem

Large language models already build implicit working models of users. These models are currently opaque, implementation-specific, difficult to inspect, difficult to revise, non-portable, and hard to evaluate.

## Proposal

CMP is an experimental open protocol for representing explicit, evidence-based working models of human-AI collaboration.

The protocol is centered on a `collaboration_model`, not a `user_profile`. Its purpose is to represent revisable hypotheses about how collaboration between a human and an AI system may work better.

## What CMP Is

- A draft protocol for representing working models used in human-AI collaboration.
- A way to make hypotheses, evidence, uncertainty, and revision history inspectable.
- A format for comparing and improving collaboration models across implementations.
- A structure that can be challenged, corrected, exported, and revised.

## What CMP Is Not

- CMP is not a personality test.
- CMP is not a diagnosis.
- CMP is not an advertising profile.
- CMP is not a fixed identity model.
- CMP is not owned by Anchor Memory.
- CMP is not yet a standard.

Anchor Memory may become one implementation or consumer of CMP, but CMP is intended to stand alone as an open protocol.

## Design Principles

- Everything is a hypothesis.
- Evidence over labels.
- Confidence is explicit.
- Uncertainty is preserved.
- Users can inspect and challenge the model.
- Models evolve through dialogue.
- Collaboration over classification.
- Portability without extraction.

## Status

Draft 0.1.0 — seeking criticism.

The project is early. The goal is to invite critique before expanding scope or treating the format as stable.

## Documents

- [WHY_CMP.md](WHY_CMP.md) explains why CMP exists and what risks it is trying to address.
- [SPEC.md](SPEC.md) defines the 0.1.0-draft protocol concepts and fields.
- [schema/cmp.schema.json](schema/cmp.schema.json) provides a draft JSON Schema for CMP documents.
- [examples/](examples/) contains illustrative YAML examples.

## GitHub Pages

The documentation site is published from [docs/](docs/) using GitHub Pages.

If the site does not deploy automatically, GitHub Pages may need to be enabled in the repository settings with GitHub Actions selected as the source.

## Licensing

Documentation, specification text, and examples are licensed under the Creative Commons Attribution 4.0 International License (CC BY 4.0). See [LICENSE.md](LICENSE.md).

Code, JSON Schema, and schema tooling are licensed under the Apache License, Version 2.0. See [LICENSE-CODE.md](LICENSE-CODE.md).

## Citation

If you use or adapt CMP, please cite:

> Filip Nilsson. Cognitive Model Protocol. Version 0.1.0-draft.

Citation metadata is available in [CITATION.cff](CITATION.cff).
