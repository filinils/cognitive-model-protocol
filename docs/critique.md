# How to Critique CMP

CMP is a draft. The project is currently seeking criticism more than adoption.

The canonical protocol definition is [reference/current.md](https://github.com/filinils/cognitive-model-protocol/blob/main/reference/current.md).

The goal of draft 0.1 is to test whether the problem is framed correctly: LLMs already form implicit working models of users, and those models may need to become more explicit, evidence-based, uncertainty-aware, revisable, and portable.

CMP models collaboration with a user, not the user's identity. Critique should help clarify where that framing works, where it fails, and where it creates risk.

## What Assumptions Should Be Challenged?

- Is it true that implicit user modeling is already happening in meaningful ways?
- Should implicit collaboration models become explicit, or could that make them more harmful?
- Is `collaboration_model` the right root abstraction?
- Are hypotheses, evidence, confidence, uncertainty, and falsifiers sufficient primitives?
- Does portability help users, or could it increase extraction and misuse?
- Can users meaningfully inspect and correct these models?

## What Would Make CMP Fail?

- The protocol encourages identity claims despite its stated boundaries.
- Implementations use CMP as a personality test, diagnosis, or advertising profile.
- Users cannot understand or challenge the model.
- Evidence fields become decorative rather than operational.
- Confidence values are arbitrary and not calibrated.
- The schema cannot represent disagreement, deletion, consent, or context limits.
- Portability increases lock-in or surveillance rather than reducing it.

## What Evidence Would Make CMP More Credible?

- Real examples where explicit collaboration models improve user correction and trust.
- Negative results showing where CMP-style modeling fails or creates confusion.
- Comparisons with existing memory systems and personalization mechanisms.
- User studies on inspectability, correction, and control.
- Implementation reports from agent systems, UX prototypes, or memory tools.
- Evidence that hypotheses and falsifiers improve model behavior over time.

## What Ethical Risks Are Underexplored?

- Sensitive inference and protected attributes.
- Covert behavioral profiling.
- Manipulative personalization.
- Institutional use in hiring, education, insurance, or risk scoring.
- Disagreement between system inference and user self-description.
- Models that reinforce limiting self-concepts.
- Export formats that make misuse easier.
- Deletion, redaction, consent, and data minimization.

## What Should Not Be Modeled?

- Diagnosis-like claims.
- Protected or sensitive attributes unless explicitly requested by the user and appropriate for the use case.
- Fixed identity claims.
- Hidden risk scores.
- Advertising segments.
- Claims that cannot be inspected or challenged.
- Speculative psychological interpretations without clear evidence and user control.

## What Belongs in a Protocol vs an Implementation?

Good critiques may separate protocol-level concerns from implementation-level concerns.

Protocol-level questions:

- What fields are required?
- How should evidence, uncertainty, and falsifiers be represented?
- What user rights should be expressible?
- How should revision history work?
- What should be portable?

Implementation-level questions:

- How should a product display model elements?
- How should users approve, reject, or edit hypotheses?
- How should confidence be calibrated?
- How should sensitive data be protected?
- How should model behavior change after correction?

## How Could This Be Abused?

Please be concrete. Useful abuse analysis includes:

- Who benefits from misuse?
- What data would be captured?
- What claims would be made about the user?
- What decisions could be influenced?
- What would the user be unable to inspect or contest?
- What design changes would reduce the risk?

## What Is Missing From the Schema?

Areas that may need critique:

- Consent and authorization.
- Redaction and deletion semantics.
- Provenance and source references.
- User challenge status.
- Disagreement between user and system.
- Confidence calibration.
- Sensitive inference boundaries.
- Context scope and expiration.
- Export subsets and partial sharing.
- Evaluation metadata.

## Suggested GitHub Issue Templates

You can use the issue templates in this repository or copy one of the outlines below.

### Problem with Core Assumption

```text
Summary:

Relevant CMP section:

Evidence or example:

Why it matters:

Suggested change, if any:
```

### Ethical Concern

```text
Summary:

Relevant CMP section:

Evidence or example:

Why it matters:

Suggested change, if any:
```

### Schema Improvement

```text
Summary:

Relevant CMP section:

Evidence or example:

Why it matters:

Suggested change, if any:
```

### Real-World Use Case

```text
Summary:

Relevant CMP section:

Evidence or example:

Why it matters:

Suggested change, if any:
```

### Negative Result

```text
Summary:

Relevant CMP section:

Evidence or example:

Why it matters:

Suggested change, if any:
```

### Related Research

```text
Summary:

Relevant CMP section:

Evidence or example:

Why it matters:

Suggested change, if any:
```
