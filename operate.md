# OPERATE — the account keeps spending after you ship

Every other CMO stage ends. This one doesn't. A landing page ships and sits there; an ad
account bills the client every day you don't look at it. OPERATE is the loop that runs
from "campaigns are live" until the engagement ends, and it is the only stage where
being slow costs the client money in real time.

Load this at SHIP when the asset is a live ad account (Google Ads, Meta, LinkedIn), or
any time you inherit an account that's already running.

**This file owns the engagement: intake, authority, cadence, reporting, exit.** It owns
no thresholds and no platform facts. Account structure, match types, negatives, bidding,
and the weekly search-terms ritual live in pack `ads` →
`references/google-search-playbook.md`. Audit scoring, benchmark discipline, and hard
stops live in `references/audit-guardrails.md`. Channel affordability lives in
`references/payback-period.md`. **Load them; never restate their numbers here.**

---

## 1. Entry: the constraint grill

Do not open the account first. Do not run RESEARCH first. The first job is finding out
whether paid media is the answer at all, and what this particular business does and
doesn't already have — that's what sets scope in §2.

Invoke the `grilling` skill and work its design tree in rounds. Two adaptations for
client engagements:

**Get numbers from the systems, decisions from the client.** Grilling already says
finding facts is your job — for an existing business the "environment" is their ad
account, GA4, CRM, search-terms report, and site. This isn't a claim that clients are
unreliable; it's that the terms are genuinely ambiguous. "CAC" means blended or
channel-level depending on who's saying it, "conversions" means platform-attributed or
CRM-confirmed, and attribution windows differ between the two systems a client is
reading. A number that's wrong at intake compounds through every decision after it, and
the account is the cheaper source anyway.

Ask them what no system records: what they've already tried and why they stopped, what
they won't do, what a good month feels like, and which numbers they steer by — that last
one is worth knowing even where it disagrees with the account, because it tells you what
they'll judge the engagement against.

**Round 1 frontier — always these four:**

1. **Where is the constraint?** Traffic, conversion, close rate, retention, or margin.
   Only one of those five answers is "buy more clicks." A business with a 2% close rate
   and a full pipeline does not have a traffic problem, and selling them ads is billing
   them to make the real problem worse.
2. **Do the unit economics support paid at all?** Run the channel gate in
   `payback-period.md` against their real numbers. If payback exceeds their cash cycle,
   paid is the wrong recommendation no matter what they came in asking for. Say so
   before you take the work.
3. **What's already been tried, and what actually happened?** Ask whether a prior ad
   account exists and get access to it if so. Historical account data is free evidence
   and it beats anything you'd infer — read it before proposing anything.
4. **Who actually buys, versus who they say buys?** Put their answer next to their CRM.
   They may match — that's a finding worth having. Where they don't, the gap is usually
   where the engagement actually is.

## 2. Scope: what this engagement actually needs

**No stage is skipped by default and no stage runs by default. Each one stays
undetermined until the grill produces evidence about this specific business.**

There are two ways to get this wrong and they cost the same. Running the full 0→1
pipeline against an established business bills them to rediscover what they already
know. Assuming an established business *has* answers it doesn't have skips the stage
that would have caught it, and everything downstream gets built on a confident belief
instead of evidence. Both errors come from deciding scope before talking to them — so
decide it after.

Resolve each with evidence, not with a prior:

| Stage | The question that decides it | What settles it |
|---|---|---|
| CONTEXT | Is there current, accurate positioning to work from? | Ask for their materials and read them. Existing ≠ current ≠ accurate. |
| RESEARCH | Do they have verbatim customer language, and is it evidence or aspiration? | Ask to see it. Personas written in a conference room are not customer research. Aspirational material is worse than none — it's confidently wrong, and it will survive into copy if you treat it as a finding. |
| STRATEGY | Does what's already working point at what to do next? | Revenue mix by channel. Revenue from referrals proves demand for the service, not for paid acquisition — different question, different answer. |
| Competitor / market | Has something material changed, or are they entering a segment they haven't sold into? | Their own win/loss and account history before any generic market scan. |

Then **write the reason for every inclusion and every exclusion**, and put both in front
of the user at the gate. An unexplained skip and an unexplained inclusion fail the same
way: one underbills the problem, the other overbills the client.

**Escalate to `/pm-lead` — don't improvise a strategy — when the grill surfaces:**
- Revenue flat or declining while spend rises
- The paying customer and the stated target customer are different people
- Payback exceeds the cash cycle on every channel, not just this one
- The offer itself is what's failing, and no amount of traffic fixes it

These are the cases where foundational rethinking is warranted. Whether a given client
is one of them is a finding, not a prior — the grill decides it.

**Gate:** the user approves the constraint diagnosis *and* the scoped plan before any
account access is requested. Present it as recommendations with the evidence behind
each call — including the calls to leave a stage out — never as a fait accompli.

---

## 3. Access and baseline

Request read-only access first and take a baseline before changing anything. An
engagement with no baseline can never prove it worked.

- **Access:** client grants access to their own account; you never create the client's
  ad account under your own billing, and you never take custody of their payment method.
  Manager-account (MCC) link, read-only until the authority tiers below are agreed in
  writing.
- **Baseline:** run the audit in `references/google-ads-audit-checklist.md`, scored by
  `references/audit-guardrails.md`. Report **coverage before health** — if you couldn't
  see it, it's unknown, not broken.
- **Tracking is the precondition.** If conversion tracking is wrong, nothing downstream
  is readable and every optimization is guesswork dressed as expertise. Fix it (pack
  `ads` → `references/conversion-tracking.md`) or stop. Operating an account with broken
  tracking and reporting on it is the single fastest way to lose a client honestly.

