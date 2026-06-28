# Cognitive Model Protocol v0.1 Draft

Version: 0.1.0-draft  
Author: Filip Nilsson  
Status: Experimental open protocol, seeking criticism

## Purpose

CMP represents explicit, evidence-based, uncertainty-aware working models of human-AI collaboration.

CMP models collaboration with a user, not the user's identity. The root object is `collaboration_model`, not `user_profile`.

CMP is not a personality test, diagnosis, advertising profile, fixed identity model, or finished standard.

## Design Principles

- Everything is a hypothesis.
- Evidence over labels.
- Confidence is explicit.
- Uncertainty is preserved.
- Users can inspect and challenge the model.
- Models evolve through dialogue.
- Collaboration over classification.
- Portability without extraction.

## Core Objects

- `collaboration_model`: Summary, scope, and known limits of the working collaboration model.
- `hypotheses`: Provisional claims about collaboration.
- `evidence`: Records supporting or qualifying hypotheses.
- `interaction_patterns`: Repeated collaboration dynamics.
- `matching_signals`: Conditions under which a tool, method, or collaborator may fit well.
- `complementarity_signals`: Capabilities or roles that may balance the collaboration.
- `revision_history`: Records of meaningful changes.
- `user_controls`: Inspection, export, deletion, challenge, and correction mechanisms.

## Required Root Fields

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

## Required Hypothesis Fields

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

## Required Evidence Fields

- `id`
- `description`
- `source_type`
- `strength`
- `timestamp`

## Hypothesis, Evidence, Confidence, and Falsifiers

A CMP model element should be represented as a hypothesis rather than as a fixed label. Each hypothesis should cite evidence, expose confidence from 0 to 1, preserve uncertainty, and list falsifiers.

Evidence explains why the hypothesis exists. Confidence expresses how strongly the current evidence supports the hypothesis. Uncertainty records ambiguity, missing context, disputed interpretation, or domain limits. Falsifiers describe what would weaken, revise, or reject the hypothesis.

## Minimal YAML Example

```yaml
protocol_version: 0.1.0-draft
model_id: cmp-example-minimal
subject_ref: local-user-001
model_purpose: Explore a small collaboration model for drafting and revision.
created_at: "2026-06-28T00:00:00Z"
updated_at: "2026-06-28T00:00:00Z"
collaboration_model:
  summary: A minimal example showing provisional collaboration hypotheses.
  scope: Drafting and revising short written artifacts.
  known_limits:
    - The example is generic and should not be treated as a template for everyone.
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

## Ethical Boundaries

CMP should not be used for covert advertising profiles, hidden risk scores, diagnosis-like classifications, or fixed identity claims.

Sensitive claims require special caution. Avoid inferring protected, medical, political, religious, sexual, or similarly sensitive attributes unless the user explicitly asks for that representation and the use case is appropriate.

## Citation Requirement

Documentation, specification text, and examples are licensed under CC BY 4.0. Code, JSON Schema, and schema tooling are licensed under Apache License 2.0.

If you use or adapt CMP, cite:

> Filip Nilsson. Cognitive Model Protocol. Version 0.1.0-draft.
