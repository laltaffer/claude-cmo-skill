# Voice & Tropes: the anti-slop discipline

Applied during CRAFT (while writing) and enforced at REVIEW (trope scan). The test
underneath every rule: **would a specific, named human say this out loud to a customer?**
AI tells are what is left when nobody in particular is talking. The goal is not passing a
detector; it is writing that could only have come from someone who knows this product and
this audience.

## The baseline lives in the pack

The static catalog is `~/.claude/marketing-pack/skills/copywriting/references/ai-tells.md`:
13 structural patterns with Ban and Cap tiers, the opener and closer table, the marketing
phrase table, the vocabulary lists, rewrite rules, and a self-check. Read it at CRAFT and
at REVIEW step 3; its Cap tiers are countable, which is what review.md asks for. Nothing in
it is repeated here. (Reconciled 2026-10-04 when the pack absorbed the catalog this file
used to carry; see the changelog.)

This file holds what the baseline does not: the dated living layer below, the owner's
taste, and the fingerprint of the model holding the pen.

## Living layer: tells the baseline does not carry

Promoted entries are rewrites or findings like any baseline entry. Watch entries need a
second independent source before they count.

- **Launch boilerplate** (promoted 2026-07-07): "We're excited/thrilled to announce",
  "Get Started Today" as the default CTA everywhere. Say what shipped and what to do.
- **Integrity failures, not style** (promoted 2026-07-07): fake urgency or scarcity;
  invented testimonials, statistics, or review quotes. Any hit blocks shipping.
- **Anaphora** (promoted 2026-07-07): three or more consecutive sentences opening
  identically. Vary the opener or merge the sentences.
- **Fractal summaries** (promoted 2026-07-07; tropes.fyi marks it rising, 2026-10-04):
  intro that previews, sections that recap, a close that restates. On a marketing page:
  the same value prop rephrased in hero, subhead, and CTA band with no new information.
  Each block carries a fact the others do not.
- **Equal-treatment symmetry** (promoted 2026-08-26, two sources; re-confirmed 08-29):
  every section or factor gets a paragraph of near-identical length, pros and cons in
  perfect balance. Give each point the length its evidence earns.
- **Superficial analysis without evidence** (watch, 2026-09-02): a sentence with the
  shape of insight that asserts a mechanism and supplies nothing behind it. Test: if a
  sentence explains why something is true, the next clause earns it or the sentence goes.
- **Advertising register in place of neutral** (watch, 2026-09-02): travel-guide diction
  ("nestled", "vibrant") standing in for description.
- **Hollow-empathy openers** (watch, 2026-08-29): "As a business owner, you know..."
  followed by a generic problem.
- **Dramatic-comparative flourish** (watch, 2026-08-26): "better than a prompt ever
  could", "like nothing else can" at the end of a mechanism description. End the sentence
  where the mechanism ends.
- **A rejected cadence reappears carrying different content** (category, 2026-09-02):
  scrub the rhythm the owner rejected, not just the words that carried it.
- **Mechanical markers from the Economist study** (single study, 2026-08-31, still not
  promoted as of 2026-10-04): punctuation scarcity, "and" overuse, Latinate-suffix
  density, never quoting anyone. Count them when a draft feels flat; see the changelog for
  why they stay unpromoted.

## The model holding the pen

Tells are per model, not one AI voice (Graphite, 2026-09-16, 10k human and 90k AI
articles across nine models: 65% of tells are unique to one model family; Rudnicka and
Juzek, arXiv 2608.06589, call it idiolect). So the scrub list depends on which model
drafted. Record the pen in the copy brief and refresh this section when it changes.

