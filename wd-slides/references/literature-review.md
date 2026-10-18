# Literature-review decks

Use this reference when building or substantively revising a scientific literature review. The approved pattern is a coherent argument built from large original paper plots, concise interpretation, visible caveats, APA footers, and a closing synthesis. A collection of text summaries or a research-plan deck does not substitute for the requested literature review.

## Scope and story

- Translate the user's questions into a narrative before selecting plots. Choose studies for their evidential role: a comparison, mechanism or conditional theory, performance determinant, scaling relationship, data requirement, or limitation.
- Use project details to select relevant literature. In a literature-only deck, exclude the user's previous experimental results unless the user asks to include them. Do not carry results from a style reference or an older deck into the review as evidence.
- Prefer primary papers and official proceedings/publisher records. Verify author lists, dates, titles, publication status, and the version actually supplying the figure. Treat a suggested bibliography as leads to verify.
- When asked for more literature, add studies that answer a missing part of the question, including differing regimes or limitations; avoid adding papers merely to increase the count.
- End with one story-summary slide by default. Connect the supported findings, answer the motivating questions, and state what remains conditional. Label a new decision rule or sufficiency criterion as the review's synthesis, not a published result. The synthesis slide need not contain a paper plot.

## Original plots and source traceability

For each evidence slide, select the key original figure or panel from the paper. Keep the full figure, caption, and relevant methods/results available during review.

1. Preserve the plotted data, numerical values, uncertainty bands, axes, and original color/marker mappings. Use clean crops and uniform scaling; do not fabricate, digitize and redraw, or generate a replacement curve merely to improve appearance. Use a reconstruction only when requested or necessary and explicitly identified as such.
2. Crop whitespace and irrelevant panels without removing information needed to interpret the result. A crop may depend on a shared axis or legend elsewhere in the source. Restore those labels faithfully outside the data region, verify their values and positions, and disclose the restoration in the source line or notes. Never infer a dataset's minimum or maximum from tick endpoints alone.
3. Put the figure/panel identifier and a full APA reference with DOI or stable primary-source URL at the bottom of each evidence slide. Preserve source readability with a dedicated footer; move or split content before shrinking it excessively. Check that long URLs remain intact in the final export. Use in-text APA citations on the synthesis slide, with full references elsewhere in the deck or accompanying notes.
4. Record enough provenance in speaker notes or a source guide to recover the evidence: paper/version, figure/panel, page when helpful, source link, and any cropping or restored labels. Exact crop comparisons or a private provenance manifest are useful for large rebuilds or disputed plots; they are not mandatory user deliverables.

## Explain the evidence precisely

Each slide should make one supported point. Use a finding-led title, an explanatory blue subtitle, a dominant plot, and short adjacent interpretation. Add equations only when they clarify the claim; define their symbols and verify subscripts, superscripts, signs, and units in the actual export. Essential interpretation and limitations belong on the slide; detailed methods and derivations belong in notes.

Check the claim against the paper's actual experiment:

- **Task and system:** scientific target, domain or simulator, evaluation setting, and whether a result is classification, probability prediction, regression, or another task. Check event definitions and forecast horizons when applicable.
- **Comparison:** methods, inputs, architectures, model sizes, training/tuning treatment, baselines, and prior or pretraining data. A performance difference alone does not identify its causal mechanism.
- **Axes and metrics:** exactly what each axis counts, its units, normalization, and whether larger or smaller is better. Do not interchange loss, RMSE, relative error, or skill scores.
- **Uncertainty:** distinguish standard deviations, confidence intervals, interquartile ranges, variability across folds/seeds, and fitted/reference lines. Preserve the source's meaning; disclose absent uncertainty when it limits the conclusion rather than inventing it.
- **Claim scope:** distinguish measured behavior from explanation, hypothesis, extrapolation, and proposed work. Do not promote a conditional theory or a single benchmark into a universal law.

Resolve apparent inconsistencies among the figure, caption, main text, appendix, and publication versions. State which source the slide follows and disclose a material unresolved discrepancy. Qualify or omit claims that cannot be verified.

### When the review concerns scaling or required data

Keep unique examples, trajectories, archive duration, overlapping samples, repeated training exposure, model parameters, state/grid dimension, and compute separate. Explain the counting convention next to the relevant plot; do not equate a large count with independent information. Account for pretraining separately from downstream data.

Distinguish data scaling from parameter scaling and compute scaling, and retain the learning regime, metric, model capacity, and any fitted error floor. A plateau can reflect the chosen architecture or training protocol; it is not automatically a physical limit or the minimum data needed for skill. Sample sufficiency requires a stated task, evaluation setting, baseline, practical target, and appropriate uncertainty, with a forecast horizon when applicable. If the literature cannot establish a robust minimum, say so and label any proposed criterion as synthesis. Keep dependence, selection/tuning, and final held-out confirmation in the supporting explanation when relevant.

## Build and review loop

Follow the working mode selected in `../SKILL.md`. For Team mode, read [team-workflow.md](team-workflow.md); substantial paper sets can be divided among several researchers while reviewers inspect completed slide batches. In Solo mode, apply the same source and render checks as separate self-review passes.

Give actionable findings with slide numbers and required corrections. Return material science or visual failures to the builder, then review the repaired revision. Inspect every slide at least once, including the closing summary, and inspect the final export: conversion can change fonts, wrapping, equations, and citations. Unchanged slides need not be repeatedly re-reviewed when their identity is verified. Tie approval to the actual final revision, and report any unresolved source or native-rendering limitation honestly.
