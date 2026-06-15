---
type: resource
topic:
  - swe
  - practical
  - debugging
  - git
date: 2026-04-12
related:
  - "[[software engineering]]"
  - "[[foundational swe principles]]"
  - "[[Sovren]]"
---

# Tips n' Tricks

## Git Discipline

- Commit messages are communication — "fix bug" is useless; "fix null pointer when user has no roles" is searchable history
- Branch per feature, never work on main directly
- `git stash` before context switching, not a new branch for every half-thought
- Learn `git bisect` — it finds the exact commit that introduced a bug via binary search
- Rebase to clean up local history before merging; merge commits for integrating branches

## Code Review Mentality (Even Solo)

- Review your own diff before committing — read it like a stranger wrote it
- If you can't explain a block of code in one sentence, it needs to be refactored or commented
- Every TODO comment needs a reason and ideally a ticket reference, not just "TODO: fix this"

## Debugging Protocol

- Read the full error message before doing anything — most people read the first line and guess
- Reproduce the bug in isolation before touching code
- Change one variable at a time
- `print`/`console.log` debugging is valid; don't let anyone tell you otherwise — but remove it before committing
- Rubber duck the problem out loud before asking for help — the act of explaining it exposes the answer 70% of the time

## Environment Hygiene

- Your local machine should never be the only place the project runs — if it only works on your machine, it's broken
- Pin dependency versions; unpinned deps will break your build six months from now when you've forgotten the project exists
- Keep dev, staging, and prod environments structurally identical — divergence causes bugs that only appear in production

## API & External Services

- Always read the rate limit docs before writing integration code
- Wrap every external call in error handling — assume the network is hostile and services go down
- Cache aggressively where the data allows it — don't hammer an API for data that doesn't change per-second
- Store API tokens with expiry awareness — build token refresh logic before you need it, not after it breaks at 3am

## Architecture Instincts

- If a function takes more than 3-4 parameters, it's a signal the abstraction is wrong
- If you're copy-pasting code, stop and abstract first
- Flat is better than nested — deeply nested logic is hard to read, test, and modify
- Config values that change between environments belong in config, not in code
- Design for deletion — code you can remove cleanly is better than code everything depends on

## Discord Bot Specific

- Handle all events with a try/catch at the top level — an unhandled promise rejection will crash the process
- Use slash commands, not prefix commands — Discord deprecated bot message reading for non-verified bots
- Rate limits are per-route, not global — learn the bucket system or you'll get 429s and not understand why
- Persist nothing in memory that needs to survive a restart — bots crash, processes restart, memory is gone
- Use an interaction collector timeout — don't leave dangling listeners in memory

## Soft Engineering Skills (High ROI)

- Learn to read other people's code faster than you write your own — most of the job is reading
- Understand HTTP deeply: status codes, headers, request/response lifecycle — it underlies everything
- Learn regex to a functional level — it appears everywhere
- Get comfortable with the terminal; GUI tools have ceilings that the CLI does not
- Learn to write a minimal reproducible example — it's how you get useful help and how you isolate bugs
- Time-box research: 20-30 minutes on a problem before escalating or changing approach — both thrashing and premature escalation are wastes

## Mindset

- Done and working beats perfect and unfinished — ship the minimal working version first
- Technical debt is a loan; sometimes it's the right call, but you always pay interest
- The best code is code you don't write — solve problems by removing complexity, not adding it
- When something feels wrong architecturally, it usually is — that friction is signal
- If the fix is taking longer than expected, you're probably solving the wrong problem