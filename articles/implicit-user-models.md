# LLMs Already Model Users. The Problem Is That the Models Are Invisible.

Note: this article is explanatory, not normative. The canonical CMP reference is [reference/current.md](../reference/current.md).

Large language models already build working models of users.

They do this even when a product does not call it personalization, even when there is no durable memory feature, and even when the system prompt says nothing about user profiling. During a conversation, an LLM tracks what a person is asking for, what they seem to know, what they may be trying to accomplish, what kind of answer has worked so far, and what kind of answer may fail next.

This is not mysterious. It is part of ordinary language use. If someone asks a technical question and then follows up with a request for implementation details, a useful assistant infers something about the task, the user's context, and the level of detail that may now be appropriate. If someone repeatedly rejects vague advice and asks for concrete examples, the assistant adapts. If someone is trying to reason through a difficult design problem, the assistant may begin to model which distinctions matter, what assumptions are in play, and where the collaboration is getting stuck.

The problem is not that AI systems model users. In any sustained collaboration, some modeling is unavoidable. The problem is that these models are usually implicit, inaccessible, non-portable, difficult to correct, and hard to evaluate.

As LLMs move from one-off text generation toward longer-running collaboration, that problem becomes more important.

## Why Implicit Models Already Exist

Every useful assistant maintains some temporary representation of the conversation. It has to. Without a working model, it cannot resolve references, choose the right level of detail, track open questions, remember constraints from earlier turns, or distinguish between a user's stated goal and a possible misunderstanding.

Some of this modeling is local and short-lived. A model may infer that "it" refers to the function just discussed, or that the user wants a concise answer because they asked for one in the previous message. Other modeling is broader. A system may infer that the user is exploring an idea rather than asking for a final answer, that they want criticism before implementation, or that they respond well to explicit tradeoffs.

These inferences can be useful. They can make collaboration feel less repetitive and more context-aware. But they also shape the interaction. The system may decide what to emphasize, what to omit, when to challenge, when to reassure, when to proceed, and when to ask questions. If those decisions are based on hidden assumptions, the user cannot inspect the model that is influencing the collaboration.

This matters even before persistent memory enters the picture. A conversation-length working model can still overfit, misread the user, or carry forward an early mistake. Persistent memory simply raises the stakes because assumptions can survive across sessions and products.

## Why Memory Is Not Enough

Memory systems are often presented as the solution to long-term AI collaboration. They are important, but memory alone is not enough.

A memory item can record that a user prefers short answers, works on a particular project, or wants a certain convention followed. But a collaboration model needs more than stored facts. It needs to represent uncertainty, evidence, confidence, scope, and revision. It needs to distinguish what the user explicitly said from what the system inferred. It needs to show when a pattern applies only in one domain, when it has weak support, and what would make it wrong.

Without that structure, memory can become a pile of assertions. Some may be true. Some may be stale. Some may be useful in one context and harmful in another. Some may be interpretations presented as facts. If the user cannot see why a memory exists or how strongly it is supported, correction becomes difficult.

The central issue is not storage. It is accountability. A durable collaboration model should be inspectable and revisable. It should make clear what evidence supports a claim, what remains uncertain, and how the model has changed over time.

## Why Personality Labels Are the Wrong Abstraction

One tempting shortcut is to describe users with labels: planner, creative, analytical, novice, expert, visual thinker, power user, risk-averse, decisive, anxious, systems thinker. Labels can be convenient. They compress complexity into a form that systems can act on.

They are also dangerous as the primary abstraction.

Personality-style labels tend to feel more stable than the evidence justifies. They invite classification rather than collaboration. They can blur the difference between who a person is and what helped in a particular interaction. They can become sticky even when the original evidence was weak. They can encourage systems to act as if they understand the person rather than maintaining a provisional model of the working relationship.

A better abstraction is the hypothesis.

Instead of saying "the user is a systems thinker," a collaboration model might say: "In this project context, the user often connects implementation details to broader design and governance concerns." That statement can be tied to evidence. It can have a confidence value. It can include uncertainty. It can say where it may not apply. It can list falsifiers, such as the user asking to stay narrowly focused or rejecting cross-domain synthesis as unhelpful.

This is a different kind of representation. It does not try to define the person. It tries to improve the collaboration while leaving room to be wrong.

## What Explicit Collaboration Models Could Enable

