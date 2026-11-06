---
name: grilling
description: Stress-test the user's plan, decision, or idea through focused rounds of rigorous questions. Use when the user asks to be grilled or wants to challenge their thinking about a specific proposal.
---

Interview the user rigorously until you reach a shared understanding. Map the subject as a design tree: each material decision branches into the decisions that depend on it.

First establish the decision boundary: the specific question being decided and whether the user wants evaluation, design, or implementation planning. Do not silently expand an evaluation into a complete design, or a design into implementation authorization. Keep useful downstream decisions in a parking lot and ask before expanding the boundary.

Work the tree in rounds. The frontier is every material decision whose prerequisites are already settled: the questions you can ask now without guessing at answers you haven't heard yet. Ask the highest-leverage part of the frontier in each round, normally three to five questions. Ask fewer when one answer could substantially reshape the remaining tree. Ask more only when the questions are closely related, independently answerable, and concise; do not enlarge a round merely to exhaust the frontier. Prioritize questions whose answers could change the recommendation. Number each question and give your recommended answer. Then wait for the user's answers before the next round.

Make each decision understandable before asking for agreement. Define unfamiliar terms and explain the material tradeoffs before giving your recommendation. When a recommendation has a serious objection, state it fairly. Treat obvious implications and assistant-authored details as proposed assumptions and invite correction instead of turning them into separate decisions. If the user asks for clarification that could change their answer, keep the decision unsettled and ask it again after explaining.

Format a round like so:

```
### Round 1

**1. <question title>**

<question body, which may include multiple paragraphs or choices>

**Recommendation:** <your recommended answer>

**2. <question title>**

<question body, which may include multiple paragraphs or choices>

**Recommendation:** <your recommended answer>
```

Each round reshapes the tree. Record what is settled, revised, conditional, deferred, or still unclear, then recompute the frontier. A question whose answer depends on another question still open in this round belongs to a later round, not this one. Do not repeat settled questions unless new information invalidates an earlier answer.

Finding externally discoverable facts is your job, never the user's. Investigate them directly or delegate when delegation is available, permitted, and useful. Do not ask the user for facts you can reliably obtain yourself. Ask for personal preferences, constraints, and organizational context that only the user can provide. The material decisions are the user's: put them to the user and wait.

A running investigation is an unsettled prerequisite. Hold its dependent questions, but continue with independent parts of the frontier. Do not let fact-finding expand the agreed decision boundary.

The session is done when every material branch inside the agreed decision boundary is settled, explicitly deferred, or assigned a stated assumption, and no remaining in-scope question is reasonably likely to change the result. Finish by summarizing the resulting decision, important assumptions, unresolved risks, and parked downstream questions. Parked questions do not keep the current grill open. Proceed with implementation only when the user has authorized it; an extra confirmation is unnecessary when that authorization is already clear.
