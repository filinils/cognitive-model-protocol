# Rationale

This document explains why CMP exists. It is not the canonical protocol definition.

The canonical definition of CMP is [reference/current.md](reference/current.md).

## 1. Why LLMs Already Build Implicit Collaboration Models

LLMs must maintain a working representation of an interaction to be useful. They infer the user's goal, the task context, the level of detail needed, which constraints have already been stated, and what kind of response may help next.

These inferences are not always durable, and they are not always called memory or personalization. They still shape the collaboration. A system that adjusts its answer based on prior turns is already using a temporary collaboration model.

As AI systems become longer-running collaborators, these implicit models become more consequential.

## 2. Problems Created by Implicit Models

Implicit models are difficult to inspect. A user may not know what assumptions are shaping the system's behavior.

They are difficult to correct. If a system acts from a hidden assumption, the user can only correct the visible behavior, not the model behind it.

They are difficult to evaluate. Researchers and builders cannot easily compare whether one model of collaboration works better than another if the model is not represented explicitly.

They can misclassify context-specific behavior as a stable property of the user.

They are often non-portable. A user's collaboration context may be locked inside one product or memory system, creating implementation lock-in.

The problem is not that AI systems form working models. The problem is that the models are often implicit and unaccountable.

## 3. Why Memory Alone Is Insufficient

Memory can store facts, preferences, and prior interactions. That is useful, but it is not enough.

A collaboration model also needs evidence, uncertainty, confidence, falsifiers, scope, and revision history. Without those structures, memory can become a list of assertions that are hard to inspect, challenge, or update.

The important question is not only what is remembered. It is why a claim exists, how strongly it is supported, when it applies, what would make it wrong, and how the user can revise it.

## 4. Why Personality Systems Are the Wrong Abstraction

Personality-style labels are tempting because they compress complex behavior into short descriptions. They are also risky.

Labels tend to imply stability. They can turn context-specific collaboration patterns into claims about who a person is. They may encourage classification rather than correction.

CMP uses hypotheses instead of personality labels. A hypothesis can be tied to evidence, confidence, uncertainty, and falsifiers. It can be revised or rejected. It can be scoped to a context.

The goal is not to classify the user. The goal is to make collaboration assumptions visible and revisable.

## 5. Why Explicit Hypotheses Improve Collaboration

Explicit hypotheses give users and systems a shared object of discussion.

A user can ask why the system believes a pattern exists. The system can point to evidence. The user can correct the evidence, reject the inference, lower confidence, or mark the hypothesis as context-specific.

Explicit hypotheses also support better evaluation. Builders can ask whether hypotheses become more accurate over time, whether corrections change behavior, and whether uncertainty is preserved.

This does not guarantee better collaboration. It makes the assumptions available for criticism.

## 6. Why Protocols Matter

If each system represents collaboration models differently, users cannot easily inspect, export, or compare them.

A protocol can provide a shared structure without requiring one implementation. It can define the concepts that need to be represented while leaving product design, storage, user interface, and inference methods to implementations.

CMP is intended to separate the protocol from any particular software system.

## 7. Open Questions

- What should never be modeled?
- What evidence should be required before a hypothesis appears?
- How should user disagreement be represented?
- How should deletion, redaction, and partial export work?
- How should confidence be calibrated?
- How should sensitive inferences be constrained?
- How should a protocol distinguish local task context from durable collaboration patterns?
- What belongs in the protocol, and what belongs in implementations?

## 8. Why Conformance Uses a Floor and Levels

Conformance needs a non-negotiable minimum because some CMP requirements are safety and boundary conditions, not optional capabilities.

A graded standard can describe increasing capability, but it must not imply that lower levels may ignore consent, inspectability, uncertainty, falsifiability, or the distinction between collaboration and identity. The Floor defines the requirements that must hold for any conformant implementation, regardless of level or extension.

Levels then describe capability above that Floor. L1 describes core hypothesis representation. L2 adds accountability over time. L3 adds portable machine-readable interchange. The levels grade completeness of implementation, not the degree to which the Floor is satisfied.

## 9. Why Extensions Exist

CMP core deliberately stays small. It should standardize only what independent implementations need to exchange collaboration models.

Some capabilities may be useful but should not become core protocol concepts. Extensions provide a place for those capabilities to declare additional requirements without weakening the Floor or importing product logic into the protocol.

An extension is therefore a mechanism for stricter, named, versioned requirements outside the core. It is not a way to relax CMP boundaries.

## 10. Why Matching Is an Extension, Not Core CMP

Matching and recommendation create risks that differ from representing a collaboration model. They may involve pools, disclosure between parties, proposed connections, and incentives to rank or score people.

CMP core does not define matching, recommendation, ranking, compatibility scoring, or a matching algorithm.

The `ext:matching` extension reconciles this boundary by specifying requirements for implementations that choose to match. It requires separate opt-in, double consent before connection, inspectable and falsifiable rationales, and no matching on identity or protected attributes.

This gives implementations a way to declare matching capability while keeping CMP neutral. The protocol gains a requirements mechanism; it does not become a recommender.

CMP is an experiment. The current draft should be challenged before it is expanded.
