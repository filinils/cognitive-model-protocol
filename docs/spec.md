# CMP Specification

Version: **0.1.0-draft**

CMP defines a draft data model for explicit, evidence-based, uncertainty-aware working models of human-AI collaboration.

The protocol represents a `collaboration_model`, not a `user_profile`.

## Root Object

A CMP document includes:

- `protocol_version`
- `model_id`
- `subject_ref`
- `model_purpose`
- `created_at`
- `updated_at`
- `collaboration_model`
- `hypotheses`
- `interaction_patterns`
- `matching_signals`
- `complementarity_signals`
- `revision_history`
- `user_controls`

## Hypotheses

Each hypothesis must include:

- `id`
- `statement`
- `type`
- `evidence`
- `confidence`
- `uncertainty`
- `falsifiers`
- `status`
- `created_at`
- `updated_at`

Hypotheses should remain provisional, falsifiable, and open to user correction.

## Evidence

Each evidence record must include:

- `id`
- `description`
- `source_type`
- `strength`
- `timestamp`

Evidence should explain why a hypothesis exists. It may come from user statements, interaction traces, artifacts, corrections, evaluations, implementation traces, or other sources.

## User Control

CMP implementations should support inspection, challenge, correction, export, deletion, and revision history.

## Ethical Boundaries

CMP should not be used for covert advertising profiles, diagnosis-like classifications, hidden risk scores, or fixed identity claims.

For the full draft specification, see the repository [SPEC.md](https://github.com/filinils/cognitive-model-protocol/blob/main/SPEC.md). The draft JSON Schema is available at [schema/cmp.schema.json](https://github.com/filinils/cognitive-model-protocol/blob/main/schema/cmp.schema.json).
