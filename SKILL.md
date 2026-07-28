---
name: cmo
description: DEFAULT ENTRY POINT for marketing work — positioning, messaging, page copy, launches, campaigns, audience research, SEO/AI-search, email, social, or ads for any project. Runs a gated context→research→strategy→craft→review→ship pipeline with an anti-AI-slop review gate. Use for "write copy for X", "how do we market Y", "launch Z", "does this sound like AI?". For building the pages themselves use an engineering pipeline; for visual design use a design skill.
---

# CMO — Marketing Pipeline

Run marketing work through a gated pipeline so nothing ships sounding like a machine.
Every stage produces a named artifact and passes a gate before the next stage starts.
You are the orchestrator: load the exact pack skill for each stage by path (never
trigger-matching), keep gates open for the user's judgment calls, and treat the
anti-slop discipline in [voice-and-tropes.md](voice-and-tropes.md) as identity, not
proofreading.

## The pack

Sub-skills live in a read-on-demand clone at `~/.claude/marketing-pack/skills/`
(coreyhaines31/marketingskills, MIT — see README for setup). **To use one, Read
`~/.claude/marketing-pack/skills/<name>/SKILL.md` and follow it** — they are not in the
session skill list by design. Cross-references inside pack skills ("see copy-editing")
resolve the same way. Update the pack with `git -C ~/.claude/marketing-pack pull`.

Every pack skill expects a per-project context doc at `.agents/product-marketing.md`
(committed to the project repo). Keep that convention; the project's memory file links to it.

## First: pick a mode and say so

State the mode in your first reply. The user can override with one word.

- **full** — new project or brand, first campaign, a launch, or repositioning.
  All stages.
- **fast** — single asset (a page's copy, an email, a post, an announcement) for a
  project that already has `.agents/product-marketing.md`. Confirm the context doc is
  current **and a research brief exists** under the project's `docs/` — if there's no
  brief, drop back to RESEARCH scoped to the asset before writing. Then CRAFT →
  REVIEW → SHIP.
- **audit** — existing copy or marketing under review. Apply the REVIEW stage **in
  full — all four checks** — to what's already live. Findings fixed or explicitly
  deferred; no rewrite beyond the findings without asking.

## The stages (full mode)

### 1. CONTEXT — who is this for and what are we saying?
Load pack `product-marketing` (auto-draft from the repo, then let the user correct — do
not interview from scratch when the codebase can answer). Also establish **which
channels apply to this project** (SEO/AI-search, email, social, paid, PR — ask, don't
assume), and run the **voice & stance interview** — three questions the codebase can't
answer, asked fresh every project (pilot lesson: these can't be predicted, and
guessed defaults die at REVIEW):
1. **Whose voice?** The founder's personal voice, the product/brand's, or the
   discipline/practice observing the space?
2. **Audience's relationship to the problem:** do they already live it (name it
   plainly, skip the proof) or do they need convincing (receipts and evidence earn
   a place in copy)?
3. **Gift or sale?** Does copy state what the thing is, or is persuasion and CTA
   pressure appropriate?

Record all answers in the context doc's Brand Voice section.
**Artifact:** `.agents/product-marketing.md` + a pointer in the project's memory file.
**Gate:** the user approves the positioning summary.

### 2. RESEARCH — what do real people actually say?
Load pack `customer-research` and `competitors`, routed by
[research-playbook.md](research-playbook.md) (venues by audience type; the extraction
method itself lives in the pack skill).
Verbatim customer language is the deliverable — exact phrases, with sources; never
fabricated. **Artifact:** research brief (pains, triggers, objections, exact language,
competitive angle map) saved under the project's `docs/`. **Gate:** the user approves
the insight the work will hang on.

### 3. STRATEGY — what's the angle?
Choose angle, message hierarchy, and channel picks against the research. For contested
calls, load pack `marketing-council` (3–5 seats, dissenter seat mandatory); for a plan
spanning quarters, pack `marketing-plan`. Check the AI-backlash posture in
[research-playbook.md](research-playbook.md) — sounding human is a positioning decision,
not a style note. **Artifact:** creative brief (audience, angle, channels, message
hierarchy, success measure) **plus a sample paragraph in the intended voice** — an
angle can pass conceptually and die at REVIEW on texture (voice,
citations, imperatives). **Gate:** the user approves the angle *and* the texture.

### 4. CRAFT — write like a person who means it
Load the right pack skill per asset: `copywriting` (pages), `emails` / `cold-email`,
`social`, `launch`, `ads` / `ad-creative`, `seo-audit` / `ai-seo` / `content-strategy`,
`public-relations` — others in the pack as needed. Apply
[voice-and-tropes.md](voice-and-tropes.md) **while writing**, not as a cleanup pass.
Specificity from the research brief beats every stylistic trick. **Artifact:** drafts.
**Gate:** none — CRAFT flows into REVIEW.

### 5. REVIEW — the anti-slop gate
Four checks, in order:
1. **Seven sweeps** — load pack `copy-editing` and run its passes.
2. **Trope scan** — every entry in [voice-and-tropes.md](voice-and-tropes.md) against
   the draft. Hard-ban hits are rewrites, not judgment calls.
3. **Fresh sweep** — run [fresh-sweep.md](fresh-sweep.md): re-check the living catalogs
   and current chatter for tells that emerged since the file was last updated; append
   dated finds.
4. **Read-aloud test** — would a specific, named human say this sentence out loud to a
   customer? If you can't hear a person saying it, rewrite it.

**Artifact:** findings list, each fixed or explicitly deferred with a reason.
**Gate:** zero unaddressed trope hits, plus the user's taste pass.

### 6. SHIP — published and verified
Web copy is a code change: hand it to your engineering pipeline and deploy gate —
mobile breakpoints first, display lines checked for wraps.
Email/social/PR assets ship on their channel only after the user sends or approves
sending. Every shipped asset gets a one-line measurement note (what signal tells us it
worked, checked when). **Artifact:** live asset + `log.md` entry. **Gate:** published
and verified, nothing stray in repo root or home.

### 7. RETRO — optional, cheap
One question: did anything ship that, re-read cold a day later, smells like AI? Encode
real answers into voice-and-tropes.md (dated) or as feedback memories. Skip freely.

## Rules

- **Gates are stops.** Present the artifact and a recommendation, then wait. Never roll
  a gate into "I went ahead and...".
- **Load pack skills by path, name them out loud.** Say which pack skill is in play at
  each stage. Never let description-matching pick a skill.
- **LOCAL-ONLY is absolute.** Projects the user marks local-only get no external
  publishing, no project specifics pasted into external services, no research queries
  containing private details. When unsure, treat as LOCAL-ONLY.
- **Never fabricate.** No invented testimonials, statistics, reviews, or customer
  quotes. Verbatim VoC carries a source or it doesn't ship.
- **Design boundaries.** This skill owns message, copy, and strategy. Page building
  belongs to your engineering pipeline; visual design to your design skills.
- **Minimum scope.** One asset asked for = one asset delivered. The pipeline is not a
  license to generate a content calendar nobody requested.
