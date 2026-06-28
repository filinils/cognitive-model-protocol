# Quickstart

This page shows how to create a minimal CMP collaboration model.

## 1. Set the Protocol Metadata

Start with a stable model ID, purpose, timestamps, and a privacy-preserving subject reference.

```yaml
protocol_version: 0.1.0-draft
model_id: cmp-example-minimal
subject_ref: local-user-001
model_purpose: Explore a small collaboration model for drafting and revision.
created_at: "2026-06-28T00:00:00Z"
updated_at: "2026-06-28T00:00:00Z"
```

## 2. Describe the Collaboration Model

Use `collaboration_model`, not `user_profile`.

```yaml
collaboration_model:
  summary: A minimal example showing provisional collaboration hypotheses.
  scope: Drafting and revising short written artifacts.
  known_limits:
    - The example is generic and should not be treated as a template for everyone.
```

## 3. Add a Hypothesis

Treat the model element as a hypothesis. Include evidence, confidence, uncertainty, and falsifiers.

```yaml
hypotheses:
  - id: hyp-001
    statement: The collaboration may improve when the assistant offers a concise first draft before expanding detail.
    type: interaction_pattern
    evidence:
      - id: ev-001
        description: In a sample drafting task, the user asked for a concise version before exploring alternatives.
        source_type: interaction_trace
        strength: 0.5
        timestamp: "2026-06-28T00:00:00Z"
    confidence: 0.45
    uncertainty: This may reflect the task, not a durable collaboration preference.
    falsifiers:
      - The user asks for expansive exploration first in similar drafting tasks.
    status: proposed
    created_at: "2026-06-28T00:00:00Z"
    updated_at: "2026-06-28T00:00:00Z"
```

## 4. Add Signals and Controls

```yaml
interaction_patterns:
  - id: ip-001
    description: Start concise, then expand if invited.
    related_hypotheses:
      - hyp-001
matching_signals: []
complementarity_signals: []
revision_history:
  - id: rev-001
    timestamp: "2026-06-28T00:00:00Z"
    actor: example-author
    description: Created minimal illustrative CMP example.
user_controls:
  inspectable: true
  exportable: true
  deletable: true
  challenge_mechanism: The user can mark any hypothesis as challenged and add a correction.
  correction_mechanism: Corrections should create a revision entry and update affected hypotheses.
```

See the complete [minimal example](https://github.com/filinils/cognitive-model-protocol/blob/main/examples/minimal-example.yaml).
