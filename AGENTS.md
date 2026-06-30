# Agent Entrypoint for CMP

This file is the entrypoint for LLMs, agents, assistants, MCP tools, memory systems, and autonomous repository readers.

CMP is the Cognitive Model Protocol. It is an experimental interoperability protocol for explicit, evidence-based, uncertainty-aware, revisable collaboration models between humans and AI systems.

CMP models the collaboration context. It does not classify the person.

## Read order

1. `cmp.manifest.yaml` for machine-readable discovery.
2. `reference/current.md` for the canonical protocol definition.
3. `SPEC.md` for the draft field specification.
4. `schema/cmp.schema.json` for validation.
5. `examples/minimal-example.yaml` for a minimal CMP document.
6. `examples/systems-synthesist-example.yaml` for a larger illustrative example.
7. `schema/cmp-conformance.schema.json` for conformance disclosure validation.
8. `examples/conformance-disclosure-example.json` for a worked conformance disclosure.
9. `RATIONALE.md` for why CMP exists.
10. `docs/critique.md` for how to challenge the protocol.

Use `docs/llms.txt` only as a compact LLM discovery note. Do not treat it as the protocol definition.

## What CMP is

- An experimental interoperability protocol.
- A way to represent explicit working models of human-AI collaboration.
- Evidence-based, uncertainty-aware, inspectable, revisable, and portable.
- Centered on `collaboration_model`.

## What CMP is not

- Not a user profile.
- Not a personality model.
- Not a diagnosis system.
- Not an advertising profile.
- Not a hidden user model.
- Not a fixed identity model.
- Not a product, SDK, API, memory system, or MCP server.

## Core operating rules for agents

- Model the collaboration context, not the human's identity.
- Treat every CMP model statement as a hypothesis.
- Back hypotheses with evidence.
- Preserve explicit confidence, uncertainty, and falsifiers.
- Do not infer beyond the available evidence.
- Prefer falsifiable hypotheses over traits or labels.
- Keep user inspectability, revisability, and portability visible.
- Do not strengthen a user's existing self-model unless the evidence supports a collaboration hypothesis.
- Do not store raw dialogues or design discussions in this repository. Use GitHub Discussions or Issues for discussion.

## Validation

When producing CMP documents:

1. Read `SPEC.md`.
2. Validate against `schema/cmp.schema.json`.
3. Compare structure against `examples/minimal-example.yaml`.
4. Preserve required fields for hypotheses: `evidence`, `confidence`, `uncertainty`, and `falsifiers`.

When producing conformance disclosures:

1. Read the conformance section in `reference/current.md`.
2. Validate against `schema/cmp-conformance.schema.json`.
3. Compare structure against `examples/conformance-disclosure-example.json`.

## Safe usage boundaries

Do not use CMP for:

- personality classification
- diagnosis
- advertising profiles
- fixed identity models
- hidden user profiling
- surveillance
- prediction of the person

CMP may represent uncertain, evidence-backed hypotheses about what improves collaboration in a specific context. It must not present those hypotheses as claims about who the person is.

## Implementation note: Anchor Memory

Anchor Memory may be an implementation or consumer of CMP. Anchor Memory is not part of CMP and does not define the protocol.

Any implementation-specific behavior belongs outside the canonical protocol reference unless at least two independent implementations need it for interoperability.

## CLI discovery example

```bash
gh repo clone filinils/cognitive-model-protocol
cd cognitive-model-protocol
cat cmp.manifest.yaml
cat AGENTS.md
```
