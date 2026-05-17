# Contributing

Thanks for considering a contribution. This list is curated and opinionated, so our bar for new entries is meaningful. Removals, recategorizations, and rewrites are equally welcome.

## Scope

We cover strict mechanistic interpretability. An entry qualifies if it engages with model internals, meaning circuits, features, sparse decompositions, causal interventions on activations, or activation steering grounded in features or circuits.

Several adjacent areas sit outside our scope. Post-hoc XAI methods like LIME, SHAP, and basic saliency do not fit. Attention-as-explanation work without mechanistic backing does not fit. Capability benchmarks, RLHF and instruction-tuning research that ignores internals, and probing work that does not connect to features or circuits also fall outside. Borderline cases get decided on the strict side, so when in doubt, open an issue before sending a PR.

## Quality bar

We accept entries that meet at least one of four bars. Canonical entries are landmark results researchers cite repeatedly, like Toy Models of Superposition, IOI, ROME, or the transformer circuits framework. Methodologically useful entries describe a technique, tool, or library a researcher could plausibly use next week. Pedagogically useful entries are walkthroughs, tutorials, glossaries, or courses that demonstrably accelerate a newcomer. Serious replications and critiques also qualify, since empirical pushback matters as much as original results.

An entry must earn its slot. Existing is not enough.

## Entry format

Use this exact shape, with one blank line between entries.

```markdown
- [Title](URL). One-sentence description, sentence case, ending in a period.
```

Keep descriptions short and substantive. Write in sentence case, with proper nouns and technical terms capitalized normally. Skip marketing language. Words like "amazing", "awesome", "comprehensive", and "carefully curated" will not pass review. State what the work is and why it matters.

Use one canonical link per entry. Prefer arxiv abstracts over PDFs, transformer-circuits.pub over the matching Anthropic press page, an official project page over a GitHub mirror, and the original publication URL over any tracker copy. If a secondary link genuinely helps, like a project page, a published version, or a walkthrough, include it in the same entry in parentheses with "See also" leading the link.

Use the actual title from the source rather than paraphrasing. If you are unsure where an entry belongs, propose a section in your PR description and we will sort it out together.

## Section ordering

Ordering within each section is pedagogical, with foundational works first. Tools and Libraries entries are alphabetical within each sub-area.

## Submitting a PR

Fork the repository, work on a descriptive branch like `add-mib-benchmark`, and edit `README.md`. Keep one logical change per PR. Sending ten unrelated entries in a single PR will get split. When you open the PR, fill in the template and explain in a sentence or two why the entry meets the bar.

## Removing entries

Open a PR removing an entry when a link is dead, when a work has been retracted or superseded, or when an entry no longer earns its slot. Include a one-line justification.
