# Review: evidence first, judgment labeled

A copy review has two layers that must never blur. Blended, reviews decay into vibes
("the tone could be warmer, the middle drags"). Split, each layer is worth something:
**evidence** is checkable and **judgment** is arguable, and the reader can tell which
is which.

This order is measured, not assumed. In the 2026-09-15 ablation, three drafts of one
landing page (a bare model with a one-page brief, the loaded stack without this
pipeline, and this pipeline) came out with the same skeleton, the same CTA label, and
the same testimonials. What separated them was checkable: whether every quoted line
traced to a live source, whether the context doc had gone stale, and a handful of
review findings. The stage choreography did not move the copy; the checks did. So the
checks stand alone here and run on any copy, drafted or live, whether or not it came
through the pipeline.

## Layer 1: evidence

**0. Name the artifact.** The file path, or the URL. For a live page, confirm the
fetched content is the real page and not a bot-challenge interstitial or an empty
client-side shell. For a CMS site that keeps a versioned content snapshot, read the
snapshot and say so.

**1. Mechanical checks.** Run them as commands and report counts, never impressions.

- Em and en dashes, counted. Claude uses more of them than human writers do (changelog
  2026-08-31), so drafts from this pipeline ship with none unless the project's
  context doc says otherwise. On copy the human wrote himself, count and report; the
  call is his.
- The avoid list: every word in the context doc's "Words to avoid" plus the hard-ban
  vocabulary in [voice-and-tropes.md](voice-and-tropes.md). Hits with line numbers.
- Placeholders and generic names: lorem, TBD, bracketed stubs, "Jane Smith", "Acme".
  Any hit blocks shipping.
- Lengths the channel enforces, for the asset type in hand only: title tag, meta
  description, ad headline and description, email subject. The pack skill for that
  channel carries the limits.
- Display lines: word count per headline line. Whether a line wraps at 390px is the
  design review's finding to confirm; flag the risk here.

**2. Fact sourcing, both directions.** Every quote, attribution, name, credential,
number, price, place, phone number, URL, and claim of fact, traced to one of: the live
site or its snapshot, the account or product data, the project docs, or the research
brief with its own source. One table: claim, where it appears, source, status
(sourced, unsourced, contradicts). Unsourced cannot ship. Contradicts is a finding
against whichever side is stale.

Then run the check in reverse: the context doc's verbatim customer language and proof
points against the live site. A testimonial or line the site no longer carries is a
stale-doc finding. Report it to the doc's owner; do not reuse it. This is the check
that caught a context doc citing three testimonials a relaunched site had dropped.

**3. Trope scan.** Every entry in [voice-and-tropes.md](voice-and-tropes.md) against
the copy: hard bans are rewrites, density tells are findings once they pattern. Quote
each occurrence. Add the project's own rules from the context doc's Brand Voice
section; those are per-project, never defaults.

**4. Seven sweeps.** Read `~/.claude/marketing-pack/skills/copy-editing/SKILL.md` and
run its passes. Report each finding with the line quoted and the sweep that caught
it. The sweeps propose edits; here they are findings, not rewrites (see below).

**5. Fresh sweep.** Run [fresh-sweep.md](fresh-sweep.md), timeboxed, every review.
New two-source tells go to the changelog, dated; then scan the copy against them. If
the sources are unreachable, say so and proceed on the static catalog.

**6. Read-aloud test.** For every display line, every CTA, and any paragraph a sweep
flagged: would the specific, named human the context doc says is speaking (the
founder, the practice's "we") say this sentence out loud to a customer? A line nobody
would say is a finding, quoted.

**State your coverage.** What was not checked and why: no live page available, no
account data, sweep sources down, an asset type with no length rules.

**Lead with the verdict line:** CLEAN, or FINDINGS (N hard, M advisory), with the
coverage caveat on the same line. Hard means a hard-ban hit, an unsourced fact, or a
placeholder. Advisory is everything else.

## Layer 2: judgment, labeled as judgment

Open the section by saying these are opinions rather than findings. At most five.
Tie each to a quoted line, and make each answer one question: **does this line do
its job for the asset's objective?** For a landing page that is message match to the
query the visitor typed, one ask, and a first line that states what this is. For an
email it is the one action. For a post it is the one idea.

Close with the single strongest improvement, stated as a delta.

## A review reports; it does not rewrite

The findings are the work list. The writer applies them: a pipeline round folds them
into the draft and re-runs the mechanical checks; the human edits his own copy as he
likes. Two categories block shipping on their own, hard-ban hits and unsourced facts.
Everything else is the human's call.

## Capture the verdict

The human's verdict is the most valuable output of the round. Two destinations:

- **Into the copy brief**, near-verbatim, for the next round. "This reads like a
  brochure" sanded into "prefers plainer tone" loses what made it actionable.
- **Into its one home**, when it outlives this asset:

| The fact | Home |
|---|---|
| A new tell, seen in two independent sources | the changelog in `voice-and-tropes.md`, dated; promote to the catalog when it recurs |
| A cadence the human rejected | the changelog, as a category: a rejected rhythm reappears carrying different content |
| A project's voice, proof, or stance ruling | that project's `.agents/product-marketing.md`, Brand Voice |
| A rejection and its why | the project's `_brain.md`, verbatim |
| How the human wants me to work | a feedback memory, with why and how-to-apply |

Three disciplines govern that write: entries are dated so a later sweep can prune
what stopped being everywhere; a tell's entry carries what to say instead (replace,
never just delete); and check for an existing entry first, update rather than
duplicate, and quote the new entry back in one line so a bad generalization can be
vetoed on the spot.

## Done

The verdict line; the mechanical counts; the fact-sourcing table with every unsourced
item named and the reverse check run; trope and sweep findings quoted; the fresh
sweep's result; coverage stated; judgment labeled and capped at five; any durable
verdict written to its one home.
