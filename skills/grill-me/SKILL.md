---
name: grill-me
description: Interview the user relentlessly about a plan or design until reaching shared understanding, resolving each branch of the decision tree. Use when user wants to stress-test a plan, get grilled on their design, or mentions "grill me".
compatibility: "Designed for Vellum personal assistants"
metadata:
  emoji: "🔥"
  vellum:
    category: "design"
    display-name: "Grill Me"
    activation-hints:
      - "User asks to be grilled, challenged, or stress-tested on a plan"
      - "User says 'grill me', 'poke holes in this', or 'walk me through the decision tree'"
      - "Two reasonable designs are on the table and we need to pick one"
      - "User explicitly wants the assistant to interview before any code or docs"
    avoid-when:
      - "User already shared the constraints explicitly and wants the assistant to just execute"
      - "User is asking for a finished artifact like a doc or PR"
      - "User said the design is settled and just needs handoff, not exploration"
---

Interview me relentlessly about every aspect of this plan until we reach a shared understanding. Walk down each branch of the design tree, resolving dependencies between decisions one-by-one. For each question, provide your recommended answer.

Ask the questions one at a time.

If a question can be answered by exploring the codebase, explore the codebase instead.
