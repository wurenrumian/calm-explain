# Math and notation

Referenced from `SKILL.md`. Read this when the answer will contain formulas.

Use math when a relation or quantity is clearer as symbols than as a sentence. If the prose already says it well, skip the math. Write math in MathJax-compatible LaTeX so it renders in any Markdown-plus-MathJax viewer.

- **Inline or display.** Use `$...$` for a short symbol inside a sentence, such as latency $L$. Use `$$...$$` for an equation that carries the argument of the paragraph and deserves its own line. Prefer these over `\(...\)` and `\[...\]`.
- **Name the symbol in words first.** The first time a quantity appears, say what it is ("call the latency $L$"), then keep using $L$. Use one symbol per concept. Switching to a synonym makes the reader lose track.
- **Let the words carry the meaning.** A display equation restates the idea precisely. It should not replace the explanation. A reader should be able to follow the surrounding sentences without decoding the formula first. Say in words what each side means and why this step follows.
- **Keep equations easy to spot.** Put an equation on its own line only if the answer refers back to it. Number it, like `(1)`, only when the text cites it. A one-off expression usually fits better inline.
- **Think about the renderer.** If the viewer might not render math, it will show raw LaTeX. In that case keep the plain-text form short and conventional, and say which notation you are using when it matters. Escape a literal dollar sign, or put it in backticks, so it is not read as the start of a formula.
- **Don't use a formula to skip a step.** When the derivation matters, explain the reasoning in words, and let the formula state the final result exactly.
