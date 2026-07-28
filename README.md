# /cmo — a gated marketing pipeline skill for Claude Code

A Claude Code skill that runs marketing work through a gated pipeline so nothing ships
sounding like a machine: CONTEXT → RESEARCH → STRATEGY → CRAFT → REVIEW → SHIP → RETRO.
Every stage produces a named artifact and stops at a gate for your judgment. Three
modes: **full** (new project / launch / repositioning), **fast** (single asset),
**audit** (review existing copy).

What makes it different from a pile of marketing prompts:

- **An anti-slop review gate** — every draft is scanned against a maintained catalog of
  AI writing tells (`voice-and-tropes.md`), plus a **fresh sweep** protocol
  (`fresh-sweep.md`) that re-checks the living catalogs and current chatter at every
  review, because AI tells shift with every model generation.
- **A voice & stance interview** at CONTEXT — whose voice, does the audience already
  live the problem, gift or sale — because these can't be guessed and wrong defaults
  die in review.
- **Research routing** (`research-playbook.md`) — where the voice of each audience type
  actually lives, and the 2026 AI-backlash data as strategy posture, not style notes.
- **Never fabricate** — verbatim customer quotes carry a source or they don't ship.

## Install

```bash
git clone https://github.com/laltaffer/claude-cmo-skill.git ~/.claude/skills/cmo
git clone https://github.com/coreyhaines31/marketingskills.git ~/.claude/marketing-pack
```

New Claude Code sessions will pick it up as `/cmo`. The second clone is the sub-skill
pack ([coreyhaines31/marketingskills](https://github.com/coreyhaines31/marketingskills),
MIT, 47 marketing skills) — deliberately **not** installed as skills: /cmo reads them
by file path at the moment of use, so your session skill list stays clean and
trigger-matching can never pick a marketing skill by accident. Update it anytime with
`git -C ~/.claude/marketing-pack pull`.

## Companion skills

Same shape, same gate discipline, built to hand work to each other:

- **[/cto](https://github.com/laltaffer/claude-cto-skill)** — the engineering pipeline
  SHIP hands web copy to.
- **[/uxr](https://github.com/laltaffer/claude-uxr-skill)** — the research pipeline.
  It owns evidence-for-product-decisions; /cmo RESEARCH owns voice-of-customer for
  copy, and the venue table here is the one both use.

## Customize

- `voice-and-tropes.md` — "The owner's taste layer" section is a template; encode your
  own taste there. The trope catalog is a living file: fresh sweeps append dated finds.
- `research-playbook.md` — add venue rows for your recurring audience types.
- The pipeline writes a per-project context doc at `.agents/product-marketing.md`
  (the pack's convention) and expects a project memory file for durable decisions.

## License

MIT. The trope catalog distills [tropes.fyi](https://tropes.fyi) and Wikipedia's
"Signs of AI writing"; sentiment data from published 2026 survey reporting.
