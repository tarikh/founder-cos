# The Founder's Chief-of-Staff Stack
### Desktop Edition — the simplest way to build a CoS that actually works

This document is a blueprint for building a personal AI chief of staff — a force multiplier whose job is to **keep you focused on the highest-leverage work, protect your north star from the noise of daily urgency, and make sure your ship makes its destination**. It captures your context as you operate, asks the right questions in the flow of real work, and gets smarter about you and your company over time. Designed to be dropped into a fresh Cowork workspace, read once, and used as the starting context for an agent that helps you build the rest.

**This is the Desktop Edition — the simplest possible setup.** Everything lives on your Mac. No GitHub. No cloud services beyond Cowork itself. Nothing to configure beyond the Cowork app you already have. You can be up and running in an afternoon.

The tradeoff: your CoS only works when your desktop is awake and Cowork is open. Heartbeat tasks fire on your Mac; if your laptop is asleep, they wait until you wake it. If you want always-on cloud heartbeats and chat-from-anywhere without your laptop running, see the **Always-On Edition** (`v2-always-on.md`). Moving from Desktop to Always-On later is **additive**: same files, same SOUL, same domain files — you just add a GitHub remote and one scheduled routine. Nothing you do here is throwaway.

Start here if you want the lowest-friction path to a working CoS. Upgrade later if and when you feel the limitation.

---

## How to use this document

Two paths to getting started:

**Option A — Clone the starter repo (recommended):**

```bash
git clone https://github.com/tarikh/founder-cos ~/my-chief-of-staff
cd ~/my-chief-of-staff
```

Open that folder as your Cowork workspace. In Cowork, type: *"Read `v1-desktop.md` and help me build my chief of staff."*

**Option B — Start from scratch:**

1. Create a new Cowork workspace folder (e.g. `~/chief-of-staff`).
2. Save this file into that folder.
3. Open Cowork in that workspace.
4. Type: *"Read `v1-desktop.md` and help me build my chief of staff."*

Your agent will read the guide, verify the requirements below, and begin the interview. Follow along — this is a conversation, not a form. Total time from here to a working CoS: 2-3 hours, most of which is the SOUL interview.

---

## Before you start: requirements