An explicit collaboration model could make the hidden working model visible.

A user could inspect the model and see the hypotheses currently shaping the interaction. They could challenge a claim, correct evidence, reject an inference, or mark something as context-specific. They could see which assumptions came from direct user statements and which came from system inference.

Builders could evaluate whether a model actually improves collaboration. Do hypotheses become more accurate over time? Are confidence values calibrated? Do users correct them? Do corrections propagate into behavior? Do models preserve uncertainty, or do they harden into labels?

Researchers could compare approaches across systems. Today, user modeling is often implementation-specific and difficult to inspect. A shared protocol would not solve evaluation by itself, but it could create a common surface for asking better questions.

Agent developers could make memory and adaptation less opaque. A system could expose why it is choosing a particular collaboration style: "I am offering a concrete next step because previous evidence suggests that implementation checks help test this kind of abstract model. Confidence is moderate. Tell me if that is not useful here."

UX designers could give users better controls. Instead of a black-box personalization toggle, users could see model elements, confidence, evidence, uncertainty, and revision history. They could export or delete the model. They could distinguish helpful adaptation from unwanted profiling.

Portability also becomes possible. If collaboration context is locked inside one product, users must either start over elsewhere or accept a platform's private representation of them. A portable collaboration model could let users carry selected context across tools while preserving boundaries, attribution, and control.

## Risks and Ethical Boundaries

Making collaboration models explicit does not remove risk. It changes the surface of the risk.

Explicit models can be misused. They could become more legible tools for surveillance, advertising, manipulation, employment screening, education scoring, or diagnosis-like classification. A protocol that represents working hypotheses could be distorted into a protocol for behavioral profiling.

That is why the boundary matters: CMP models collaboration with a user, not the user's identity.

The model should not claim to know who a person is. It should not infer sensitive attributes casually. It should not be used for covert advertising profiles, hidden risk scores, diagnosis, or personality typing. It should not turn a temporary interaction pattern into a permanent claim.

The model should also preserve user agency. A user should be able to inspect it, challenge it, correct it, export it, and delete it. A system should not treat disagreement as noise. In many cases, user correction should outweigh inferred patterns.

There are hard open questions here. What should never be modeled? How should sensitive inferences be handled? How should systems represent disagreement between user self-description and observed interaction patterns? How should models avoid reinforcing a user's existing self-model when that model may be limiting or inaccurate? How should confidence be calibrated? What kind of evidence is enough?

These questions should be addressed before any protocol like this is treated as mature.

## Introducing CMP as Draft 0.1

The Cognitive Model Protocol, or CMP, is an experimental open protocol for representing explicit, evidence-based, uncertainty-aware working models of human-AI collaboration.

It is draft 0.1. It is not a standard. It is not a claim that the problem has been solved.

CMP proposes a root object called `collaboration_model`, not `user_profile`. That naming choice is central. A `user_profile` implies that the object describes the user. A `collaboration_model` implies that the object describes provisional working hypotheses about the collaboration between a user, a system, a context, and a purpose.

In CMP, model elements are hypotheses. A hypothesis has a statement, evidence, confidence, uncertainty, falsifiers, status, and timestamps. Evidence has a source type, description, strength, and timestamp. The model also includes interaction patterns, revision history, and user controls.

The aim is practical rather than metaphysical. CMP does not try to solve identity, personality, consciousness, or diagnosis. It asks a narrower question: if AI systems are already forming working models during collaboration, can those models be made more explicit, accountable, revisable, and portable?

That question may be framed wrong. The schema may be too narrow. The terminology may invite misuse. The protocol may need stronger deletion semantics, richer consent fields, better provenance, clearer boundaries for sensitive inferences, or a different abstraction entirely.

That is why the current draft is seeking criticism.

## Project Links

GitHub repo: https://github.com/filinils/cognitive-model-protocol

Docs: https://filinils.github.io/cognitive-model-protocol/

## Call for Criticism

The most useful response to CMP right now is not adoption. It is critique.

Challenge the core assumption that implicit models should become explicit. Identify cases where explicit modeling could make things worse. Point out where the schema overreaches, where it is too weak, and where the ethical boundaries are incomplete. Bring related research. Bring negative results. Bring concrete examples that do not fit.

CMP is a draft. The most useful contribution right now is criticism.
