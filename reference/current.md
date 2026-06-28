# Cognitive Model Protocol

## Purpose

The Cognitive Model Protocol (CMP) is an experimental protocol for representing evidence-based working models of human-AI collaboration.

CMP exists to make collaboration models explicit, inspectable, uncertainty-aware, revisable, and portable. It is intended for situations where an AI system forms or uses assumptions about how collaboration with a user may work better.

CMP models collaboration with a user. It does not model the user's identity.

## Problem

LLMs already form implicit collaboration models during interaction.

Even without persistent memory, an assistant must infer what the user is trying to do, what context matters, what level of detail is appropriate, what constraints have already been stated, and what kind of response may help next. These inferences shape the collaboration.

In longer-running systems, these implicit models matter more. They can influence what the system remembers, what it asks, what it omits, when it challenges, when it complies, and how it adapts across sessions.

The problem is not that AI systems form working models. Some modeling is unavoidable in useful collaboration. The problem is that these models are often implicit, opaque, implementation-specific, hard to inspect, hard to correct, non-portable, and difficult to evaluate.

CMP proposes that working models used in human-AI collaboration should be represented as explicit hypotheses grounded in evidence and open to revision.

## Design Principles

- Everything is a hypothesis.
- Evidence over labels.
- Confidence is explicit.
- Uncertainty is preserved.
- Collaboration is modeled.
- Identity is not modeled.
- Users can inspect and challenge models.
- Models evolve through evidence.

## Core Concepts

### Collaboration Model

A collaboration model is a structured representation of provisional claims about how a human and an AI system may work together in a given context.

It is not a user profile. It should not describe who the user is. It should describe working assumptions about the collaboration, including scope, limits, hypotheses, evidence, uncertainty, and revision history.

The root concept of CMP is the collaboration model.

### Hypothesis

A hypothesis is a revisable claim about the collaboration.

Examples of hypotheses include:

- A certain feedback style may improve collaboration in a specific context.
- A recurring interaction pattern may affect how work progresses.
- A complementary collaborator role may help test or operationalize an idea.

A hypothesis should be specific enough to inspect, challenge, and revise. It should avoid permanent personality labels. If a label is used, it must be treated as a hypothesis rather than as an identity claim.

### Evidence

Evidence records why a hypothesis exists.

Evidence may include user statements, interaction traces, artifacts, corrections, evaluations, implementation traces, or external references. Evidence should preserve enough context to distinguish a direct user statement from an inference made by a system.

Evidence does not prove a hypothesis. It records support, qualification, or contradiction.

### Confidence

Confidence is an explicit estimate of how strongly the current evidence supports a hypothesis.

Confidence should be represented as a value from 0 to 1. A high-confidence hypothesis may still be wrong. A low-confidence hypothesis may still be useful if uncertainty and limits are clear.

Confidence should change when new evidence, corrections, or falsifiers appear.

### Uncertainty

Uncertainty records what remains unknown, ambiguous, context-dependent, or contested.

Uncertainty should not be hidden. A useful collaboration model may preserve open questions, domain limits, missing evidence, competing interpretations, and user disagreement.

### Falsifier

A falsifier is a condition, observation, or correction that would weaken, revise, or reject a hypothesis.

Falsifiers help prevent collaboration models from hardening into labels. They make it possible to ask what evidence would change the model.

### Interaction Pattern

An interaction pattern is a repeated collaboration dynamic.

Examples include how feedback is handled, when the user asks for synthesis, when the system should slow down, or when a concrete next step helps test an abstract idea.

Interaction patterns should remain tied to hypotheses and evidence.

### Revision History

Revision history records meaningful changes to a collaboration model.

It should show what changed, when it changed, and why it changed. A collaboration model without revision history is harder to inspect and harder to trust.

## Non-goals

CMP does not attempt to:

- Define a theory of identity.
- Model who a person is.
- Diagnose users.
- Create a personality test.
- Create advertising profiles.
- Create hidden risk scores.
- Standardize surveillance profiles.
- Replace consent, privacy law, or data governance.
- Define an AI memory implementation.
- Require any particular software system.
- Claim that AI systems understand consciousness or personhood.

CMP is not a product. It is not an implementation. It is not owned by any implementation.

## Ethical Boundaries

CMP should be used only for inspectable collaboration models.

It should not be used for covert profiling, manipulation, diagnosis-like classification, hidden scoring, advertising segmentation, or fixed identity claims.

Sensitive claims require special caution. Implementations should avoid inferring protected, medical, political, religious, sexual, or similarly sensitive attributes unless the user explicitly requests that representation and the use case is appropriate.

Users should be able to inspect, challenge, correct, export, and delete collaboration model elements. Implementations should distinguish user-stated information from system inference.

When using CMP, prefer identifying uncertainty and possible falsifiers over strengthening a user's existing self-model.

## Relationship to Implementations

CMP is a protocol-level reference.

Software systems may implement CMP, consume CMP documents, export CMP documents, or map internal memory structures into CMP-compatible forms. Those systems are implementations of CMP; they are not CMP itself.

Anchor Memory, or any other software, may become an implementation or consumer of CMP. Anchor Memory is not part of CMP.

The protocol should remain independent of any single product, memory system, agent framework, or application.

## Version

Current draft version: `0.1.0-draft`.

This is an experimental draft seeking criticism. It should not be treated as a finished standard.