| Pen | Fingerprint | Source |
|---|---|---|
| **Fable 5.1** (this pipeline's pen since 2026-10) | No published fingerprint yet. Until one exists, count the Opus 5.5 phrases below in every draft and record the per-1,000-word em-dash rate in the review; promote whatever recurs | Own measurement |
| Claude Opus 5.5 | "dependable" 23x human rate, "this matters" 116x, "why X matters" 92x, "more than an X, it's a Y" still common; em dashes 99% below Opus 5 | TechCrunch, Russell Brandom, 2026-10-01, on Graphite's follow-up |
| Claude Opus 5 | "less like a _ and more like" 105x, "rather than merely" 160x, "matters because" 132x; em dashes at the human rate | Graphite, 2026-09-16 |
| GPT-6 Astra | "the _ is not simply" 576x, "not simply" 157x, "another dimension" 117x, hedges "may provide" and "can provide"; em dashes 88% below human | Graphite, 2026-09-16 |
| Gemini 3.1 Pro | "is not just a _ it is" 153x, "incredibly", "furthermore"; em dashes near zero | Graphite, 2026-09-16 |

Shared across models: contrast framing, corrective phrasing ("rather than", "not just",
"not simply"), hedging. Humans use first person and exclamation marks far more than any
model. The em-dash rule for this pipeline is now house style (the global instruction bans
them in anything written for the owner), not a correction of a measured Claude bias: the
08-31 finding was about Opus 5, and the pen has changed twice since.

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
- **No adversary in the lead.** Copy never opens on the vendor, the hype, the
  competitor, or on what someone did to the reader. Name what the thing *is*, positively
  and concretely, and let the antagonist stay implied. Watch for this in the *angle*,
  not only the sentence: an angle whose first beat is "you've been sold X" reproduces the
  fear lead no matter how the paragraph is rewritten.
- **No deficit-framing of the reader's current state.** Never "barely using", "failing
  to", "wasting", "you're behind", "most people get this wrong". Describe their situation
  as an opportunity or leave it unsaid — "you've probably been using AI already and we'll
  help you get the most out of it", not "you bought a tool you barely use". The reader
  is not the problem in the story.

## Changelog

- **2026-10-04** Fresh sweep (pack reconciliation, no draft in hand). **Catalog moved.**
  The pack's copywriting 2.1.0 shipped `references/ai-tells.md`, which carries every Hard
  ban and Density tell this file listed, with Ban and Cap tiers. This file's catalog
  sections were removed and the entries the baseline lacks were lifted into the living
  layer above. **Per-model fingerprints**, verified by fetch: Graphite (2026-09-16) and
  TechCrunch (2026-10-01) as tabled in the pen section. The pen is Fable 5.1 and has no
  published fingerprint; the Opus 5.5 phrases are the proxy until measured. **tropes.fyi
  now flags status** (fetched 2026-10-04, 63 tropes): new (reasoning leak, premise
  stacking, compulsive counting, self-echo, synonym cycling, comma-clipped trailing
  phrase, never-ending conclusion, promotional language, "Where / What / Why" headers,
  among 16), rising (short punchy fragments, grandiose stakes, invented concept labels,
  fractal summaries, excessive enumeration), consistent (negative parallelism, em-dash
  addiction, "quietly", vague attributions, rule of three, "Not X. Not Y. Just Z.", title
  case, signposted conclusion), fading ("The X? A Y.", anaphora, bold-first bullets,
  "Think of it as", "Imagine a world", false ranges, "serves as", "delve" and friends,
  "It's worth noting", "Let's break this down"). Page carries no dates; fresh-sweep.md
  step 1 now reads the flags. **Wikipedia** (fetched 2026-10-04): "delve" dropped sharply
  in 2025; the mid-2025-onward vocabulary is "emphasizing, enhance, highlighting,
  showcasing"; the "no ..., no ..., just ..." form is documented. **LinkedIn** (May 2026,
  secondary write-ups only, thenextweb and magicpost; primary announcement not fetched):
  formulaic AI posts are suppressed from recommendations, with "it's not X, it's Y" named
  as the example; one tracker puts the reach penalty near 5%. **Economist tells not
  promoted.** The audit proposed Graphite and Poynter as the second source for
  punctuation scarcity, "and" overuse, Latinate density, and never quoting anyone.
  Checked: Poynter (Matthew Crowley, 2026-09-28) cites the Economist only for the Claude
  em-dash rate and names negative parallelism, waffle ("it can be argued that"), and
  overabundant lists; Graphite reports first person and exclamation marks as the human
  markers, not punctuation scarcity or "and". Fast Company and The Conversation (09-02
  entry) are write-ups of the same study. One study with four write-ups is one source.
  The four stay in the living layer as count-when-flat markers. **Reverse direction:**
  Poynter's editors warn that stripping em dashes to pre-empt suspicion lowers quality;
  Opus 5.5 and Astra barely use them. The scrub here is house style, not detection.

- **2026-08-31** — Fresh sweep. **Real find, and it corrects one of ours.** The
  Economist ran the largest controlled comparison yet — 1.2M words / 55,940 sentences,
  ChatGPT + Claude + Gemini + Grok rewriting its own articles, scored against its prose,
  other journalism, and novels 1950–2022 (reported 2026-08-11; two independent
  write-ups). Four new tells, all **mechanical and countable**: **punctuation scarcity**
  (LLMs use fewer commas and semicolons than humans, and hardly any parentheses);
  **"and" overuse** (their most overused word, gluing clauses into long sentences);
  **Latinate-suffix density** — Orwell's "pretentious diction," simple ideas in
  complicated language, which generalises the delve-class wordlist into a measure that
  survives model-era vocabulary drift; and **never quoting anyone**. Changelog only,
  no catalog promotion — first sighting.
  **This retires a calibration number.** Most models use *fewer* em dashes than human
  writers; ChatGPT "markedly fewer"; **Claude is the only one that uses more.** So
  em-dash density is a **model-specific** tell, not a universal one — check it against
  whichever model is holding the pen, and scrub to correct that model's known bias
  rather than to appease a detector. The catalog rule ("several per paragraph") is
  unchanged.
- **2026-08-26** — Fresh sweep. New tells: **"quietly" as a tell word** (UWA study
  Aug 2026 + an independent design-catalog ban on "Quietly in use at" headers) and
  **equal-treatment symmetry** — sections of near-identical length, pros/cons in
  perfect balance (GPTZero "AI Patterns" + a 2026 spotting guide).
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
