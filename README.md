# claude-skills-for-pms

Templates, frameworks, and skills for product managers using Claude Code. Companion to [pm-second-brain](https://github.com/dandanmarcovici/pm-second-brain): that repo ships the structure (folder conventions, the CLAUDE.md loading pattern, self-context files). This repo ships the content that plugs into it.

Everything here was built for real PM work, not written as a portfolio piece. Each one has been used repeatedly and revised based on what actually happened in the room.

None of this arrived finished. The product decision principles started as one rule after a single bad sequencing call, then a second after a different project hit the same wall, and grew into a set only after enough repeats made the pattern obvious. Same with the skills: `opportunity-check` and `product-sense` are shaped by the specific ways earlier, looser versions let vague answers through. What's here is the version after that many passes, not the first draft.

---

## The three kinds of content

Each behaves differently, so each gets wired in differently.

| Kind | What it is | How to use it |
|---|---|---|
| **Templates** | A fixed output format. Claude fills it in when producing a specific kind of document. | Reference from a CLAUDE.md trigger: "When writing a pre-read, load `templates/pre-read-format.md`." |
| **Frameworks** | A reasoning model. Informs how Claude thinks about a problem, doesn't force a specific output shape. | Reference from a CLAUDE.md trigger, usually "load when relevant" rather than always-on. |
| **Skills** | A bounded, interactive workflow. Claude runs a specific process end-to-end when invoked. | Drop the folder into `.claude/skills/`, invoke with `/name`. |

---

## Templates

| File | What it's for |
|---|---|
| [`templates/pre-read-format.md`](templates/pre-read-format.md) | Documents sent before a meeting, built on the Minto pyramid: recommendation first, then options, then supporting evidence. |
| [`templates/meeting-notes-format.md`](templates/meeting-notes-format.md) | Meeting agendas and notes, structured so the same document works before the meeting (agenda) and after it (notes). |

---

## Frameworks

| File | What it's for |
|---|---|
| [`frameworks/product-decision-principles.md`](frameworks/product-decision-principles.md) | Eight decision filters for product strategy: sequencing, scoping, and when to trust (or distrust) your own expertise. |
| [`frameworks/exec-communication.md`](frameworks/exec-communication.md) | Principles and pre/post-meeting rituals for communicating upward, with managers, directors, and executives. |
| [`frameworks/opportunity-validation.md`](frameworks/opportunity-validation.md) | A 9-step process for pressure-testing a market opportunity before committing resources, with an emphasis on demand-fit over supply-fill. |

Not included here, but worth knowing: Teresa Torres' Business Fundamentals Canvas (from Continuous Discovery Habits) is a strong companion framework for clarifying a business model at the initiative level. It's paid course material, so it's not reproduced in this repo, go take the course directly.

---

## Skills

| Folder | What it does |
|---|---|
| [`skills/opportunity-check/`](skills/opportunity-check/SKILL.md) | Runs the opportunity-validation framework above as a forced, one-step-at-a-time interrogation, ending in a Go / Needs More Signal / No-Go verdict. |
| [`skills/product-sense/`](skills/product-sense/SKILL.md) | A 5-question stress test (empathy, simulation, strategy, taste, creativity) for a product decision, ending in a Go / Reconsider / Stop verdict. |
| [`skills/html-presentation/`](skills/html-presentation/SKILL.md) | Turns a markdown file or doc into a single self-contained HTML slide deck for live screen delivery, two-phase (outline approval, then build) so it never generates 20 slides you didn't ask for. Ships with a default accent color, swap the hex in the Brand section for your own. |
| [`skills/session-sync/`](skills/session-sync/SKILL.md) | Scans the current session and updates context.md, tasks.md, and log.md with what actually changed, skipping anything already captured or uncertain. Built for the pm-second-brain file convention. |

`opportunity-check` and `product-sense` are built to push back, not validate. If an answer is vague or generic, they're instructed to challenge it once before moving on, not accept it and move to the next question.

---

## Setting it up

1. Copy the folders you want into your own vault or repo.
2. For templates and frameworks: add a trigger line to your CLAUDE.md pointing at the file, so Claude loads it only when it's relevant, not on every session. Same pattern either way: `path → when to load it`.

   ```
   - `templates/pre-read-format.md` → when writing a pre-read, briefing document, or anything meant to be reviewed before a meeting.
   - `frameworks/opportunity-validation.md` → when weighing whether to pursue a new market opportunity, or evaluating a go/no-go bet before committing resources.
   ```

3. For skills: copy the whole skill folder into `.claude/skills/`. Claude Code picks it up automatically, invoke with `/opportunity-check`, `/product-sense`, `/html-presentation`, or `/session-sync`.

---

## Related

- [pm-second-brain](https://github.com/dandanmarcovici/pm-second-brain): the structure this content plugs into.

---

## License

MIT, see [LICENSE](LICENSE).
