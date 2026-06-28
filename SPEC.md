# CMP Draft Field Specification

Version: 0.1.0-draft  
Author: Filip Nilsson  
Project: Cognitive Model Protocol

This file describes the draft document fields used by CMP examples and the JSON Schema.

The canonical protocol definition is [reference/current.md](reference/current.md). Conceptual definitions, non-goals, ethical boundaries, and the relationship to implementations belong there.

## Root Fields

A CMP document has the following root fields:

- `protocol_version`
- `model_id`
- `subject_ref`
- `model_purpose`
- `created_at`
- `updated_at`
- `collaboration_model`
- `hypotheses`
- `interaction_patterns`
- `revision_history`
- `user_controls`

The draft JSON Schema is [schema/cmp.schema.json](schema/cmp.schema.json).

## `collaboration_model`

Required fields:

- `summary`
- `scope`
- `known_limits`

## `hypotheses[]`

Required fields:

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

`confidence` is a number between 0 and 1.

Current draft `type` values:

- `interaction_pattern`
- `constraint`
- `preference`
- `risk`
- `capability`
- `uncertainty`
- `other`

Current draft `status` values:

- `proposed`
- `active`
- `challenged`
- `revised`
- `rejected`
- `retired`

## `evidence[]`

Required fields:

- `id`
- `description`
- `source_type`
- `strength`
- `timestamp`

`strength` is a number between 0 and 1.

Current draft `source_type` values:

- `user_statement`
- `interaction_trace`
- `artifact`
- `correction`
- `evaluation`
- `external_reference`
- `other`

## `interaction_patterns[]`

Required fields:

- `id`
- `description`
- `related_hypotheses`

## `revision_history[]`

Required fields:

- `id`
- `timestamp`
- `actor`
- `description`

## `user_controls`

Required fields:

- `inspectable`
- `challengeable`
- `correctable`
- `exportable`
- `deletable`

## Examples

- [examples/minimal-example.yaml](examples/minimal-example.yaml)
- [examples/systems-synthesist-example.yaml](examples/systems-synthesist-example.yaml)
