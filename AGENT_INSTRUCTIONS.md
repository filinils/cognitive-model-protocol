# Agent Instructions

This repository contains the canonical materials for the Cognitive Model Protocol (CMP):

- the canonical protocol reference in `reference/current.md`
- the rationale in `RATIONALE.md`
- the technical field specification in `SPEC.md`
- the JSON Schema in `schema/cmp.schema.json`
- example CMP documents in `examples/`
- supporting project instructions and governance files

Do not commit dialogues, raw transcripts, working conversations, meeting notes, or design discussions to this repository.

The repository is for stable protocol materials, rationale, specification, schema, examples, and contribution guidance. Discussion records belong outside the repository unless they have been distilled into a protocol change, rationale update, example, issue, or pull request.

## External Discussion

Agents and automated processes should use GitHub Issues or GitHub Discussions for proposals, questions, critique, and design discussion.

Use the GitHub CLI when available:

```sh
gh issue create --title "CMP Question: Evidence Ageing" --body "..."
gh issue create --title "CMP Proposal: Conformance Definition" --body "..."
gh issue create --title "CMP Critique: User Control Semantics" --body "..."
```

For GitHub Discussions, use `gh api` or the GitHub web interface, depending on repository configuration and available permissions.

## Summaries

Agents, or humans acting on their behalf, may summarize external conversations and post distilled insights as GitHub issues, discussion posts, or comments.

Do not store raw transcripts in this repository. If a conversation produces a useful protocol insight, record the insight as a concise issue, pull request, or documentation change.

## Future Automation

Future workflows may summarize external discussions into issues or discussion comments. Such pipelines should run outside this repository unless and until they produce stable protocol documentation or contribution guidance.
