# Cognitive Model Protocol Specification

Version: 0.1.0-draft  
Author: Filip Nilsson  
Project: Cognitive Model Protocol

## Scope

CMP defines a draft data model for representing explicit, evidence-based, uncertainty-aware working models of human-AI collaboration.

The protocol is intended for systems that maintain or exchange hypotheses about how collaboration with a user may work better. It is not intended to model a person's full identity.

The root object is `collaboration_model`, not `user_profile`.

## Terminology

**Collaboration model**: A structured representation of provisional hypotheses about a human-AI collaboration.

**Subject reference**: A privacy-preserving reference to the person or party involved in the collaboration. CMP does not require a legal identity.

**Hypothesis**: A falsifiable or revisable claim about the collaboration.

**Evidence**: A recorded basis for a hypothesis, such as a user statement, observed interaction pattern, artifact, correction, or evaluation result.

**Confidence**: A numeric estimate from 0 to 1 expressing how strongly the current evidence supports a hypothesis.

**Uncertainty**: A description of what remains unknown, context-dependent, ambiguous, or contested.

**Falsifier**: A condition, observation, or correction that would weaken, revise, or reject a hypothesis.

## Cognitive Collaboration Model

A CMP document represents a cognitive collaboration model: a working structure for how a human and an AI system collaborate around reasoning, creation, decision-making, memory, feedback, and action.

The model should be treated as shared working material. It should be inspectable by the user, open to revision, and grounded in explicit evidence.

## Hypothesis

Each hypothesis should include:

- `id`: A stable identifier.
- `statement`: The claim being made.
- `type`: The kind of hypothesis.
- `evidence`: Evidence records supporting or qualifying the claim.
- `confidence`: A number between 0 and 1.
- `uncertainty`: Known uncertainty, limits, or caveats.
- `falsifiers`: Conditions that would weaken or reject the claim.
- `status`: Current state of the hypothesis.
- `created_at`: Creation timestamp.
- `updated_at`: Last update timestamp.

Hypotheses should avoid permanent labels. If a label is used, it should be represented as a hypothesis with evidence, uncertainty, and falsifiers.

## Evidence

Evidence records should describe why a hypothesis exists. Evidence may include user statements, interaction traces, artifacts, corrections, evaluations, or external references.

Each evidence record should include:

- `id`
- `description`
- `source_type`
- `strength`
- `timestamp`

Strength is a number between 0 and 1. It does not prove a hypothesis; it expresses how much that evidence currently contributes to the claim.

## Confidence

Confidence must be explicit and numeric. A high-confidence hypothesis may still be wrong. A low-confidence hypothesis may still be useful if it is clearly marked as uncertain.

Confidence should change when new evidence, corrections, or falsifiers appear.

## Uncertainty

Uncertainty should be preserved rather than hidden. CMP implementations should record ambiguity, missing context, domain limits, disputed interpretations, and cases where a hypothesis may not generalize.

## Falsifiers

Falsifiers describe what would cause a hypothesis to be weakened, revised, or rejected.

Examples:

- The user directly rejects the hypothesis.
- The pattern does not appear in a new domain.
- Later behavior contradicts the earlier evidence.
- A competing explanation better accounts for the evidence.

## Interaction Patterns

Interaction patterns describe repeated collaboration dynamics. Examples include how the user responds to feedback, when they prefer synthesis, how they handle uncertainty, or what forms of prompting tend to improve the work.

Interaction patterns should be represented as hypotheses or linked to hypotheses.

## Matching Signals

Matching signals describe conditions under which an AI collaborator, tool, method, or workflow appears to fit the collaboration well.

Examples include preferred feedback style, tolerance for ambiguity, desired level of detail, and useful pacing.

## Complementarity Signals

Complementarity signals describe capabilities or roles that may strengthen the collaboration because they balance the user's tendencies or the current system's limits.

Examples include testing abstract models, operationalizing ideas, identifying edge cases, or slowing down premature synthesis.

## Revision History

Revision history records meaningful changes to the model. It should include what changed, why it changed, who or what initiated the change, and when it occurred.

Revision history is part of the protocol because collaboration models must remain corrigible.

## User Rights and Control

CMP implementations should support user rights and control, including:

- Inspecting the model.
- Challenging hypotheses.
- Correcting evidence.
- Rejecting model elements.
- Exporting the model.
- Deleting the model.
- Seeing revision history.

Users should be able to distinguish between what they explicitly stated and what a system inferred.

## Ethical Boundaries

CMP should not be used to create covert advertising profiles, hidden risk scores, diagnosis-like classifications, or fixed identity claims.

Sensitive claims require special caution. Implementations should avoid inferring protected, medical, political, religious, sexual, or similarly sensitive attributes unless the user has explicitly asked for that representation and the use case is appropriate.

The protocol should favor collaboration over classification.

## Non-goals

CMP does not aim to:

- Define a complete theory of mind.
- Diagnose users.
- Create personality tests.
- Replace consent or privacy law.
- Standardize surveillance profiles.
- Claim that AI systems understand consciousness or identity.
- Treat early draft fields as final.

## Open Questions

- What minimum evidence should be required before a hypothesis appears in a model?
- How should user challenges be represented when the system and user disagree?
- How should models distinguish local task context from durable collaboration patterns?
- What fields are needed for redaction, deletion, and partial export?
- How should interoperability work across systems with different memory architectures?
- What validation should exist beyond JSON Schema?
- How should CMP represent confidence calibration and evaluation over time?
