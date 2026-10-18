# Review mode

Use for feedback, review, or critique. Apply the visual style and S1–S5 in `../SKILL.md`. A review-only request authorizes feedback, not deck edits. For literature decks, also apply `literature-review.md`; the same checks support internal review during an authorized build.

Ask one short question for essential missing talk context, without repeating information already supplied. Render every slide and inspect it visually; do not rely on extracted text alone. Read the numbers printed inside figure panels.

Check both:

- **Craft:** use of space, figure construction, panel count, readable typography, consistent colors and symbols, finding-led titles, layout consistency, and typos.
- **Science:** what each figure shows; support for titles, subtitles, bullets, and tables; contradictions across slides; missing baselines, controls, uncertainty, or analyses; and whether content belongs in the main deck or appendix.

For literature evidence, compare the actual plots and claims with their primary-paper context. Verify the source figure/panel, numerical labels, APA footer, task/lead/metric, data-count convention, uncertainty meaning, and material qualifications. Check restored axes or legends numerically. Review the closing synthesis for whether it answers the motivating questions without adding unsupported claims or presenting proposed criteria as published results.

During an authorized build or revision, return material findings to the builder and recheck the repaired slides and final export. Keep finding IDs stable across revisions. Approval applies only to the version actually reviewed; do not silently carry it over after substantive changes. Internal review need not produce a separate user-facing report unless requested.

## Concise feedback in chat

Open with the three most consequential issues, in priority order, each with a slide reference. Then provide one block per slide in deck order:

```text
Slide N — "<exact title>"
- C-N.1 [craft] <specific, actionable issue quoting exact text or a number>
- S-N.1 [science] <specific, actionable issue quoting exact text or a number>
- Keep: <what works, if anything>
```

Use about three bullets at most per slide; prioritize high-impact issues and omit empty categories. Give each critique a stable ID, C-N.k for craft or S-N.k for science. Cite the exact text or number and the relevant S1–S5 standard where applicable.

Close with brief notes on what to keep, apparent errors that are not errors, and a numbered order of work. Keep the tone concise, professional, and specific, without praise padding.

## Full review PDFs

Only when the user requests PDFs or a full review, produce two separate PDFs:

1. **Presentation craft:** cosmetics and slide-making issues.
2. **Substance:** scientific findings, supported or contradicted conclusions, missing evidence, and main-deck versus appendix placement.

Use the user's specified output folder, or the current workspace's normal deliverables folder if none is specified. For each PDF, lead with the three most consequential issues, rank the remaining issues, provide numbered IDs and exact slide/text/number references, note what to keep and what is not an error, and finish with the recommended order of work.

Use the PDF skill for generation. Render and inspect the PDFs, and verify slide references before delivery.
