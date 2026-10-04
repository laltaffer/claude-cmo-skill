---
name: cmo
description: Marketing pipeline (context, research, strategy, craft, review, ship, operate) for positioning, copy, launches, campaigns, SEO and AI search, email, social, and paid ads, including operating a live ad account. User-invoked only; type /cmo.
disable-model-invocation: true
---

# CMO — Marketing Pipeline

Run marketing work through a gated pipeline so nothing ships sounding like a machine.
Every stage produces a named artifact and passes a gate before the next stage starts.
You are the orchestrator: load the exact pack skill for each stage by path (never
trigger-matching), keep gates open for the user's judgment calls, and treat the
anti-slop discipline in [voice-and-tropes.md](voice-and-tropes.md) as identity, not
proofreading. Writing runs from a brief; review is a standalone checklist,
[review.md](review.md), that runs on any copy, drafted or live.


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
  Stages 1–6 and 8; OPERATE only if it leaves behind something that keeps spending.
- **fast** — single asset (a page's copy, an email, a post, an announcement) for a
  project that already has `.agents/product-marketing.md`. Confirm the context doc is
  current by spot-checking its verbatim customer language and proof points against
  the live site (a stale entry is a finding to fix in the doc, never copy to reuse),
  **and that a research brief exists** under the project's `docs/` — if there's no
  brief, drop back to RESEARCH scoped to the asset before writing. Then BRIEF →
  WRITE → REVIEW → SHIP.
- **audit** — existing copy or marketing under review. Run [review.md](review.md)
  **in full** on what's already live. Findings fixed or explicitly deferred; no
  rewrite beyond the findings without asking.
- **engagement** — an existing business as a client, not a 0→1 project. Open with the
  constraint grill in [operate.md](operate.md): find where the business is actually
  constrained, then let evidence decide which stages this engagement needs. No stage is
  skipped or run by default — deciding that in advance is how you either bill them to
  rediscover what they know or build on a belief they can't support. Ends in OPERATE.

## The stages

Full mode runs 1–6 and 8. **OPERATE (7) is conditional** — it runs whenever the work
leaves behind something that keeps spending money after launch, and it is where
`engagement` mode both starts and ends: that mode enters at OPERATE's constraint grill
to decide which of stages 1–6 this client actually needs, runs the ones that survive
scoping, then returns to the OPERATE loop and stays there.

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

### 4. BRIEF, then WRITE — constraints first, then a person who means it
Write the copy brief before the draft, one page: the audience and the moment they meet
this asset (the query they typed, the inbox, the feed); the angle and message hierarchy
from STRATEGY or the creative brief; the must-say facts, each with its source; the
verbatim customer language to reuse; the banned territory (the context doc's words to
avoid, the hard bans, anything the user has rejected on this project); the format (the
template's blocks, the channel's lengths, the one CTA and its exact label); and what
done means. State the brief in the reply so the user can redirect it in one line. Then
write from it. Load the pack skill for the asset type by path for the channel's
mechanics and formats: `copywriting` (pages), `emails` / `cold-email`, `social`,
`launch`, `ads` / `ad-creative`, `seo-audit` / `ai-seo` / `content-strategy`,
`public-relations`, others as needed. The brief, not the pack skill, carries what the
copy must say. Apply [voice-and-tropes.md](voice-and-tropes.md) **while writing**, not
as a cleanup pass. Specificity from the research brief beats every stylistic trick.
**Artifact:** brief + draft. **Gate:** none — WRITE flows into REVIEW.

This order is measured, not assumed. In the 2026-09-15 ablation, three drafts of one
landing page (a bare model with a one-page brief, the loaded stack without this
pipeline, and this pipeline) came out with the same skeleton, CTA, and testimonials;
brief specificity and the review checks separated them, the stage choreography did not.

### 5. REVIEW — the anti-slop gate
Run [review.md](review.md): the mechanical checks, fact sourcing in both directions,
the trope scan, the seven sweeps, the fresh sweep, and the read-aloud test, then
judgment labeled as judgment. The review reports; this stage applies. Verdict line
first.

**Artifact:** findings list, each fixed or explicitly deferred with a reason, with the
mechanical checks re-run after the fixes.
**Gate:** zero unaddressed hard-ban hits or unsourced facts, plus the user's taste pass.

### 6. SHIP — published and verified
Web copy is a code change: hand it to your engineering pipeline and deploy gate —
mobile breakpoints first, display lines checked for wraps.
Email/social/PR assets ship on their channel only after the user sends or approves
sending. Every shipped asset gets a one-line measurement note (what signal tells us it
worked, checked when). **Artifact:** live asset + `log.md` entry. **Gate:** published
and verified, nothing stray in repo root or home.

A live ad account does not stop here. It has no ship date, only an operating loop that
bills the client daily — hand it to OPERATE.

### 7. OPERATE — the account keeps spending after you ship
Live ad accounts, and anything else that costs money after launch. Load
[operate.md](operate.md) and run its loop: constraint grill → scoped plan → baseline
audit → authority tiers → derived cadence → one-page reports that each end in a
decision. The pack `ads` references own every threshold and platform fact; operate.md
owns the engagement — intake, authority, cadence, reporting, exit. **Artifact:**
standing engagement record + append-only change log. **Gate:** constraint diagnosis and
scoped plan approved before account access; Red-tier actions need written client
authorization every time.

### 8. RETRO — optional, cheap
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
- **Client money is a separate gate.** OPERATE is the only stage that spends someone
  else's budget continuously, and it's the only place a gate can't be cleared by anyone
  in this conversation. The user's approval moves the engagement; it does not authorize
  a change to a live account. Red-tier actions in [operate.md](operate.md) need written
  authorization from someone at the client who can approve spend, every time, and absent
  an explicit tier agreement everything is Yellow.