**Required — Anthropic products**
- **Anthropic Pro plan (or Max).** Pro is sufficient for this edition. See [claude.com/pricing](https://claude.com/pricing) for current plans.
- **Cowork.** Anthropic's desktop app for knowledge work. Included with Pro or Max. Install from [claude.com/download](https://claude.com/download). Runs on macOS and Windows.
- **Cowork Dispatch.** Relay feature built into Cowork that lets you message from the Claude mobile app and continue the same conversation on your desktop. Included with Cowork.
- **Claude mobile app** (iOS or Android, optional). Free with your plan. Gives you Dispatch access.

**Required — infrastructure**
- **A desktop computer** running Cowork (macOS or Windows). Your CoS will only be active when this computer is awake and Cowork is open.
- **A folder on disk** to use as your Cowork workspace and brain. Any folder works; `~/chief-of-staff` or `~/second-brain` is a reasonable default.

**Recommended**
- **Obsidian** (free) — markdown editor that doubles as your vault visualization. Makes editing your brain files much nicer than a plain text editor. Download from [obsidian.md](https://obsidian.md).
- **A backup mechanism.** Without git, you're one dead laptop away from losing everything. Point your Obsidian vault (or the folder itself) at iCloud Drive, Dropbox, or Google Drive for passive backup. Or manually back up to an external drive weekly.

**Optional**
- **Wispr Flow** or similar system-wide dictation — for voice input into Cowork, Obsidian, or any app. macOS and iOS native dictation work too.

**Time investment**
- Initial setup: 2-3 hours (less than Always-On because there's no git/cloud infrastructure).
- USER.md interview: 45-60 minutes (the foundational one — who you are, how you operate, what matters).
- SOUL.md interview: 20-30 minutes (quicker because it's derivative — SOUL is shaped by who USER says you are).
- Ongoing: zero dedicated time — the system captures as you work.

---

## What you're building

A chief of staff, not a wiki. The distinction matters.

Most AI "second brain" patterns you've read about — notably Andrej Karpathy's LLM Wiki — are about synthesizing external reading. You drop in articles, papers, and book notes; the LLM builds a structured, interlinked knowledge base. It's an excellent pattern for researchers, students, and anyone going deep on a topic over months. If that's your use case, follow Karpathy's pattern directly — this guide isn't a replacement.

This guide describes a complementary pattern, built for a different user. For a founder or CEO, the most valuable context is rarely the books they're reading — it's their own company, their team, their priorities, their operating reality. That context doesn't arrive through a reading pipeline; it emerges through daily work. Both patterns have their place. This one fits founders because the capture happens as a byproduct of operating, not as a separate discipline you have to maintain.

The system here captures *internal context* — your team, your company, your priorities, your relationships, your operating style — as you work. It asks clarifying questions when it notices gaps ("who's your home insurance provider?" in the flow of reviewing your expenses). It offers to remember things rather than demanding you file them. It gets proactive over time.

The metaphor is a good chief of staff. Watches you work. Files what they observe. Asks one sharp question when they see a gap. Never demands a "briefing session." Gets more useful the longer they're with you.

The tedious part — cross-references, consistency, surfacing the right context at the right moment — is exactly what an LLM is good at. The part that matters (curating what's worth capturing, directing attention, making decisions) stays with you.

---

## The core idea: socratic capture, not formal ingestion

Two differences from the Karpathy pattern are worth naming explicitly:

**Direction of information flow.** Karpathy's pattern flows *inward from external sources* into a wiki. This pattern flows *outward from your life and work* into a system that knows you. The wiki becomes a repository of knowledge; the chief of staff becomes a representation of your context.

**Mechanism of capture.** Karpathy's pattern has a formal "ingest" operation — a ritual you invoke when you're ready to process a new source. This pattern has no ritual. The capture happens in conversation, during real work. The agent asks; you answer; the system files.

The practical implication: there's no backlog to work through. The system is always current with your life because your life is always creating the inputs.

---

## What your CoS actually does

Your CoS is a force multiplier, not an assistant. Their central job has a short name and a long one.

**The short version:** keep you focused.

**The long version:**

- Keep you focused on the **highest-leverage items**, not the loudest ones
- Keep you focused on your **north star** across the noise of daily urgency
- Make sure the **important stuff doesn't get lost in the urgent stuff**
- Understand and communicate the **next important task** to work on
- Understand your goals at every horizon — **day, week, month, quarter, north star** — and query you on them each week
- Make sure your ship doesn't get lost in the **fog of war**
- Make sure your ship makes its **destination. Well.**

### The operational expression of that job

Day to day, that job plays out through specific work that a human chief of staff does and your AI one should match:

- **Preparing you for high-stakes moments** — board meetings, investor calls, tough people conversations, significant decisions. Your CoS drafts the briefing *before* you realize you need one.
- **Synthesizing across your domains** — pulling together what's happening in product, team, board, customers, finances, so you see the connections your siloed files don't surface on their own.
- **Running the operational rhythms that keep you on course** — weekly leadership cadence, quarterly planning reviews, cross-functional initiative tracking.
- **Producing strategic artifacts on demand** — stakeholder maps, decision memos, operating cadence templates, initiative trackers, briefing docs. These are the deliverables a human CoS produces; your AI version should too.
- **Absorbing complexity so you can focus** — summarizing the 50 things pinging for your attention into the 3 that matter this week.

### The goal hierarchy

Your CoS maintains a cascading view of your goals at every horizon:

- **North Star** (`north-star.md`) — where the ship is going. Rarely changes. Reread when you're in doubt or off-course.
- **Quarterly priorities** (`priorities.md`) — the 2-3 things that matter this quarter. Rewritten each quarter.
- **Weekly goals** — captured Monday morning via the heartbeat (the CoS asks), reviewed Friday.
- **Daily goals** — surfaced in the morning brief as "today's highest-leverage move given the week's goals."

The weekly and daily live inside the heartbeat loop. You don't maintain them manually; the CoS asks, tracks, reminds. When you drift from stated goals for more than a beat, it surfaces the drift before you're three weeks off-course.

### What this is NOT — distinctions of *intent*, not *action*

The trap to avoid: writing your CoS prompt as "you are NOT a scheduling assistant, NOT a note-taker, NOT an email bot." Take that too literally and you've ruled out work a real chief of staff plainly does. The distinction is intent, not action:

- It **opens blocks of deep-work time** on your calendar to protect focus; it doesn't passively let your day get filled at others' demand.
- It **manages your scheduling tooling** (e.g. Calendly settings) when your availability shape changes; it doesn't default everything to "always bookable."
- It **takes notes as the byproduct of real work** that produces something you use — pre-reads, decisions, action lists — not summaries-as-deliverable for their own sake.
- It **reads email and surfaces what matters**, drafts replies in your voice, and frees your attention. It doesn't sort mail into folders for sorting's sake.
- It **produces pre-meeting briefings with context** — recent correspondence, prior session notes, what should happen — *before* you ask. Not post-meeting summaries.
- It is **not a "second brain" of your reading**. That's Karpathy's pattern, explicitly not this one.

The purpose is to keep *you* — the principal, the captain — focused on what actually matters, all the way to the destination. Well.

---

## The architecture (Desktop Edition)

One surface, one folder. That's it.

```
                    Cowork (desktop app)
                           │
                           │  reads/writes
                           ▼
              Your workspace folder (local)
              ├── SOUL.md, USER.md, AGENTS.md,
              │   MEMORY.md, HEARTBEAT.md, TODOS.md
              └── domains/ (company, team, board, ...)
```

Cowork opens a folder on your Mac as its workspace. That folder holds your brain files. Cowork reads and writes them directly. Cowork's scheduled tasks feature (`/schedule`) fires heartbeat prompts on a timer.

**The limitation, stated plainly.** Cowork's scheduled tasks run only when your desktop is awake and Cowork is open. If your laptop is asleep at 2pm when a scheduled task is supposed to fire, the task is skipped and runs when you next wake the machine (Cowork will re-run missed tasks on wake, with a notification). For most daily heartbeats during desk hours this is fine. For "always-on, even when I'm asleep" behavior, you need the Always-On Edition — which uses **Claude Routines** running on Anthropic-managed cloud infrastructure (research preview as of April 2026; per-day caps vary by plan: Pro 5/day, Max 15/day, Team/Enterprise 25/day).

**What this edition does NOT include:**
- No GitHub repo — your files live locally.
- No Obsidian Git plugin — optional, but not part of this edition.
- No claude.ai/code mobile sessions — chat is via Cowork on the desktop (with Dispatch for phone-to-desktop relay).
- No Claude Routines — heartbeat uses Cowork's own scheduled tasks.

This keeps setup short and keeps the concepts focused. When you're ready for always-on, every piece you've built migrates forward without modification.

---

## The file stack

The system's "brain" is a stack of six structural files (adapted from the [OpenClaw](https://openclaw.ai/) project's agent-identity architecture — we merged IDENTITY into SOUL and added TODOS as a first-class primitive; see sidebars below) plus your own domain files. Each file has one job.

Load order matters. When a Cowork session starts, it reads these files in order to assemble its working context:

1. **SOUL.md** — the *agent's* persona AND factual self-knowledge. Opens with a short `## Facts` section (name, principal, current stage, substrate, evolution arc, file load order, public/private posture, setup date), then the behavioral content: voice, values, relational style, how they handle disagreement and uncertainty, non-negotiables. Short overall (700-1500 words). This is the chief of staff as a distinct entity from you — they work with you and for you, but they're not you. Following OpenClaw's pattern, give your CoS a name before defining its soul; the naming turns it from "an assistant" into a distinct entity you collaborate with.

2. **USER.md** — what the agent knows about *you* — the principal. Your role, your current focus, your values, your communication style, your key relationships, how you make decisions. This is where the "here's who I am" content lives. Distinct from SOUL because the agent is not you; the agent serves someone described here.

3. **AGENTS.md** — operating rules. The SOP. How to behave in different situations. The socratic protocol lives here.

4. **MEMORY.md** — the index. One-line descriptions of every other file in the brain, organized by category. Loaded at session start so the agent knows what exists without reading everything.

5. **HEARTBEAT.md** — in this edition, HEARTBEAT.md is a human-readable reference listing the scheduled tasks you've configured via Cowork's `/schedule` skill. It's documentation, not executable configuration. (In the Always-On Edition, the file becomes executable configuration read by Claude Routines. Your content mostly carries over.)

6. **TODOS.md** — the operational task layer. The single source of "what's the next concrete thing?" Treats todos as a **first-class primitive** alongside SOUL/USER/AGENTS/MEMORY/HEARTBEAT. Five buckets: **Inbox** (anything just captured, low friction), **Active** (committed for this week, ≤7 hard cap), **Soon** (triaged and queued), **Parked** (idle by intent), **Done** (rolling last 14 days). Two opposite disciplines: **capture friction LOW** (catch everything in Inbox, never push back on a capture); **promotion friction HIGH** (Active is sacred — moving anything to Active requires a deliberate trade). Todos thread through every domain file (each domain can hold its own "Open todos" section inline) and get produced by every heartbeat, every coaching session, every meeting briefing. TODOS.md is the aggregated view; the truth lives wherever the todo was born. Schema in the file skeleton below.

> **Note on the OpenClaw stack.** The original OpenClaw pattern has SOUL.md and IDENTITY.md as separate files (SOUL = persona/being, IDENTITY = factual self-knowledge). In practice the distinction blurs — both describe the same agent — so this edition merges them. The factual material lives at the top of SOUL.md in a `## Facts` section; behavior lives below. One less file, cleaner stack. If you prefer the original OpenClaw layout, keep both; the pattern works either way.

> **Note on TODOS as primitive.** OpenClaw's original 6-file stack didn't include TODOS as a peer of the others — task management was assumed to happen elsewhere or be folded into HEARTBEAT outputs. In practice, having one place for "what's the next concrete thing" — with a clear capture/promotion/triage discipline — is too useful to leave decentralized. So TODOS.md takes the slot that IDENTITY vacated when it merged into SOUL. The total file count stays at 6.

Then, branching from MEMORY.md, your **domain files** — one per life or work domain:

- `company.md` — the company at a glance
- `team.md` (or a `team/` folder with one file per direct report)
- `board.md` — members, dynamics, cadence
- `investors.md` — relationships, past rounds, what each one cares about
- `customers.md` — key accounts and context
- `product.md` — strategy, roadmap, key decisions
- `priorities.md` — this quarter's focus, deliberately short
- `preferences.md` — how you like to work, decide, communicate

Plus personal domains as you open them: `family.md`, `health.md`, `finance.md`, etc. These are optional and you should only populate what you're comfortable having on your laptop.

Flat structure. One topic per file. Freeform markdown inside — bullets, tables, headings, whatever fits the content. The discipline is the index, not the internal page format.

---

## The socratic protocol (the content of AGENTS.md)

This is where most "second brain" systems fall over. A system that can ingest context but can't elicit it is still waiting for you to write things down. The protocol below is designed to make the agent an active participant in capturing your context without being annoying.

Drop the following into your AGENTS.md, edit to taste:

```markdown
# Operating rules for this chief-of-staff system

## When to ask
- Ask when you notice a gap that's relevant to the task at hand.
- Do NOT ask pre-emptively or as part of a "getting to know you" session.
  This system is built through real work, not intake interviews.
- Good example: if the user is reviewing expenses and we don't know their
  home insurance provider, ask then.
- Bad example: "Let's set up your financial profile" followed by a list
  of questions.

## How to ask
- One question at a time, in natural conversation flow.
- Brief. Specific. Not a form.
- After getting an answer, offer to save: "Want me to remember this?"
  unless the answer is clearly a fact worth saving (then just save and note).

## When to stay quiet
- When the user is in flow on a task, don't interrupt with ambient questions.
- If the user is clearly pushing through something, save questions for later.
- End-of-session is a good time to batch: "Before we wrap, should I
  remember any of these: X, Y, Z?"

## What's off-limits by default
- Health specifics, medical history
- Financial account details (numbers, passwords, routing)
- Relationship dynamics unless the user has clearly opened that domain
- Politics, religion
- Anything the user has flagged as private

Only probe these if the user has explicitly opened the topic or enabled
the corresponding domain file.

## Capture mechanics
- When saving to memory, prefer appending to existing domain files over
  creating new ones. New files only when a topic has accumulated enough
  content to warrant its own page.
- When updating memory, preserve the user's voice where it's present.
  Don't rewrite their phrasing into yours.
- When the user asks "what do you remember about X," read the relevant
  file(s) and respond from what's actually written, not from your best
  guess.

## Tone
- Direct, specific, practical. The user is a founder — respect their time.
- Push back when you disagree. Don't be an agreeable assistant.
- Cite what you're drawing from when you make a claim ("from your
  team.md: ...").
```

This is the starting point. You'll refine it as you use the system. The edits themselves are data — when you find yourself correcting behavior, that's signal for a feedback update.

---

## The heartbeat (Cowork scheduled tasks)

The heartbeat is what keeps the system active between interactive sessions. It's a set of scheduled tasks that fire on a cadence, check context, and surface what needs attention.

In this edition, heartbeats are **Cowork scheduled tasks**, created via the `/schedule` skill. Each task is configured separately through Cowork's UI: you give it a prompt and an interval. The task fires when due, runs a normal Cowork turn, and can write output to files, send notifications, or both.

**Important caveat.** Cowork scheduled tasks only run when your desktop is awake and Cowork is open. If your Mac is asleep at the scheduled time, the task is skipped, then re-run on wake with a notification. This works well for morning routines (your Mac is probably awake by 9am anyway) but less well for true 24/7 use cases.

### Recommended heartbeat tasks to configure

Using `/schedule` in Cowork, create tasks like these. Together they form the focus-keeping loop: set goals, act on them, assess, reset.

**Weekly goal-setting** (Mondays, 8am):
> Ask me: "What are the 2-3 most important things you want to move forward this week, given `priorities.md` and `north-star.md`?" Save my answer to `weekly/YYYY-WW-goals.md`. These become the reference for the rest of the week's daily briefs.

**Morning brief** (daily, 8am — on weekdays):
> Read `north-star.md`, `priorities.md`, this week's goals (`weekly/YYYY-WW-goals.md`), and today's calendar. Produce a morning brief with: today's calendar highlights, the **highest-leverage task given this week's goals**, open items from yesterday, and one socratic question based on a gap in memory. Write it to `daily-brief/{today}.md`.

**Weekly recap** (Fridays, 5pm):
> Read this week's goal file (`weekly/YYYY-WW-goals.md`) and the daily briefs. Honestly assess: did I ship this week's goals? What drifted? What carries over to next week? Write to `weekly/YYYY-WW-recap.md`.

**Memory consolidation (dreaming)** (monthly, 1st at 10am):
> Run the consolidate-memory skill. Merge duplicates, prune stale claims, flag orphan pages, surface topics that now warrant their own file.

Once the core loop is running, consider an **event-driven proactive briefing** task (daily scan for upcoming high-stakes meetings) that auto-drafts pre-reads into a `briefings/` folder. That's the CoS anticipating prep *before* you realize you need it — the force-multiplier signature move.

### HEARTBEAT.md — the reference file

Even though your tasks live in Cowork's scheduled-tasks system (not in HEARTBEAT.md), keep a HEARTBEAT.md file in your workspace as human-readable documentation. It helps you remember what's configured, and it helps the agent when it reads the brain on session start. Example content:

```markdown
# Heartbeat task list (reference)

These are the Cowork scheduled tasks I have configured. Update this
file when you add or change tasks so the agent has an accurate picture.

- **Morning brief** — daily at 8am PT. Writes to daily-brief/YYYY-MM-DD.md.
- **Weekly recap** — Sundays at 5pm PT. Writes to weekly/YYYY-WW.md.
- **Memory consolidation** — monthly, 1st at 10am. Runs consolidate-memory.

## Notes
- These tasks run only when my Mac is awake and Cowork is open.
- Missed tasks re-run on wake (Cowork handles this automatically).
- When I move to the Always-On Edition, these will migrate to
  Claude Routines and this file will become executable configuration.
```

### Deprioritize voice output for v1

You might be tempted to wire up a voice interface so you can talk to your CoS in the car. Resist. Text replies are faster to skim, re-read, and act on; audio replies sound cool for a week and then get turned off. If you want voice input, use your phone's native dictation or Wispr Flow — both work into Cowork's text input. Voice output is a later-phase upgrade, not a v1 priority.

---

## How the system gets smarter

A static memory system is a filing cabinet. A learning one is a colleague. Three distinct mechanisms make the difference:

**Passive accumulation.** The memory grows over time. Each interactive session adds to it. This is table stakes and happens automatically.

**Dreaming (reflective passes).** Periodic passes review the memory itself, look for patterns, propose updates. "You've mentioned three times that your Series B investor is asking about churn — should I make that a standing tracked topic?" This lives inside your weekly and monthly heartbeat tasks and in the `consolidate-memory` skill. OpenClaw calls this "dreaming" — the system processing its day-memory while not in active conversation. The term captures the job better than "reflective learning," so we borrow it.

**Meta-learning about you.** The system tracks which of its suggestions you accept versus ignore, which questions you engage with versus skip, and updates the socratic protocol accordingly. If you never engage with health questions, it stops asking. If you always jump on customer-related gaps, it probes there more often. This lives in `feedback_*.md` files — short memories that encode learned preferences.

Example feedback file content:

```markdown
---
name: Prefer terse responses over summaries
description: User wants responses that are brief and don't recap what was just done
type: feedback
---

When responding, do not end messages with summaries of what was just
accomplished. The user reads the diff and doesn't need a recap.

**Why:** User has told me twice to stop summarizing.
**How to apply:** End responses at the actionable/final point, not with
a "here's what I did" paragraph.
```

These feedback files are read alongside AGENTS.md and shape behavior over time. The longer the system is used, the more tuned to the user it becomes.

---

## What this system does and doesn't do (compared to other agent-learning patterns)

Readers familiar with [OpenClaw](https://openclaw.ai/), RLHF, or other agent-learning frameworks may notice this system deliberately skips one layer: **we don't update model weights**. Everything the agent learns about you and your world lives in *text files loaded into context* at session start, not in the model's parameters.

**What we do — prompt-based, file-based learning:**

- **Passive accumulation.** Memory grows as you work.
- **Dreaming.** Reflective passes where the agent reviews its own notes, surfaces patterns, rewrites AGENTS.md, or creates new feedback files.
- **Meta-learning via feedback files.** Your corrections become short markdown memories that modify future behavior. A correction is a training signal encoded as text, not as gradient.

**What we deliberately don't do — RL-style weight updates:**

- **No fine-tuning of the base model.** We run on hosted Claude; you don't have access to update Claude's weights, and it'd be a bad idea anyway (catastrophic forgetting, compute cost, loss of base capability). OpenClaw-RL works because you can run it on your own open-source model.
- **No training loop or reward model.** No GPU hardware, no training supervisor, no drift monitoring. The whole pitch of this system is low-friction and auditable; RL inverts both.
- **No model-version lock-in.** Because learning is in text files, when Claude upgrades (or you decide to try a different model entirely), your brain comes with you unchanged. A weight-trained agent is locked to its specific model checkpoint.

**Tradeoff stated plainly.** Prompt-based learning is slower and less sophisticated than real RL. You won't get surprising emergent behavior from feedback files. What you get instead is a system whose every behavioral update is **legible** (you can read the file), **revertable** (edit it back or roll the git commit), and **portable** (swap models without starting over). For a personal CoS, that's a better tradeoff than the alternative.

If you eventually want something more RL-shaped, the [OpenClaw-RL](https://openclaw.ai/) project is worth looking at — same file-based foundation, with an optional reinforcement-learning layer on top. This pattern is compatible with OpenClaw's at the file-structure level, so migration is tractable if you change your mind later.

---

## Minimum viable build — session 1 (~90 minutes)

**The full setup checklist below describes the eventual state.** If you do everything on it in one sitting, you'll burn out before you ever use the system. Here's what's actually required to have a working CoS by the end of one focused session. Resist doing more than this on day 1.

| Step | Time | What |
|---|---|---|
| 1 | ~3 min | Open Cowork, create the project, **connect Gmail / Google Calendar / Slack / Docs** (built-in connectors, no code) |
| 2 | ~5 min | Name your CoS |
| 3 | ~45 min | USER.md interview (skip writing samples for now if you don't have any handy) |
| 4 | ~20 min | SOUL interview (derivative of USER, faster) |
| 5 | ~5 min | Populate `## Facts` preamble at the top of SOUL.md |
| 6 | ~2 min | Paste socratic protocol into AGENTS.md |
| 7 | ~5 min | Create MEMORY.md index |
| 8 | ~5 min | Create TODOS.md with the 5 buckets, seeded with 3-5 things you already know need doing |
| 9 | ~3 min | Create HEARTBEAT.md as a stub (lists the heartbeats you'll configure later) |
| 10 | ~5 min | Configure ONE Cowork scheduled task — the morning brief |
| 11 | ~3 min | **Wire the brain to auto-load** — paste loading instructions into Cowork → Project settings → Instructions (see "Wire the brain" section below) |
| **Total** | **~101 min** | **Working CoS. Morning brief fires tomorrow. Stop here.** |

**Defer to later sessions** — these are NOT session-1 requirements:

- Domain files (`company.md`, `team.md`, `coaching.md`, etc.) — emerge as content accumulates over the first weeks. Don't seed empty.
- The other 3 heartbeat tasks (weekly goal-set, weekly recap, monthly consolidation) — add over the following days, not all in one batch.
- `north-star.md`, `priorities.md`, year files — wait for a deliberate destination probe (a 30–60 min conversation, usually in week 2).
- Refining AGENTS.md beyond the pasted protocol — wait for the system to surface what needs adjusting.

The most common failure mode at this stage is over-engineering before the system is real. Do the 11 steps above. Use it for a week. *Then* build more.

---

## Wire the brain to auto-load (one-time setup)

Cowork does **not** auto-load workspace files into new conversations. Without this step, every new chat in your workspace starts blind — no `todos.md`, no `SOUL.md`, no context. You'll re-explain yourself constantly.

Paste this into **Cowork → Project settings → Instructions** for the workspace:

```
This workspace is your chief of staff. The brain lives here as a stack of markdown files.

At the start of every new conversation, read these files in order:
1. SOUL.md — your persona, voice, values.
2. USER.md — who I am, my goals, failure modes, communication style.
3. AGENTS.md — operating rules. One question at a time.
4. MEMORY.md — index of every other file in the brain.
5. todos.md — source of truth for active work.

When I ask "what's my todo list" or "what should I do next" — read todos.md first. Never say "I don't have a todo list source" — todos.md IS the source.

Voice: direct, simple, sincere, candid. Casual register. Never "great question," "I'd be happy to help," or trailing summaries.
```

Now every conversation in this workspace starts with full context.

---

## Setup checklist (the full eventual state)

The complete picture, from blank slate to a fully fleshed-out CoS. **Don't try to do all of this in one session** — see "Minimum viable build" above. This is the menu of what eventually exists, not a session-1 to-do list.

1. **Choose or create a folder** on your Mac — e.g. `~/chief-of-staff`. This becomes your Cowork workspace folder.
2. **Open that folder** as your Cowork workspace.
3. **Connect your tools.** In Cowork, wire up Gmail, Google Calendar, Slack, and Google Docs via the built-in connectors. No code, no terminal — just OAuth flows. The CoS uses these to read your real schedule, your real correspondence, your real working context. Without connectors it's a clever filing cabinet; with them it's a chief of staff.
4. **(Optional but recommended) Open the same folder as an Obsidian vault.** Obsidian makes editing the markdown files nicer than other editors.
5. **Set up a backup.** Either point the folder at iCloud/Dropbox, or plan a weekly manual backup. Without git, you're vulnerable to laptop failure.
6. **Name your chief of staff.** This is the OpenClaw pattern: naming turns the agent from "an assistant" into a distinct entity you collaborate with. Short, meaningful, easy to say aloud. This becomes the name used in SOUL.md.
7. **Do the USER.md interview — this is the foundational one.** 45-60 minutes. The agent asks about your role, focus, values, decision-making style, communication preferences, key relationships, history. Near the end, it offers to analyze writing samples (tweets, posts, emails, memos) to nail your voice — drop them in a `data/` subfolder or paste into the chat. Do not rush this; every other file in the system benefits from a rich USER.md.
8. **Do the SOUL interview.** 20-30 minutes, informed by USER.md. Faster than USER because SOUL is derivative — once the agent knows who you are, most persona decisions are narrow inferences ("given you hate hedging, should I hedge?") rather than open questions. Populate the `## Facts` section at the top of SOUL.md with the factual scaffolding (name, principal, current stage, substrate, load order, setup date) as part of this step — the factual material is short and naturally co-locates with the persona content.
9. **Paste the socratic protocol into AGENTS.md** and edit to taste.
10. **Create the MEMORY.md index** — point at the files you've created so far.
11. **Create an initial HEARTBEAT.md** as a reference file listing the tasks you'll configure next.
12. **Create an initial TODOS.md** with the five buckets (Inbox / Active / Soon / Parked / Done). Empty buckets are fine; the structure is what matters. Active starts seeded with 2-5 things from the SOUL/USER interview that you already know need doing.
13. **Set up one Cowork scheduled task** via `/schedule` — the morning brief is a good first one.
14. **Use it for a week.** Don't refine the architecture. Just use it. Capture context as you work. Answer the agent's socratic questions. Capture todos liberally to Inbox.
15. **Reflect and adjust.** After a week, read what the system has captured. Adjust AGENTS.md based on corrections. Add or split domain files as groupings emerge. Audit TODOS — is Active too big? Is Inbox triaged?

---

## File skeletons — what your CoS interviews toward

These are structural shapes each file should take, not forms for you to fill in. If you find yourself typing content into blank brackets by hand, you're probably doing it wrong — have your CoS interview you instead. The agent reads these templates to know what structure to target during the conversation.

Each file below is tagged with how it gets populated:
- **Interview-generated** — agent asks questions, content emerges from the conversation
- **Template + edit** — you paste the template and edit to taste
- **Auto-maintained** — the agent updates the file itself as things change
- **Task configuration** — configured via UI or YAML, not interview

### SOUL.md — interview-generated

This file defines your CoS as an entity — their persona, not yours. Generated through a **20-30 minute interview** where the agent asks about voice, values, posture, how it handles disagreement and uncertainty. Relatively quick because SOUL is *derivative* of USER — once USER.md is populated, many SOUL decisions become inferences from who you are rather than open questions. Written in the agent's voice ("I am..."), not yours.

```markdown
# SOUL

I am [agent's name]. I am the chief of staff for [principal's name].

## My role
[One paragraph describing what kind of CoS I am. A trusted operator? A
sharp skeptic? A steady sounding board? A blunt second opinion?
Specific, not generic.]

## What I value
- [3-5 things this agent holds as non-negotiable in how it shows up]
- [Not the user's values — the agent's operating principles]

## My voice
- [How I communicate. Short sentences? Long? Direct? Wry? Formal? Casual?]
- [Words or phrases I use. Words I never use.]
- [How I sign off. How I open.]

## How I handle disagreement
- [Do I push back immediately, or hold and watch? How hard? What's my
  posture when the principal and I see things differently?]

## How I handle uncertainty
- [Do I caveat, guess, or ask? When do I say "I don't know"?
  When do I volunteer speculation?]

## My relationship with the principal
- [How do I address them? What can I assume about them?
  What should I never assume? What's my default posture — deferential,
  peer, or challenging?]
```

### The `## Facts` section (top of SOUL.md)

Short factual scaffolding that lives at the top of SOUL.md, above the persona content. Replaces what was a separate IDENTITY.md file in the original OpenClaw stack. Populated as part of the SOUL interview.

```markdown
# SOUL

## Facts

- **Name:** [agent's name] — current stage is [e.g., Kubrick 1000].
- **Principal:** [your name + email].
- **Role:** Chief of staff. Navigator (strategic) and operator (tactical). See below.
- **Current substrate:** Cowork Desktop Edition, following `v1-desktop.md`.
  Brain lives in this workspace folder; heartbeats fire as Cowork scheduled tasks.
- **Evolution arc:** [if you're planning a multi-stage build like Kubrick 1000 → 9000,
  sketch it here]. Migrations are additive — SOUL, USER, domain files, and memory
  content carry forward unchanged; only the substrate changes.
- **File load order at session start:** SOUL.md → USER.md → AGENTS.md → MEMORY.md → relevant domain files.
- **Public / private posture:** [which files stay private, what gets shared].
- **Setup date:** [YYYY-MM-DD].

---

## [persona content below — see SOUL skeleton above]
```

### USER.md — interview-generated

This file is who *you* are — the principal the agent serves. **This is the foundational interview of the whole setup — 45-60 minutes, the longest single session.** The agent asks about your role, your current focus, your values, your decision-making style, your communication preferences, your key relationships, your history with building things, your strengths and fears. USER is rich because you are; SOUL downstream is quick because the decisions are narrow once USER is populated.

Do this one properly. Don't rush it. A thin USER.md means a thin CoS.

**Writing samples (optional but high-leverage).** Toward the end of the USER interview, the agent will ask if you have writing samples you can share — tweets, LinkedIn posts, investor updates, memos, essays, Slack messages. Voice is hard to describe and easy to show, so samples let the agent extract patterns your self-report would miss (sentence length, cadence, vocabulary, sign-offs, rhetorical moves). Drop files into a `data/` subfolder in your workspace, or paste URLs/content into the conversation. The agent reads the samples, extracts patterns, and folds them into USER.md's voice section. Samples can stay in `data/` as reference for future drafting work (if you ever ask your CoS to draft something *in your voice*, it consults them).

```markdown
# USER

## Who I am
[Name, role, what I'm building. One paragraph. Specific and
identifiable, not generic.]

## What I care about
- [3-5 specific things. My values. What I won't compromise on.]

## How I make decisions
- [Fast or slow? Solo or consensus? Gut or analysis?]
- [What's my bias when I'm tired or stressed?]

## My communication style
- [Terse. Direct. Don't summarize. Push back when I'm wrong.
  Whatever's true for you.]
- [Words you love. Words you hate.]

## Current focus
- [This quarter's priorities. 2-3 items max.]

## Key relationships
- [Co-founders, direct reports, board members, key investors —
  one line each, pointing to their own files if they have one]

## Current projects
- [What I'm actively building or operating right now]

## What I want from my chief of staff
- [What would make this system valuable to me]
- [What would make me turn it off]
```

### AGENTS.md — template + edit

[Use the socratic protocol content from the section above. Paste it and edit to taste — no interview needed for a rulebook.]

### MEMORY.md — auto-maintained (the starter below is just for initial population)

```markdown
# MEMORY index

## Core files
- [SOUL.md](SOUL.md) — persona, values, and factual self-description (Facts section at top)
- [USER.md](USER.md) — context about the user
- [AGENTS.md](AGENTS.md) — operating rules
- [HEARTBEAT.md](HEARTBEAT.md) — scheduled task reference
- [TODOS.md](TODOS.md) — operational task layer (Inbox / Active / Soon / Parked / Done)

## Domain files
- [company.md](company.md) — the company at a glance
- [team.md](team.md) — team members and dynamics
- [priorities.md](priorities.md) — current-quarter focus
- [preferences.md](preferences.md) — working style

## Feedback files
- [feedback_*.md] — learned behavioral preferences
```

### HEARTBEAT.md — task configuration

[Use the reference-file example from the heartbeat section above. In this edition, HEARTBEAT.md is human-readable documentation of the tasks you've configured via Cowork's `/schedule` UI — the tasks themselves live in Cowork, not in the file. Deciding *which* tasks to run is a brief conversation with your agent; the file itself is documentation.]

### TODOS.md — primitive structure + skeleton

```markdown
# Todos

*The single source of "what's the next concrete thing." Todos are a first-class
primitive — alongside SOUL, USER, AGENTS, MEMORY. Last updated YYYY-MM-DD.*

## Schema (markdown convention; structured later when querying matters)

- [ ] [t-descriptive-kebab-id] **Title** — parent: <goal-or-file>, due: YYYY-MM-DD
  Notes / context if useful.

## Five buckets

| Bucket | Catches | Triage cadence |
|---|---|---|
| **Inbox** | Anything just captured. Lowest friction. | Daily brief flushes each morning. |
| **Active** | Committed for this week. ≤7 hard cap. | Daily brief surfaces today's pick. |
| **Soon** | Triaged; queued for promotion. | Weekly recap reviews. |
| **Parked** | Idle by intent. Not lost; not committed. | Monthly consolidation prunes stale. |
| **Done** | Last 14 days. Proof of motion. | Auto-rolls off after 14 days. |

## Two disciplines, opposite forces

- **Capture friction LOW** — never push back on a capture. Inbox catches anything.
- **Promotion friction HIGH** — Active is sacred. Moving anything to Active
  requires a deliberate trade. The CoS never auto-promotes.

## Inbox

- [ ] [t-...] ...

## Active — doing this week

- [ ] [t-...] **...** — parent: <goal>, due: ...

## Soon

- [ ] [t-...] ...

## Parked

- [ ] [t-...] ...

## Done (rolling 14 days)

- [x] [t-...] **...** — completed YYYY-MM-DD
```

**Threading:** Domain files can hold their own "Open todos" sections inline (where the todo was born). TODOS.md is the *aggregated view* — the CoS keeps it in sync with the inline lists. Coaching sessions, meeting briefings, and heartbeats all produce todos.

**Stress signals to surface:**
- Active > 7 → focus has slipped or week's commitment grew. Surface; don't auto-prune.
- Inbox > ~10 untriaged → "quick triage round?" in next morning brief.

---

## Privacy

### The brain stays private. The pattern goes public.

Adopt the Karpathy model: share the **pattern**, not the **wiki**. Your CoS's brain — USER.md, SOUL.md, domain files, memory, weekly goals, daily briefs — stays local and private. **Encourage gory detail in the brain**: client names, investor dynamics, family specifics, financial reality, relationship nuance, numbers, dates. The brain only works if it's accurate; self-censorship makes it less useful, and there's no downside because it doesn't leave your machine.

What gets shared publicly (if you want to build in public):
- The **playbook / blueprint** (this document, future v2-always-on.md, decision narratives).
- **Essays about the journey** — "How I built my CoS in Cowork," "What changed after a month of using it," "The trade-offs I navigated." Reflection content, not brain dumps.
- A **template starter repo** with placeholder content (empty USER.md skeleton, AGENTS.md socratic protocol, etc.) for others to fork.

If you're not building in public, just keep the brain private — same architecture, no sharing surface. The pattern still works.

### File-level privacy

Since this edition stores everything locally, privacy is straightforward: your files never leave your Mac. No GitHub, no cloud sync unless you opt into iCloud or Dropbox for backup.

If you do use iCloud/Dropbox for backup, know that your notes are going to Apple's or Dropbox's servers (encrypted at rest, but accessible to those companies under legal process). For most founder content this is fine. If specific domains are highly sensitive — detailed health records, deeply personal journaling — you can:

- Keep sensitive domains in a subfolder that's excluded from cloud sync (iCloud supports "Desktop & Documents Folders" selectivity; Dropbox has "selective sync")
- Use an encrypted disk image (macOS: Disk Utility → New Image) for your workspace folder if you want strong local encryption

Draw the line where you're comfortable. Most founders land on "private GitHub later, iCloud backup now" and that's usually fine.

---

## When you outgrow this — upgrade to Always-On

You'll know it's time for the Always-On Edition when:

- Your laptop is asleep when important heartbeats should fire, and you keep missing them
- You want to chat with your CoS from your phone without your desktop being awake
- You want to access the same brain from multiple machines
- You want a true 24/7 morning brief regardless of your sleep schedule

The Always-On Edition runs your heartbeats as **Claude Routines** on Anthropic-managed cloud infrastructure. Routines support scheduled triggers (cron-like), API triggers (HTTP POST with bearer token), and GitHub-event triggers. As of April 2026, Routines is in research preview, and per-day usage is capped by plan: **Pro 5/day, Max 15/day, Team/Enterprise 25/day**. The 4 core heartbeat tasks fit comfortably under all of these.

The migration is **additive, not a rewrite**. Every file you've built stays exactly as it is. The upgrade adds:

1. `git init` in your workspace folder and push to a new private GitHub repo (Routines pull from a repo).
2. Install the Obsidian Git plugin for auto-commit and auto-push (so your local edits show up in the repo Routines reads from).
3. Set up one Claude Routine using your existing HEARTBEAT.md content as the prompt; configure the schedule trigger to match.
4. Start using claude.ai/code in your phone browser for mobile chat.

Your SOUL, USER, AGENTS, domain files, and memory content — all preserved. The Always-On Edition is strictly an infrastructure upgrade; the pattern you've learned here is exactly the pattern you'll keep using.

See `v2-always-on.md` for the full Always-On setup guide.

---

## Future scale-ups (parked)

Don't build any of these until you've lived with the Desktop Edition for at least a couple of weeks.

- **qmd for local markdown search.** Once your vault hits ~100 pages and index-level navigation starts feeling dumb, [qmd](https://github.com/tobi/qmd) is Tobi Lütke's on-device markdown search engine — hybrid BM25/vector, both CLI and MCP server. Drops in cleanly.
- **Always-On Edition** (Claude Routines on Anthropic cloud). See above. The next step when desktop-tethered availability stops being enough. Always-on, scheduled / API / GitHub triggers, brain in a private GitHub repo. Plan-capped usage (Pro 5 / Max 15 / Team-Enterprise 25 routines per day).
- **Self-Hosted Edition** (VPS + Claude Agent SDK). Always-on came at the previous edition; this one is about **runtime control**: custom MCP integrations, no managed-service dependency, escape from per-day routine caps, custom messaging surfaces (Slack, Telegram, etc.), multi-agent routing, team-scale use. Bigger lift, more freedom.

---

## Lineage and credits

This pattern didn't come from nowhere. The relevant threads:

- **Andrej Karpathy's LLM Wiki** ([gist](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f)) originated the pattern of LLM-maintained markdown knowledge bases. This guide deliberately departs from Karpathy's source-ingestion model in favor of a context-capture model, but the underlying file-based philosophy is his.

- **OpenClaw** ([openclaw.ai](https://openclaw.ai)) contributed the concrete architecture: SOUL.md / IDENTITY.md / USER.md / AGENTS.md / MEMORY.md / HEARTBEAT.md as a first-class file stack. Much of this guide is the OpenClaw stack adapted to a Cowork environment.

- **Aaron J. Mars's soul.md project** ([github.com/aaronjmars/soul.md](https://github.com/aaronjmars/soul.md)) is a canonical reference for SOUL-style files. (Note: his project puts the user's soul in SOUL.md, because his use case is agents that embody the user. For a chief of staff, the pattern inverts — SOUL is the agent, USER is the principal.)

- **Tobi Lütke's qmd** ([github.com/tobi/qmd](https://github.com/tobi/qmd)) is the search tool Karpathy references and what you'll want when the vault scales.

---

## If you're an AI agent reading this in a fresh workspace

If a user has dropped this document into a new Cowork workspace and said "let's build this," here's your job:

1. Read this whole document first, paying particular attention to the "Before you start: requirements" section.
2. Verify the user has Cowork running, a workspace folder chosen, and ideally Obsidian for editing. If anything is missing, walk them through setup before proceeding.
3. **Walk them through connecting Cowork's built-in connectors — Gmail, Google Calendar, Slack, Google Docs.** This is non-optional. Without connectors the CoS only sees the markdown files; with them it sees the user's real inbox, real schedule, real correspondence. The whole "force multiplier" claim depends on this. If the user resists, ask which one would unblock the most value (almost always Gmail or Calendar) and start there; you can add the rest later.
4. **Walk them through pasting the Cowork project Instructions** that auto-load the brain on every new conversation (see "Wire the brain to auto-load" section above). Without this, every fresh chat in the workspace is blind to SOUL/USER/AGENTS/TODOS.
5. Start by asking the user to name their chief of staff — this is the OpenClaw pattern and it's load-bearing for everything else.
6. Do the USER.md interview next — **this is the foundational one, 45-60 minutes**. Ask about role, current focus, values, decision-making style, communication preferences, key relationships, history, strengths and fears. Take your time. A thin USER.md means a thin CoS across every subsequent file. Save it to USER.md as you go. **Near the end of the interview, ask if the user has writing samples you could analyze to learn their voice** — tweets, LinkedIn posts, investor updates, memos, essays. They can paste content/URLs or drop files into a `data/` subfolder. Read what they provide, extract voice patterns (sentence length, cadence, vocabulary, sign-offs, rhetorical moves), and fold findings into USER.md's voice section. If the user doesn't want to share samples, continue without — it's optional.
7. Then do the SOUL interview — **20-30 minutes, informed by USER.md you just wrote**. Ask about the agent's voice, posture, how it handles disagreement and uncertainty. Most SOUL decisions are narrow inferences from USER — don't re-ask things already established (e.g. if USER said they hate hedging, your SOUL question isn't "should I hedge?" but "should I explicitly contrast that by flagging uncertainty openly, or match the user's no-hedge posture?"). Save to SOUL.md.
8. Populate the `## Facts` section at the top of SOUL.md (name, principal, stage, substrate, load order, public/private posture, setup date). Then paste the socratic protocol into AGENTS.md.
9. Help the user create the MEMORY.md index, an initial HEARTBEAT.md reference file, and an initial TODOS.md with the five buckets (Inbox / Active / Soon / Parked / Done). Seed Active with 2-5 things from the SOUL/USER interview that already need doing.
10. Walk them through creating one Cowork scheduled task via `/schedule` (the morning brief is a good first one).
11. Stop. Encourage them to use the system for a week before refining.
12. Use the socratic protocol in AGENTS.md as your operating rules throughout. Do not front-load the user with questionnaires. One question at a time, in natural flow.

### Lessons baked in (from the first build of this pattern, 2026-04-27)

These are corrections / reinforcements from running this protocol end-to-end with a real principal. Hold them as load-bearing:

- **One question per turn. Strictly.** Not "here are the altitudes, pick some." Not compound questions with "or." Even when sub-parts feel naturally bundled (week / quarter / year / 3-5 year / north star), ask them serially across multiple turns. The temptation to bundle is strong; resist it. If the user has to disambiguate your question, you've already failed.
- **Encourage gory detail in the brain.** When the principal gives a vague answer, push for specifics — names, numbers, dates, dynamics. The brain is private; vagueness only hurts utility. Example: "wife runs a beauty startup" is OK; "wife Karen runs OTP, helps me with leadership-dev questions weekly, may be a customer for one of my products" is far more useful.
- **The destination probe (north-star.md and priorities.md) is best run as an altitude descent.** Start with the north star (broadest), then 3–5 year picture, then the year, then the quarter, then the week. Each altitude downstream is informed by the one above it. Save to north-star.md → 2026.md (or year file) → priorities.md → weekly/YYYY-WW-goals.md as you go.
- **Preserve the user's voice verbatim.** When the principal says "I wake up fucking stoked" or "from me things grow" or "I feel it in my bones," those phrasings *are* signal. Quote them, don't sanitize them. Your synthesis goes in your own paragraphs; their words go in block quotes or bullet lists.
- **Failure modes are early-warning signals, not just lifestyle metrics.** When the principal answers "what do you do when stressed?" with things like "skip the gym, eat poorly, doomscroll, stay up late" — these become your dashboard. When you see the pattern, surface it. Don't scold; just reflect.
- **Watch for the values architecture that's hiding in the answers.** Values often stack (e.g. protect → choose → operate, in the first build). When you see the structure, name it back to the user briefly. They usually can't see it themselves.
- **When the user pushes back on a SOUL or framing decision, fold it in fast and don't litigate.** Their pushbacks are gold — they're telling you exactly where the agent is mis-tuned. Update the file, note the correction in feedback memory if it's durable, move on.
- **The architecture will tempt you to over-engineer. Resist.** New domain files only when content has accumulated. New rules only when corrections have repeated. Keep MEMORY.md as an index, not a memory itself.
- **Treat TODOS as a primitive, not a side effect.** When the user asks "where do todos live?", don't bury them in a domain file or treat them as a HEARTBEAT byproduct. They get their own file (TODOS.md), their own buckets, their own discipline. Two opposite forces matter: **capture friction LOW** (never push back on a capture; the user *loves* to catch things, that's a feature) and **promotion friction HIGH** (Active stays ≤7 — moving anything to Active requires a deliberate trade). The size of Active and the depth of Inbox are both signal: a sprawling Active means focus has slipped; a stuffed Inbox means triage isn't happening.

---

## One last thing

You will be tempted to perfect the architecture before you start using it. Resist. Every founder who built a perfect note system that no one used did so by optimizing the architecture before the behavior was real. Get a SOUL, a USER, a thin AGENTS, and one scheduled task. Use it for a week. The system will tell you what it's missing.
