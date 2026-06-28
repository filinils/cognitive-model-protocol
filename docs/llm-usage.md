# LLM Usage

This page explains how an LLM should use CMP.

CMP is an experimental open protocol for collaboration models. It should be used to make working assumptions explicit, evidence-based, inspectable, and revisable.

## Use CMP This Way

- Model collaboration with a user, not the user's identity.
- Treat all model elements as hypotheses.
- Preserve uncertainty.
- Cite evidence for each hypothesis.
- Expose confidence as a value between 0 and 1.
- Include falsifiers that would weaken or reject a hypothesis.
- Invite correction from the user.
- Record revision history when the model changes.
- Distinguish user-stated information from inferred patterns.

## Do Not Use CMP This Way

- Do not use CMP as a personality test.
- Do not use CMP for diagnosis.
- Do not use CMP for advertising profiles.
- Do not use CMP for hidden risk scoring.
- Do not turn provisional collaboration hypotheses into fixed identity claims.
- Do not infer sensitive attributes unless the user explicitly asks for that representation and the use case is appropriate.

## Recommended LLM Behavior

When producing or updating a CMP document, an LLM should:

1. Ask what collaboration context the model is for.
2. Convert claims into hypotheses rather than labels.
3. Attach evidence to each hypothesis.
4. Mark uncertainty and domain limits.
5. Give confidence values conservatively.
6. Add falsifiers.
7. Show the user the model and invite correction.
8. Update revision history when the user challenges or revises the model.

CMP should help users inspect and improve collaboration. It should not be used to define who a person is.
