---
name: citation-formatter
description: >-
  Formats academic citations and bibliographies in APA 7th, MLA 9th, Chicago/Turabian, Harvard, and IEEE styles with proper in-text and reference list entries. Use when formatting research paper citations, creating bibliographies, or converting between citation styles.
---

# Citation Formatter

Citation formatting has objectively correct answers per style guide — this isn't a judgment call the way most writing tasks are. Get the punctuation, ordering, and italicization exactly right, since a professor or journal checking citations will catch small deviations.

## Workflow

1. **Identify the style requested.** If not stated, ask — don't assume APA by default, since MLA (humanities) and Chicago (history) are just as common depending on the field. If the user mentions their field or assignment type, that's often enough to infer it (e.g. "my psych paper" → APA is a safe default, but confirm if there's any doubt).
2. **Get the source details.** If given a URL, try to identify author, title, publication/site name, and date from it rather than asking the user to manually extract these — but always show what you found so they can correct anything wrong, since automated extraction from a URL isn't always reliable.
3. **Identify the source type** (book, journal article, website, video, dataset, etc.) — each has a different citation template even within the same style, so get this right before formatting.
4. **Apply the exact template** for that style + source type from `references/style-templates.md`. Don't approximate from memory for less common types (datasets, social media posts, personal interviews) — check the reference file, since these are the ones people get wrong most often.
5. **For a full bibliography**, apply consistent formatting across every entry and alphabetize per the style's rules (usually by first author's last name), and apply the correct hanging-indent/spacing convention if the output format supports it.

## Common mistakes to avoid

- Mixing italics conventions — book/journal *titles* are italicized in most styles, but article titles within a journal typically aren't (they're in quotes instead, or plain in APA). Don't italicize everything indiscriminately.
- Author name ordering differs by style and by position (first author vs. subsequent authors) — check the specific rule rather than applying one format to all authors.
- "Et al." usage thresholds differ by style (APA: 3+ authors in-text after first citation; MLA: also 3+ but different in-text format) — check the specific rule, don't guess a shared threshold.
- Access dates for web sources are required by some styles for some source types and not others — check rather than always including or always omitting.

## What NOT to do

- Don't fabricate missing citation details (a publisher, a date, a DOI) — if information is missing, say what's missing and ask, or format with a clear placeholder like `[publisher not provided]` rather than inventing something plausible-sounding.
- Don't silently pick a citation style — always confirm or infer explicitly and state your assumption.

## Output format

```markdown
**Style:** [APA 7th ed. / MLA 9th ed. / Chicago 17th ed. (author-date or notes-bibliography — ask which) / IEEE / Harvard]

**Citation(s):**
1. [Formatted citation]
2. ...

[If converting between styles, show both the original and the converted version side by side so the user can verify nothing was lost.]
```

See `references/style-templates.md` for the full per-style, per-source-type templates.

## Verification & Quality Checklist
- [ ] Code compiles cleanly and passes all automated tests and typechecks without warnings.
- [ ] Edge cases, boundary conditions, and error states handled explicitly.
- [ ] No hardcoded secrets, test credentials, or insecure defaults introduced.
- [ ] Performance and resource utilization verified against baseline constraints.
