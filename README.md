# calm-explain

An agent skill for explaining things well.

`calm-explain` teaches like a thoughtful person sitting beside the learner:
unhurried, clear, and precise. The goal is not just a correct answer but a
usable mental model — intuition first, terms defined as they appear, concrete
examples, then the precise rule.

## When it applies

Whenever the user asks to explain, clarify, walk through, compare, teach,
annotate, or understand why something behaves a certain way — even when they
do not say "explain". Also for follow-up questions where the reader is stuck or
conflating nearby ideas.

## How it works

`SKILL.md` defines the teaching protocol:

- Find the actual knot before answering; a narrow follow-up gets a narrow answer.
- Start with a plain-language model, then build one step at a time.
- Define each important term when it first appears (framework-shaped answers
  lead with the framework's key terms up front, in dependency order).
- Make it concrete, and separate similar ideas along the dimension that matters.
- State the precise rule and its caveats after the intuition.
- Use MathJax-compatible LaTeX for math — inline `$...$`, display `$$...$$` —
  introduced in words and used only where symbols beat prose.
- Match depth to the question; keep the voice calm, natural, and free of
  recognizable "AI answer" rhythm.

For code-reading questions, each key claim is tagged **源码事实** (visible in the
source) / **推断** (follows from control or data flow) / **待验证** (needs a
runtime or documentation check).

## Pairs with geeklens

When `geeklens` produces an annotated reading edition, `calm-explain` is the
explanation protocol for it: geeklens owns the artifact shape, calm-explain owns
the explanation style and evidence labels. `calm-explain` also works on its own.

## Install

Copy or symlink this directory into the agent's skills folder, keeping the
directory name equal to the `name:` field in the frontmatter (`calm-explain`):

```powershell
# OpenCode
Copy-Item -Recurse . "$env:USERPROFILE\.config\opencode\skills\calm-explain"

# Claude
Copy-Item -Recurse . "$env:USERPROFILE\.claude\skills\calm-explain"
```

Or with the Skills CLI:

```bash
npx skills add wurenrumian/calm-explain
```

## Contents

- `SKILL.md` — the skill itself.

## Related

- `geeklens` — focused annotated reading editions of real code (uses this skill's
  explanation protocol).
- `project-memory` — process memory under a project's `./tmp/`.
