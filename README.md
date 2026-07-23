# Claude Token Reducers

> A collection of Claude skills and tools to maximize information density and minimize token usage — without sacrificing accuracy.

---

## Skills

### `/reduceToken`

A Claude skill that activates compact, high-density response mode on command.

**The problem it solves:** Every session you copy-paste a long disclaimer asking Claude to be concise. This skill replaces that entirely — one command, session-wide effect.

#### Commands

| Command | Effect |
|---|---|
| `/reduceToken` | Default mode — 300–800 token budget |
| `/reduceToken [N]` | Custom budget — e.g. `/reduceToken 500` |
| `/reduceToken study` | Study mode — 150–400 tokens, concept-first format |
| `/reduceToken off` | Deactivates, returns to default Claude style |

#### What it enforces

- No filler, no preamble, no re-stating your question
- Bullets over prose, tables over explanations, diffs over rewrites
- Code: only changed files, minimal comments
- Analysis: Decision → Reason → Implementation → Risks
- Study: Concept → How it works → When to use it → Gotcha

#### Core rule

> **Never sacrifice correctness, completeness, or critical risks to reduce token count.**
> Token reduction is a style constraint, not a quality constraint.

---

## Installation

### Option A — Claude.ai Skills (recommended)

1. Download [`reduce-token.skill`](./reduce-token/SKILL.md)
2. Go to **Claude.ai → Settings → Skills → Install**
3. Upload the file
4. Type `/reduceToken` in any chat to activate

### Option B — Paste manually

Copy the contents of [`reduce-token/SKILL.md`](./reduce-token/SKILL.md) into your Claude chat as a system prompt or at the start of a session.

### Option C — Claude Code

Add to your `CLAUDE.md`:
```
Read reduce-token/SKILL.md and apply its rules whenever the user types /reduceToken.
```

---

## Usage examples

```
/reduceToken
Review this Python function and suggest improvements.
```

```
/reduceToken 500
Explain how Redis pub/sub works.
```

```
/reduceToken study
What is a transformer attention mechanism?
```

---

## Project structure

```
Claude-Token-Reducers/
├── README.md
├── LICENSE
└── reduce-token/
    └── SKILL.md        ← the skill definition
```

---

## Contributing

PRs welcome. If you build a new token-reduction skill (e.g. `/reduceToken code`, `/reduceToken review`), open a PR with:
- A new folder under the root
- A `SKILL.md` following the same format
- A section added to this README

---

## License

MIT — see [LICENSE](./LICENSE)
