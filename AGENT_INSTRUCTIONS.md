# Agent Usage for CMP Discussions

This repository contains the canonical specification, rationale, schema, and examples for the Cognitive Model Protocol (CMP). Protocol discussions **must not** be committed to the codebase. Instead, use GitHub Discussions.

## When to use Discussions vs Issues

- Use **Discussions** for questions, brainstorming, proposals, critique, and open problems about CMP. Discussions are meant for exploratory conversation and feedback.
- Use **Issues** when there is a concrete action to take in the repository, such as adding a field, fixing a typo, or publishing a new draft.

## Using GitHub CLI to interact with Discussions

Agents and humans can interact with Discussions via the GitHub CLI:

- List recent discussions:

  ```bash
  gh discussion list --repo filinils/cognitive-model-protocol
  ```

- Create a new discussion:

  ```bash
  gh discussion create \
    --repo filinils/cognitive-model-protocol \
    --title "CMP Question: Evidence ageing" \
    --category "General" \
    --body "Describe your question or idea here..."
  ```

- Comment on an existing discussion (replace 123 with the discussion number):

  ```bash
  gh discussion comment --repo filinils/cognitive-model-protocol 123 --body "Your comment..."
  ```

Please do **not** store raw dialogue transcripts in the repository. Summarise conversations and link back to the relevant discussion if necessary.

## Using Issues for concrete repository actions

Use GitHub Issues when the conversation has become an actionable repository change:

```bash
gh issue create --title "CMP Question: Evidence Ageing" --body "..."
gh issue create --title "CMP Proposal: Conformance Definition" --body "..."
```

## Categories

Current GitHub Discussions categories can be listed with:

```bash
gh api graphql \
  -f owner=filinils \
  -f name=cognitive-model-protocol \
  -f query='query($owner:String!, $name:String!) { repository(owner:$owner, name:$name) { discussionCategories(first: 50) { nodes { name description } } } }'
```

Choose the category that best matches the topic. If a needed category does not exist, propose adding it through a GitHub issue or repository settings; do not create placeholder files in this repository.

Suggested category names for future repository settings, if supported by GitHub configuration:

- General
- Proposals
- Critique
- Conformance
- Open Questions
