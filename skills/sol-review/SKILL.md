---
name: sol-review
description: Use when the user wants to double-check changes in the code with GPT Sol. Use when user says "sol review"
---

# Sol review

This is a workflow to make sure an implementation is correct before or after opening a pull request. Use GPT 6.1 Sol High to review your code and find issues.

Make the most minimal possible changes to appease the Sol reviewers. Be careful of scope creep and don't be scared to push back.

## Looping

If Sol finds issues, you should enter in a loop with it on fixing changes and asking for another review back.

### Looping rules

- Default: 3 rounds total. Round 1 is full. Later rounds check only changed code and open findings.
- Extend to 5 only for security, permissions, auth, data loss, or state/concurrency, while a blocker or should stays open with evidence. Or when the user asks.
- Stop early if a round returns only nits. Declined nits and comment, doc, or format-only fixes need no new round.
- One reviewer only. Sol must not start subagents or reviewers.

## Orchestration

Use the orchestration capabilities of the ADE you are in. If it's T3 Code, call `orchestrator_capabilities`.

