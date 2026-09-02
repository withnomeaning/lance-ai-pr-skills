# AI PR Skill Pack

Turn PR **judgment logic, risk awareness, and execution workflows** into reusable AI Skill files.

## What This Is

A set of 6 Claude Code Skills for brand PR scenarios, built on one core assumption:

> PR is fundamentally business judgment, not expression. Expression is only the action that follows judgment.

So this isn't 6 standalone writing templates — it's a complete "analyze → decide → execute" decision chain: **5 Skills for specialized analysis, 1 Skill for the final call.**

## Why Skills Instead of Prompts

- Judgment logic, risk awareness, and execution workflows are locked into files, reusable across sessions without relying on memory
- Every call follows the same standard, so results are predictable, accumulable, and reviewable
- A clear division of labor between specialized Skills avoids diluting judgment by having "one prompt do everything"

## The Six Skills

### 1. Judgment Hub `judgment-hub` — Final Call

Decides "what to do, what not to do, and why":

- Whether to respond, publish, or delay
- Whether to sacrifice communication impact to protect trust
- Whether to turn external sentiment into an internal business review
- Whether to escalate a seemingly small expression problem into a strategic issue

Use when you need a final recommendation, priority ranking, crisis-response decision, communication-strategy diagnosis, or business-impact judgment.

### 2. Hot Public Opinion Analysis `hot-public-opinion-analysis` — Specialized

Turns external hot topics into business judgment. Answers four questions each time:

- Has it grown from a single piece of information into collective opinion?
- Who does it actually offend, and why can it be amplified?
- Will it escalate, cool down, reverse, or become a long-term issue?
- How does it relate to brand trust, business risk, and PR assets?

Outputs a four-part judgment: **gained momentum / substance / trajectory / business implications** — ready to forward to the business team.

### 3. Media Narrative Analysis `media-narrative-analysis` — Specialized

Reading a piece isn't summarizing what it says — it's judging whose perception it's building:

- What is the piece's real communication intent?
- Does it affect us, and which PR assets does it hit?
- Do we ignore, observe, or escalate to the Judgment Hub?

Outputs a conclusion-first analysis, not a summary.

### 4. PR Contingency Plan `pr-contingency-plan` — Specialized

Risk mapping for upcoming brand, product, content, partnership, spokesperson, or rule changes. A contingency plan isn't about zero risk — it's about unpacking, before launch, the points that could drain trust, cause misunderstanding, be amplified by rivals, be screenshotted by media, or be questioned by regulators. Produces three things:

- What is most likely to be attacked
- What to say publicly and on the record if attacked
- What must be changed, prepared, or merely monitored before launch

### 5. Copy Public-Context Review `copy-lens-review` — Specialized

Public-context risk review, not creative aesthetic review. Core formula:

```
Public risk = semantic ambiguity × group sensitivity × scenario severity × screenshot shareability × explanation cost
```

Covers gender, family, holidays, fandom, vulnerable groups, pet-food regulation, screenshot spread, and media amplification risks. Outputs a three-level conclusion: **pass / usable after revision / high risk — rewrite recommended.**

### 6. Press Release `press-release` — Specialized

Drafting and editing ten types of press releases (new car launch, auto show, tech/OTA upgrade, strategic partnership, crisis response, new product launch, pet welfare, event, expert view, year-in-review). Workflow: confirm the core action and communication goal → MVP → full draft → final review. Defaults to party/central-media hard-news style.

## Workflow

```
Hot event ──────→ Hot Public Opinion Analysis ──┐
Single piece ───→ Media Narrative Analysis ─────┤
Upcoming action → PR Contingency Plan ──────────┼──→ Judgment Hub (final call)
Copy material ──→ Copy Public-Context Review ───┤
Press release ──→ Press Release ────────────────┘
```

Concrete tasks go through the matching specialized Skill first; the Judgment Hub makes the final call afterward.

## Installation

Place the whole directory into `~/.claude/skills/`:

```bash
git clone https://github.com/withnomeaning/lance-ai-pr-skills.git
cp -R lance-ai-pr-skills/{judgment-hub,hot-public-opinion-analysis,media-narrative-analysis,pr-contingency-plan,copy-lens-review,press-release} ~/.claude/skills/
```

Each Skill is triggered via `/skill-name` in Claude Code or natural language.

## Structure

```
├── judgment-hub/                  Judgment Hub
├── hot-public-opinion-analysis/   Hot Public Opinion Analysis
├── media-narrative-analysis/      Media Narrative Analysis
├── pr-contingency-plan/           PR Contingency Plan
├── copy-lens-review/              Copy Public-Context Review
└── press-release/                 Press Release
```

Each Skill directory contains `SKILL.md` (core definition), `references/` (knowledge base), `Test-Cases/` (test cases), etc.
