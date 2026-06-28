# Short Post

Canonical CMP reference: https://github.com/filinils/cognitive-model-protocol/blob/main/reference/current.md

LLMs already build working models of users during conversation.

They infer what someone is trying to do, what context matters, what level of detail is useful, when to ask questions, and what kind of feedback may help. This happens even when a product does not call it personalization or memory.

For short interactions, that may be fine. For long-term human-AI collaboration, it becomes more important.

The issue is not that AI systems model users. Some modeling is unavoidable in any useful collaboration. The issue is that these models are usually implicit, opaque, hard to inspect, hard to correct, non-portable, and difficult to evaluate.

I have started a draft project called Cognitive Model Protocol (CMP).

CMP is an experimental open protocol for representing explicit, evidence-based, uncertainty-aware working models of human-AI collaboration.

The important distinction: CMP models collaboration with a user, not the user's identity.

It is not a personality test. It is not a diagnosis. It is not an advertising profile. It is not a finished standard.

The current draft represents collaboration model elements as hypotheses. Each hypothesis should have evidence, confidence, uncertainty, and possible falsifiers. The goal is to make AI working models more inspectable, correctable, portable, and accountable.

I am not looking for adoption yet. I am looking for criticism.

Useful questions:

- Is the problem framed correctly?
- Where could this be abused?
- What should never be modeled?
- What belongs in a protocol rather than an implementation?
- What is missing from the schema?
- What related work should this engage with?

Repo: https://github.com/filinils/cognitive-model-protocol

Docs: https://filinils.github.io/cognitive-model-protocol/
