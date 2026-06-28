# Why CMP Exists

LLMs increasingly collaborate with users over time. They help with writing, programming, planning, research, design, memory, and decision-making. Long-term collaboration requires some form of working model.

Today, many working models are implicit. They may shape system behavior without being inspectable, correctable, portable, or easy to evaluate. This creates risks: opacity, misclassification, paternalism, extraction, lock-in, and hidden assumptions about a person.

CMP proposes that working models used in human-AI collaboration should become explicit, evidence-based, uncertainty-aware, collaboratively revisable, portable, and falsifiable.

## The Core Distinction

CMP models collaboration with a user, not the user's identity.

The root object is `collaboration_model`, not `user_profile`. That distinction is intentional. A collaboration model represents provisional hypotheses about how a human and AI system may work together better in a context. It does not claim to describe who a person is.

## What Explicit Models Enable

- Users can inspect and challenge hypotheses.
- Systems can cite evidence instead of relying on hidden labels.
- Confidence and uncertainty can be exposed.
- Models can be revised through dialogue.
- Implementations can be compared more concretely.
- Users can move collaboration context across tools without surrendering it to one platform.

## What CMP Does Not Claim

CMP does not solve identity, consciousness, diagnosis, or personality. It is not a finished standard. It is an experimental open protocol and draft seeking criticism.

For the full rationale, see the repository [WHY_CMP.md](https://github.com/filinils/cognitive-model-protocol/blob/main/WHY_CMP.md).
