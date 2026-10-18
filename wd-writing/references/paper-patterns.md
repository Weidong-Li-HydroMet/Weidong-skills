# Writing structure examples from the core papers

Research date: 2026-10-18. The following is structural analysis, not a substitute for reading the papers or checking the science. Source families share identifiers W01–W13; see `sources.json`. Full main texts W01–W06 received focused reading. For SI, only the structure, references from the main text, and necessary excerpts were checked; no claim is made to have reproduced every equation or experiment. For the remaining papers, partial main-text reading is explicitly distinguished from abstract-only reading.

## W01 — 2026-08-26: Missing the Butterfly and Predicting the Past

[Fixed version](https://arxiv.org/html/2608.25835v1). First author and co-corresponding author; the contribution statement explicitly credits PH with writing the main text, with separate roles for the methods section.

- Abstract progression: established achievements → unexplained reasons → tests across a model hierarchy → unified explanation → tradeoff between fidelity and skill → significance.
- Introduction: combines several seemingly unrelated puzzles into one testable question. Backcasting serves as a diagnostic design rather than a separate application.
- Results sequence: establish the phenomenon in realistic/intermediate-complexity systems → control information completeness with Lorenz → return to the official Pangu model to test for the same trends.
- Captions: identify independent models, variables, quantities being averaged, thresholds, shading, and ranges of variation.
- Boundaries: distinguish butterfly-like behavior from a true butterfly effect, and chaos from multiscale error growth. Express future uses as hypotheses.
- Main text/SI: the main text retains the unified explanation and rebuttals; methods and supplementary material elaborate on systems, numerical controls, time reversal, and architecture.

## W02 — 2026-02-10 PRL: Analytical and AI-discovered closure

[Formal publication and authorship roles](https://journals.aps.org/prl/abstract/10.1103/v28b-5qmp), [v3 main text read](https://arxiv.org/html/2509.20365v3). Corresponding authorship is verified; the v3 contribution statement does not separately identify who wrote the manuscript.

- The abstract begins directly with the finding and uses shortcomings of earlier methods to explain why the new term is needed.
- The introduction defines success criteria before comparing which criteria existing methods satisfy.
- Argument: discovery criteria → analytical correspondence → offline comparisons → online trajectories/statistics/tails → practical boundaries.
- Captions distinguish structural correlations, energy transfer, normalized PDFs, and online metrics. The discussion retains the resolution conditions.
- SI/appendices provide expansions, results for each configuration, and numerical details; the main text explicitly states conditional stability.

**Limited, verified version differences:** Comparing [v1](https://arxiv.org/html/2509.20365v1) with v3, v3 clarifies that Δ in Eq.(4) is the filter width and gives its relation to grid spacing; Fig.3 makes normalization by the standard deviation clearer; and the conclusion adds discussion of scope concerning nonlocality, stochastic/memory effects, and implicit LES. These are textual differences; do not infer who made them or why. Both HTML versions contain anomalous main-text dates that conflict with the arXiv version history; use the formal publication page/version-history dates.

## W03 — 2025 PNAS: Gray swan tropical cyclones

[Full text](https://pmc.ncbi.nlm.nih.gov/articles/PMC12130898/). Co-corresponding author, not first author.

- Abstract: question → test that removes training events → failure and partial success → extrapolation limits/requirements.
- The introduction first distinguishes general forecasting achievements, rare events, and events outside the training set, then explains the controlled training-set design.
- Results: failure at extreme intensity → partial transfer across basins → physical-consistency diagnostics.
- Captions count events, model realizations, and perturbed initial conditions separately; they do not treat all forecast members as independent cyclones.
- The Discussion separates demonstrated findings, expectations for other models/types of extremes, and possible remedies.
- The SI contains controls involving additional global metrics, weaker events, and tracks, while the main text still explains which interpretations they rule out.

## W04 — 2024 JAMES: Promises and Challenges

[Published full text and CRediT](https://agupubs.onlinelibrary.wiley.com/doi/10.1029/2023MS003874), [preprint v3 read](https://arxiv.org/html/2306.05014v3). Corresponding authorship and original-draft writing are documented; the first author also has the latter contribution.

- The abstract acknowledges success, immediately presents online failure and physical diagnostics, then proposes the next step.
- The introduction organizes approaches into functional/structural/ML/equation-discovery categories; methods precede results.
- Results move from robustness of discovery to analytical connections, then examine numerical error, online instability, the candidate library, and filter dependence.
- Captions mark exceptions, different color-bar ranges, and normalization. The Discussion distinguishes “failure of the discovery process” from “failure of the closure model.”
- Appendices cover filtering, solvers, expansions, and energy definitions; the main text retains the key constraints under which its explanations hold.
- Do not treat the 2024→2026 follow-up research as version differences within the same paper.

## W05 — 2023 PNAS Nexus: Physics of transfer learning

[Publication page](https://doi.org/10.1093/pnasnexus/pgad015), [published PDF read](https://par.nsf.gov/servlets/purl/10472803). p1 has the corresponding-author footnote; p12 states that all authors wrote the manuscript.

- The abstract opens with two practical decision questions, then presents an analytical method, a framework, cases, and a counterintuitive finding.
- The introduction turns “which layers to retrain” from an empirical choice into a question needing explanation, and lists explicit research objectives.
- Results: generalization gap → layer selection → spectra of activations/convolution kernels → loss landscape → actionable workflow.
- Fig.2 explicitly defines every type of error bar/shading; the methods explain data independence.
- The Discussion makes clear that the best specific layers may depend on the case and architecture; the analytical framework is what transfers. The SI adds mechanism and sensitivity diagnostics.

## W06 — 2020 Nature Communications: Texas tropical cyclone movement

[Publication page](https://doi.org/10.1038/s41467-020-17130-7), [published PDF read](https://repository.library.noaa.gov/view/noaa/27538/noaa_27538_DS1.pdf). p1 identifies first and corresponding authorship; p9 states that PH/Lee wrote the manuscript together.

- The introduction narrows a practical regional problem into a question with clearly specified time, geography, and variables.
- Results establish, in order, physical intuition from the historical record, future mean changes, a mechanistic explanation, weather-pattern frequencies, and an independent downscaling test.
- Captions specify time windows, model ensembles, and statistical markers, referring readers to the SI for additional monthly and bias-corrected results.
- The Discussion explains apparently conflicting literature through differences in scope and methods while preserving unresolved disagreements.
- Implications must be accompanied by limitations: faster movement does not directly imply lower overall risk.

## Partially read samples and their uses

| Sample | Reading coverage | Usable writing observation | Unsupported inference |
|---|---|---|---|
| [W07 Dubai v3](https://arxiv.org/html/2505.10241v3) | Abstract, introduction, main results, and captions | Define local/global novelty first, then compare translocation/extrapolation; qualify claims when evidence is insufficient. | The abs/HTML/group webpage contents differ; do not construct an unverified revision history. |
| [W08 QBO](https://arxiv.org/abs/2407.05224) | Abstract | Use the mismatch between evaluation metrics and online behavior to motivate explanatory diagnostics. | Do not infer main-text ordering or that PH was the lead writer. |
| [W09 climate physics and simulations](https://arxiv.org/abs/2404.13227) | Abstract | A review first presents a classification framework that organizes the whole article. | Do not impose the experimental structure of a research paper. |
| [W10 physics of climate review](https://arxiv.org/abs/2408.09627) | Abstract | Present scientific progress alongside challenges; this can provide a contrasting example of genre. | Do not infer personal wording habits. |
| [W11 conformal prediction](https://arxiv.org/abs/2606.19642) | Abstract | First test blind spots in common evaluations, then state the remedy. | Do not restate unverified details of mathematical guarantees. |
| [W12 monsoon benchmark](https://arxiv.org/abs/2602.03767) | Abstract, attachment index, and verified corresponding-author block | Define evaluation objectives through users' decisions, then connect them to applications. | Do not present the scale of forecast dissemination as measured social benefit. |
| [W13 semi-analytical closures](https://arxiv.org/html/2504.09670v3) | Abstract, introduction, derivation, and opening of the results | Place terminology qualifications immediately after the method: semi-analytical, domain-averaged constants, scope of assumptions. | The contact email belongs to Guan; neither a two-author paper nor last authorship establishes that PH is the corresponding author. |

## Known reading limitations

Reading the full main text does not constitute scientific reproduction or a complete reading of the SI. Text extracted from older two-column PDFs may interleave columns; cross-check structural judgments against sections, captions, and page numbers. All quantitative references here support analysis of research writing structure and should not enter a user's new manuscript without a second verification. Web caches/HTML conversion may introduce mathematical typesetting errors; consult original PDF figures and equations before adding scientific conclusions.
