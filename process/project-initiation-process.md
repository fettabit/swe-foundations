---
type: resource
topic:
  - swe
  - process
  - project-setup
date: 2026-04-12
related:
  - "[[software engineering]]"
  - "[[build loop]]"
  - "[[swe thinking]]"
---

# Project Initiation Process

### Phase 1: Define Before You Build

1. Write a one-paragraph problem statement — what does this solve, for whom, under what constraints
2. Define scope explicitly: what is **in** scope, what is **out** of scope (scope creep kills projects)
3. Identify success criteria — how do you know it works
4. List known unknowns (Discord API rate limits, hosting requirements, etc.)

### Phase 2: Technical Design

1. Choose the stack — for a Discord bot: language (Python/discord.py, JS/discord.js, etc.), runtime, hosting target
2. Draft a high-level architecture diagram (even a rough sketch) — data flow, components, external dependencies
3. Identify external dependencies and evaluate them: maturity, maintenance status, license
4. Decide on data persistence needs — do you need a DB, which one, why
5. Define the API surface of your own system (what commands/events does the bot handle)

### Phase 3: Environment Setup

1. Create a version-controlled repo (Git) immediately — before writing any code
2. Set up `.gitignore` — credentials, build artifacts, env files never touch the repo
3. Create a `README.md` — document intent, setup steps, and usage before you forget
4. Set up environment variable management (`.env` + `dotenv` or equivalent) — no hardcoded secrets ever
5. Define dependency management (requirements.txt, package.json, etc.)
6. Set up a virtual/isolated environment (venv, nvm, Docker, etc.)
7. Configure a linter and formatter upfront — enforce style from line one

### Phase 4: Project Structure

1. Establish folder structure before writing logic — separate concerns from the start
2. Create an entry point file, config loader, and at minimum a placeholder for core logic
3. Write a stub/skeleton of the main components so the shape of the system is visible

### Phase 5: Build Loop

1. Work in small, committed increments — one feature, one fix, one commit
2. Write the simplest version that works before optimizing
3. Test each piece in isolation before integrating
4. Keep the main branch in a working state at all times

### Phase 6: Testing

1. Unit test core logic (not Discord API calls — mock those)
2. Integration test the command/event flow
3. Test edge cases and failure modes explicitly — what happens if the API is down, user sends malformed input

### Phase 7: Deployment

1. Choose hosting (Railway, Fly.io, VPS, etc.) before you need it — don't bolt this on at the end
2. Set up CI/CD if the project will live beyond a weekend
3. Configure logging to an external sink — you need visibility post-deploy
4. Set up error alerting