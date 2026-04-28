# The Founder's Chief-of-Staff Stack
### Always-On Edition — heartbeats in the cloud, brain in a private repo

> **🚧 This is a stub. The v1 desktop edition (`v1-desktop.md`) is the working blueprint today. v2 is the next step — sketched here so you know what's coming. Full prose lands when v2 ships (~two weeks from v1 launch).**

---

## What v2 unlocks

The single thing v1 can't do: **fire heartbeats while your laptop is asleep.**

v2 fixes that. Your chief of staff lives in the cloud. Morning briefs land in your inbox / phone whether or not your Mac is on. You can chat with the same brain from your phone via claude.ai/code. Travel days, weekends, vacation — the system keeps running.

## What changes from v1

The brain — SOUL.md, USER.md, AGENTS.md, MEMORY.md, domain files — **does not change.** The migration is additive.

What changes:

- **Brain lives in a private GitHub repo.** You push your local edits; the cloud agent pulls.
- **Heartbeats run as Claude Routines** on Anthropic-managed cloud infrastructure. Cron-like scheduling, no laptop dependency.
- **Mobile chat** via claude.ai/code in your phone browser.

## Requirements (additional to v1)

- **Claude Max plan or higher.** Routines per-day caps: Pro 5, Max 15, Team/Enterprise 25. The 4 core heartbeats (morning brief, weekly goal-set, weekly recap, monthly consolidation) need 4-5/day, with headroom on Max for event-driven briefings.
- **A GitHub account** (private repo).
- **30-60 minutes** for the migration.

## Migration steps (sketched — full prose at v2 launch)

1. `git init` your existing workspace folder. Decide your `.gitignore` strategy (most domains stay; sensitive subdirs can be excluded).
2. Create a private GitHub repo and `git push` your brain.
3. Configure one Claude Routine pointing at the repo. Use your existing HEARTBEAT.md content as the prompt; configure schedule trigger to match.
4. Repeat for each heartbeat task you have running in Cowork.
5. Optional: install the Obsidian Git plugin for auto-commit and auto-push (so your local edits show up in the repo Routines reads from without manual pushes).

That's it. Same brain. Different substrate.

## What v2 does NOT do

- **No custom code.** That's v3 (Agent SDK).
- **No multi-agent routing.** That's v3 (VPS + SDK).
- **No multi-model support.** That's v4 (beyond Anthropic).
- **No replacement for Cowork interactive chat.** Cowork remains your primary interactive interface; Routines run in the background.

## Tradeoff stated plainly

Routines is research preview as of April 2026. The per-day caps are real and will affect you if you're running many event-driven tasks. If you outgrow them, the next step is v3 (self-hosted on VPS — no caps, custom MCPs, custom messaging surfaces).

## When v2 ships

v2 is in flight. The blueprint will land here with a companion essay. **Expected: ~two weeks from v1 launch.**

---

— [tarikh](https://tarikhkorula.com)
