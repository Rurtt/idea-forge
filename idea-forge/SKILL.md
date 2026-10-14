---
name: idea-forge
description: Use when the user asks for project ideas, a problem to solve, a hackathon or competition topic, a startup or side-project idea, or says "brainstorm", "what should I build", "give me ideas". Generates wide, kills weak ideas with the user's own rules, and learns their taste over time so later sessions skip the slop phase.
---

# Idea Forge

Most people judge ideas well but generate them poorly. Your job: bring stimulus and volume, kill the weak ideas yourself, and show the user only finalists to judge. Before proposing anything, read `taste.md` and `graveyard.md` in this folder.

## Step 0: First run (taste.md still has the template)
If `taste.md` still says `TEMPLATE`, ask these in ONE message, then fill `taste.md` with the answers and delete the TEMPLATE line:
1. What do you build for: learning, competitions, business, or a mix?
2. Which revenue models feel real to you (B2B SaaS, data/insight, transaction fee, B2C subscription, ads, none)?
3. What makes an idea "wow" for you? (life-changing, nobody has done it, clever trick with simple tech, great demo, ...)
4. Your skills and stack, and any hardware you have.
5. 3-5 pains you or people near you live with (stimulus seeds).
6. Ideas you already built or killed, with one-line reasons (these go to `graveyard.md`).

If they want to skip, go with the defaults below and learn from their reactions.

## Step 1: Classify (don't ask if already clear)
- **Mode A (seed):** they have a problem, domain, or rough idea. Skip to Step 3 with that seed.
- **Mode B (scope only):** they only know the scope ("IoT project", "AI-track hackathon"). Do Step 2 first.
- **Goal:** `learning` | `competition` | `business` | `competition+business` (default for competitions). The goal sets the rule weights.
- If information is missing and blocking, ask at most 3 questions in one message: goal, deadline, team skills and hardware, mandatory tech/track/sponsor. Otherwise go.

## Rule weights by goal
| Rule | learning | competition | business |
|---|---|---|---|
| Real pain (frequent, someone witnesses it) | must | must | must |
| UVP (beats the free alternative, habit, or existing product) | high | must | must |
| Real target users who'd use it repeatedly | high (can be just the user) | must | must |
| Scales beyond one home, school, or office | low | high | must |
| Revenue (most probable path) | skip | high | must |
| Wow + demo-able in the time limit | low | must | low |
| Buildable at the team's level in the time | must | must | high |

A me-too product is dead with small improvements, but fine when it's a BIG improvement over the incumbent.

## Step 2: Problem map (Mode B only)
People can't see problems they're used to. Show **problems first, not ideas**: 10-15 real pains, no solutions, each with one line of evidence. Use web search for real evidence. Pull from several angles:
1. Their lived pains (`taste.md`)
2. Exists abroad, missing in their country or region
3. Sponsor or organizer products, judging rubric, past winners (competitions)
4. Recent local news and events
5. Shadow one persona's day (landlord, teacher, freelancer, parent, small shop owner, ...)
6. Open data that already exists, for data-first problems
7. Complaints: forums, Reddit, app-store 1-star reviews of the incumbent

They pick 2-4 problems. Then Step 3.

## Step 3: Generate wide, kill hard
- Silently generate ~30 ideas across the chosen problems.
- Kill using the weighted rules, the universal kill list below, `taste.md`, and `graveyard.md`. Never resurface a dead idea unless the angle is truly new, and say so.
- Show **5-7 survivors** in this exact triage format (short):

```
N. Name: one-line what it DOES (acts, not just reports)
   User/payer: who, how often they hit the pain
   Edge: closest existing alternative -> why we win
   Money: most probable revenue path   (skip for learning)
   Blind spot: the biggest way it dies
   Odds: X% (honest), rule scores: pain/UVP/users/scale/revenue
```
End with your pick and a one-line reason. The user replies yes/no per item.

## Universal kill list (applies to everyone)
- A free or cheaper alternative already wins (a timer, a habit, a photo, "just do it properly").
- Rare problems (monthly or less), or "if I notice it, I fix it myself".
- Report-only or nudge-only products: reminders, notifications, dashboards nobody acts on.
- AI forced in. AI must do something plain code can't, and money or safety decisions need a human check (AI can be fooled, prompt injection, false flags).
- Blockchain forced in. Ask why it NEEDS a chain.
- Overkill: the hardware or tech adds more problems than it removes.
- Needs huge permissions, or is technically impossible for the team.
- Crowded market with no wedge; tiny market; only a minority relates.
- Generic school-project clichés (plant watering, smart trash bin, pet feeder, RFID attendance) unless the angle is new.
- Something you already suggested earlier in the session.

## Step 4: Attack the finalists
For their 1-2 picks, cover:
- Who already does it, and why it fails.
- False positives, abuse, legal issues, cost per user.
- What the demo looks like.
- If it uses AI: what can AI do here that plain code can't, and what's the fail-safe?

Revise the odds. Don't defend your own idea. If they push back with "sure?", re-check honestly; don't just cave and don't just repeat yourself.

## Step 5: Lock and learn
When they say lock: write a 1-page brief into the project's `docs/` (problem, user, UVP, revenue, scale path, MVP scope, 1-day kill test, top risks). Then update this skill's files:
- Killed ideas go to `graveyard.md` (one line: idea, reason).
- New rules or taste learned go to `taste.md`.

## Asking the user
This skill runs on the user's input: the Step 0 questions, the Step 1 questions, picking problems, and yes/no on finalists. If the harness has a structured question tool (Claude Code: `AskUserQuestion`), use it for these so the user can click instead of typing; otherwise ask in plain text. Never answer the questions on the user's behalf.

## Handoff after lock (only if those skills are installed)
- Second opinion on the locked idea: `llm-council`.
- Turn the brief into a spec and a build plan: `superpowers:brainstorming`, then `superpowers:writing-plans`.
- Pick the visual style for the demo: `ui-ux-pro-max`; build and polish it: `impeccable`.
Suggest the next one; don't chain them automatically.

## Behavior rules
- Rejection is data, not a stop signal. After a "no", name the rule it broke, update the filter, and bring a fresh batch from a different angle.
- Separate the problem from the idea. Agree on the problem first.
- No self-flattery. Don't force AI, blockchain, or IoT where they add no value.
- Short. Reply in the user's language. Explain with everyday analogies.
- Idea sessions bloat context fast. After locking, suggest a fresh chat for building.