**Artifact:** a standing engagement record, one directory per client, kept outside any
project repo — access and who granted it, the baseline audit with its coverage score,
the authority tier agreement, and an append-only change log. It's an ongoing
responsibility rather than a project: it has no completion date.


---

## 4. Authority tiers

Agree these in writing before touching a live account. Absent an explicit agreement,
everything is Yellow.

| Tier | Examples | Rule |
|---|---|---|
| **Green** — act, then log | Adding negatives from a *reviewed* search-terms report; pausing an ad confirmed broken; budget shifts inside an already-agreed envelope | Do it, log it in the change record same day |
| **Yellow** — propose, wait | Bid strategy changes, new campaign types, creative direction, landing page changes, changing the budget envelope | Written client approval before execution |
| **Red** — never without signed client decision | Raising total spend, changing or deleting conversion definitions, account restructures, touching billing, anything irreversible (deleting historical campaigns loses the learning) | Refuse until signed, in writing, by someone who can authorize spend |

Every hard stop in `audit-guardrails.md` is Red by default — including summing
conversions across platforms with different attribution windows, and producing negative
keywords without a search-terms report.

**Change one thing at a time when the account can't attribute more.** Whether it can
is a function of conversion volume and lag (see Cadence) — on a low-volume account,
simultaneous changes are unattributable and you'll never learn which one worked.

---

## 5. Cadence

**Cadence is derived from the account, not assigned to it — and it can't be derived
until the baseline audit is done.** Don't commit to a review rhythm in the proposal.
Say it will be set from the baseline, and set it there.

Two limits. The cadence is the slower one:

- **What the data can support.** Conversion volume and conversion lag set the earliest
  moment a change is readable. Derive both from the account: how long before a cohort's
  conversions are substantially complete, and how many accrue inside that window.
  Reviewing faster than the data can carry manufactures signal and invites the
  learning-phase reset `audit-guardrails.md` warns against.
- **What the engagement can fund.** Review time comes out of the retainer. Arithmetic on
  their actual spend and your actual rate — done once you know both.

Write the cadence in the engagement record *with the numbers it was derived from*, so
the next person can see whether it still holds, and re-derive it when conversion volume
or spend moves materially.

When the two limits disagree — budget for weekly, data for monthly — bill the slower
one and say why. Selling reviews the data can't support is the easiest thing in this
stage to do by accident, and it's indistinguishable from padding.

The search-terms ritual in `google-search-playbook.md` is the highest-value recurring
action; scale its frequency to the account, but never drop it entirely.

---

## 6. Reporting

**Do not rebuild Google's charts.** The client can already export those, and billing
them to re-render data they own is the reason in-house teams fire agencies. Google's
reporting is competent at data and useless at causality.

Every report is one page and answers four things:

1. **What we changed** — from the change log, with dates
2. **What it did** — measured against the baseline, with coverage stated
3. **What we recommend next** — and what it costs
4. **What we need from you** — the decision, or the access, or the tracking fix

**A report with no decision in it is a status update, and status updates get skimmed and
then cancelled.** If a cycle genuinely produced no decision, say that in two sentences
and skip the report — that's a better client experience than manufacturing pages.

Apply `audit-guardrails.md` benchmark discipline to every number you quote: label
provenance, check cohort fit, never blend attribution windows without saying so.

---

## 7. Paid fresh sweep

Same discipline as [fresh-sweep.md](fresh-sweep.md), different failure mode. Ad platforms
ship breaking changes on their own schedule; anything you write down about the current
platform surface is wrong within a quarter. **Never write a current platform fact into a
durable file — write the procedure that derives it.**

Run at the start of each reporting cycle. Timebox ~10 minutes.

1. **Release and policy sources:**
   - Google Ads API release notes (versions deprecate on a published schedule; Google's
     own `google-ads-api-quickstart` skill refuses to hardcode a version for this reason)
   - Google Ads Help "what's new" and policy updates
   - The account itself — new recommendation types and features appearing in the UI are
     the earliest signal that something changed
2. **Practitioner chatter** — r/PPC and Search Engine Land name real behavior changes
   weeks before official docs acknowledge them. Two independent reports before you
   act on one.
3. **Diff against the pack playbooks.** When a platform change contradicts something in
   `google-search-playbook.md`, that's an upstream fix — note it dated in the engagement
   record and open it against the pack, don't silently work around it.
4. **Never let a platform change become a Green action.** A new campaign type is Yellow
   at minimum, regardless of how hard Google's own UI pushes it.

---

## 8. Exit

Name the exit conditions at engagement start. An agency that can't say when to stop
buying ads isn't advising, it's renting.

Stop, hand back, or kill the channel when:
- Honest measurement puts payback beyond the client's cash cycle
- The constraint was never traffic, and the grill's finding has now been confirmed by
  spend that didn't move the business
- The client won't fix tracking — you cannot operate blind and you shouldn't bill to
  pretend otherwise
- Evidence coverage stays below the threshold `audit-guardrails.md` sets for reporting
  a health score at all, so no report you produce can carry one

Exiting well is the referral. Say plainly what you'd do instead, and hand over the
account, the change log, and the baseline.

---

## Artifacts and gates

| | |
|---|---|
| **Artifacts** | Constraint diagnosis + scoped plan with reasons · baseline audit with coverage score · authority tier agreement · append-only change log · per-cycle one-page report |
| **Entry gate** | the user approves the constraint diagnosis and the scoped plan before account access |
| **Standing gate** | Red-tier actions require signed client authorization, every time |
| **Exit gate** | Exit conditions named in writing at engagement start |
