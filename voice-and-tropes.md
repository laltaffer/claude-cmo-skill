# Voice & Tropes — the anti-slop discipline

Applied during CRAFT (while writing) and enforced at REVIEW (trope scan). This is a
**living file**: fresh sweeps append dated entries to the changelog at the bottom and
promote recurring finds into the catalog. Distilled 2026-07 from tropes.fyi,
Wikipedia's "Signs of AI writing," and 2026 consumer-sentiment research.

The test underneath every rule: **would a specific, named human say this out loud to a
customer?** AI tells are what's left when nobody in particular is talking. The goal is
not passing a detector — it's writing that could only have come from someone who knows
this product, this audience, and gives a damn.

## Hard bans — any hit is a rewrite

**Words (delve-class vocabulary):** delve, leverage (as verb), robust, seamless,
streamline, harness, elevate, unlock, unleash, supercharge, empower, effortless,
game-changing, cutting-edge, revolutionize, transformative, tapestry, landscape (for
abstractions), realm, journey (for product use), "in today's fast-paced world."

**Sentence patterns:**
- Negative parallelism: "It's not X — it's Y." / "It's not just an X. It's a Y." The
  single most-recognized AI tell. Also the stacked form: "Not X. Not Y. Just Z."
- Self-posed question flips: "The result? A better workflow."
- "Imagine a world where…" / "Picture this:" openers.
- "Let's dive in / unpack / explore / break this down" — pedagogical throat-clearing.
- "Think of it as…" — patronizing analogy reflex.
- "Here's the kicker / the thing / where it gets interesting" — false suspense.
- "It's worth noting that…" / "That said," as filler transitions.
- "Whether you're a X, a Y, or a Z…" — the audience triple that names no one.

**Marketing boilerplate:**
- "We're excited/thrilled to announce…" launch openers.
- "Get Started Today" as the default CTA everywhere.
- Exclamation points in body copy. Emoji clusters (🚀✨💡) in headlines or CTAs.
- Fake urgency or scarcity; invented testimonials, statistics, or review quotes —
  these are integrity failures, not style failures.

## Density tells — fine once, slop in a pattern

These are legitimate tools that read as AI at high frequency. Flag when the pattern
repeats, not on first use:
- **Em-dash addiction** — several per paragraph, or every pivot leaning on one.
- **Rule-of-three abuse** — every list, headline, and benefit set shaped as a triple.
  Uniformity is the tell: three cards, three words each, identical rhythm.
- **Bold-first bullets** — every list item opening with a bolded phrase.
- **Short punchy fragments. Everywhere. For emphasis.** — one-line paragraphs as a
  default rhythm rather than a deliberate hit.
- **Anaphora** — three+ consecutive sentences opening identically.
- **"Serves as / stands as / boasts"** — copula-dodging; just say "is."
- **Fractal summaries** — intro that previews, sections that recap, a conclusion that
  restates. Marketing pages: the same value prop rephrased in hero, subhead, and CTA
  band with no new information added.
- **Signposted endings** — "In conclusion," "To sum up," "At the end of the day."
- **Title Case On Every Heading** — sentence case reads more human in 2026.
- **Vague attributions** — "experts agree," "studies show," "industry reports" with no
  named source. Either cite it or cut it.
- **False ranges** — "from startups to enterprises" when the items aren't a spectrum.
- **Grandiose stakes** — every feature framed as pivotal, revolutionary, a paradigm.
  If the copy can't earn the claim with a specific, shrink the claim.
- **Uniform rhythm / low burstiness** — sentence length and structure barely vary,
  producing a monotonous cadence readers now name explicitly.
- **Transition-word stacking** — "furthermore," "moreover," "additionally" as
  paragraph glue.
- **Fake-profound closers** — endings reaching for unearned profundity ("The future
  isn't coming. It's already here.").

## Visual slop (flag and route, don't fix here)

Marketing assets have an "AI look" as recognizable as the prose tells: purple-to-blue
gradients, glow effects on dark, Inter-everywhere, three identical benefit cards,
generic 3D blobs/orbs, sparkle iconography. Flag it, then route to your design skills —
visual craft is their jurisdiction.

## Voice rules — what to do instead

1. **Specificity is the whole game.** "Cut weekly reporting from 4 hours to 15 minutes"
   beats any adjective. Numbers, named users, real objects, actual moments. Every vague
   claim in a draft is a research question that wasn't answered.
2. **Verbatim customer language.** Say it the way the research brief says they say it.
   "We were drowning in spreadsheets" outperforms "manual process inefficiency" every
   time — and it can't be generated, only found.
3. **One idea per section.** Each block advances one argument. If a sentence is doing
   two jobs, split it or cut one.
4. **Benefits in the reader's world.** What changes for them by Friday — not what the
   feature does.
5. **Confident and plain.** No hedges ("almost," "really," "arguably"), no qualifier
   stacks. Take a position; state what would change it.
6. **Honest over sensational.** Claims the product can't cash erode the only asset
   marketing has.

## The owner's taste layer — replace with your own

Encode the copy owner's taste here so every asset inherits it. Examples of the kind of
rules that belong (edit these to yours):

- **Bold over safe.** A specific, opinionated line the owner can reject beats a
  generic-safe line they must tolerate. Generic costs a full review round.
- **Display lines are lockups.** Headlines are written to their measure — count the
  words, know where it breaks. A mid-sentence wrap at display size is unacceptable.
- **Voice, proof, and stance are per-project decisions, never defaults** — they come
  from the CONTEXT stage's voice & stance interview and live in that project's
  `.agents/product-marketing.md`, not here.

## Changelog

- **2026-07-26** — Fresh sweep. New tell for the catalog: **fake-profound closers** —
  endings that reach for unearned profundity ("The future isn't coming. It's already
  here."), named in Peter Yang's open-source no-ai-slop skill (2026-07-22, ~20
  patterns; two independent write-ups). The same source set confirms "binary contrasts"
  (our negative parallelism) and "throat-clearing openers" as the most-recognized
  tells. Context shift worth tracking: Substack now runs Pangram AI-detection natively,
  and Pangram measures 41% of LinkedIn longform as fully AI-generated — folk-detector
  scrutiny is rising, which strengthens the reverse-direction rule (write for "would a
  human say this," not for detectors).
- **2026-07-08** — Fresh sweep (first pilot REVIEW). New density tells: **uniform
  rhythm / low burstiness** and **transition-word stacking**. Supporting stat for the
  posture file: 52% of consumers stop reading on suspecting AI (Bynder, via 2026 tell
  lists). tropes.fyi re-checked: no new entries beyond the initial catalog.
- **2026-07-07** — Initial catalog. Sources: tropes.fyi/tropes-md (~35 named tropes),
  Wikipedia "Signs of AI writing" (notes vocabulary drift per model era), Harris/
  Marketing Brew 2026 sentiment data. Baseline model era: Claude 5 / GPT-5.x.
