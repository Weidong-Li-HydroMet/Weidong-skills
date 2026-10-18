# Pedram's Scientific Judgment: Current Evidence Cards

Verified through 2026-10-18. The 17 records represent 16 paper or official-statement families. The two monsoon papers come from the same closely related project and must not be treated as two independent validations across domains. See `sources.json` for source metadata, versions, and access limitations.

This document distills discussion practices supported by public work; it cannot substitute for his own judgment. The "recommendations" below are operating guidance for a research assistant, not his verbatim instructions. The 2026 first-author paper S02 provides the strongest basis for personal attribution: its Author contributions explicitly credit PH with conceptualization and writing the original draft. Other papers should generally be attributed to their author teams. Corresponding or last authorship does not mean that he proposed every statement.

## Judgments to Prioritize Currently

### 1. Establish the task before deciding which physical properties are worth preserving

- Evidence: The newest strongly attributable source inspected here, [S02](https://arxiv.org/html/2608.25835v1), §3 Discussion, especially the final paragraph distinguishing days-ahead large scales from predictability/climate; the model comparisons and scope in [S17](https://arxiv.org/html/2511.00274v2), §4.2.
- Supported inference: Being "more like the full physical system" cannot automatically be equated with "better prediction on the specified metric." Coarse-graining may benefit short-term large-scale forecasting while losing properties such as realistic error growth.
- Discussion recommendation: State the target variables, spatial scales, lead times, use case, and metrics at the outset. Report predictive skill and physical diagnostics separately. If they conflict, present the tradeoff and its mechanism.
- Strength and limits: S02 supports strong personal attribution but remains a preprint. Some climate risks are explicitly posed as questions and must not be presented as proven universal failures.

### 2. Diagnose missing information before discussing architectures, loss functions, and constraints

- Evidence: The controlled experiments in [S02](https://arxiv.org/html/2608.25835v1), §§2.3–2.4, and the discussion of training-data scales and architecture/loss in §3; [S08](https://pmc.ncbi.nlm.nih.gov/articles/PMC12130898/), Summary and Discussion; the distinctions among losses, function libraries, and target construction in [S14](https://arxiv.org/html/2306.05014v3), §4.
- Supported inference: Separating insufficient observational or training information, optimization problems, representational capacity, and generalization problems usually provides more explanatory power than immediately replacing the network.
- Discussion recommendation: Map the information chain: original system → sampling and filtering → labels → model → evaluation. Identify the level at which the bottleneck occurs and design experiments that change one factor at a time.
- Limits: Do not turn this into "architecture never matters." S14 and S15 both provide concrete examples of representational structure affecting results.

### 3. Prioritize controls that distinguish mechanisms over demonstrations of improved performance alone

- Evidence: [S12](https://nadirjeevanjee.com/papers/jeevanjee2017a.pdf), PDF pp.4–6, §§3.1–3.3; the experiments removing strong tropical cyclones globally versus regionally in [S08](https://pmc.ncbi.nlm.nih.gov/articles/PMC12130898/); [S02](https://arxiv.org/html/2608.25835v1), §2.3, which changes training information while holding the network and loss fixed.
- Supported inference: Mechanism testing, controlled simplification, and model hierarchies show continuity from earlier to recent work.
- Discussion recommendation: List at least one competing explanation for the claim and propose an experiment in which the two explanations predict different outcomes. Do not treat agreement among multiple models with shared biases as independent ground truth.
- Limits: The 2017 material is a collaborative perspective article and can serve only as a long-term methodological anchor.

### 4. Define OOD, gray swans, and generalization in testable terms

- Evidence: The removal experiments and Summary and Discussion in [S08](https://pmc.ncbi.nlm.nih.gov/articles/PMC12130898/); [S09](https://arxiv.org/html/2505.10241v3), §§3–5, on extrapolation, translocation, and effective receptive fields.
- Supported inference: An event being locally rare or record-breaking does not mean that its dynamical patterns are absent from the global training data. A successful case alone cannot establish true extrapolation.
- Discussion recommendation: Specify the training set, variables, and dynamical structures relative to which OOD is defined. Distinguish geographic transfer, extrapolation in magnitude, and new mechanisms. Where retraining with data removed is feasible, prioritize that causal control.
- Limits: The effective-receptive-field analysis for Dubai provides explanatory evidence of a different strength from the removal-and-retraining experiments for tropical cyclones. Do not combine them into a claim that "all extremes can/cannot be predicted."

### 5. Specify the role and conditions of applicability of physical constraints

- Evidence: The three opening criteria concerning structure, energy transfer, and coupled statistics, and the conclusions in [S03](https://arxiv.org/html/2509.20365v3); [S08](https://pmc.ncbi.nlm.nih.gov/articles/PMC12130898/), Forecasts Lack Physical Consistency; the comparison paragraph beginning "Incorporating physics" near the end of [S11](https://pmc.ncbi.nlm.nih.gov/articles/PMC9991455/).
- Supported inference: Physical knowledge remains valuable, but explain what it constrains, across which regimes it holds, and why it improves the target task. Similar residuals for a particular physical balance do not imply similar forecast skill.
- Discussion recommendation: Replace "adding physics" with a specific proposition and an ablation experiment. Report benefits, costs, the range in which it works, and the range in which it fails.
- Limits: S11 has now been supplemented by full-text verification using the published PDF. Do not elevate "universal constraints may be useful" into a mandatory priority. S03's stability has explicit resolution conditions.

### 6. Test offline fits through coupled runs and target statistics

- Evidence: [S14](https://arxiv.org/html/2306.05014v3), §4; [S15](https://arxiv.org/html/2407.05224v2), Results and Discussion; the NGM4/NGM6 comparison and conclusions in [S03](https://arxiv.org/html/2509.20365v3).
- Supported inference: High correlations, low errors, or higher-order closure expressions are insufficient to establish practical scientific value. Feedback, stability, energy processes, and long-term statistics may change the ranking.
- Discussion recommendation: Arrange a priori, a posteriori, and key-mechanism diagnostics according to the intended use. Identify the feedback responsible for online failure rather than merely adding an aggregate score.
- Limits: Long-term coupled behavior is not the sole criterion for every short-term prediction task. Use this principle together with item 1.

### 7. Favor concise results that yield explanations and testable theory

- Evidence: The progression from AI discovery to an analytical derivation through Taylor expansion, and the NGM4/NGM6 discussion in [S03](https://arxiv.org/html/2509.20365v3); the results and discussion linking convolutional-kernel spectra to transfer learning in [S11](https://pmc.ncbi.nlm.nih.gov/articles/PMC9991455/); [S12](https://nadirjeevanjee.com/papers/jeevanjee2017a.pdf), §3.1.
- Supported inference: Simpler mechanisms or expressions are valuable when they provide sufficient explanatory power and performance on the target task. AI can help generate theory rather than only replace simulators.
- Discussion recommendation: Provide the simplest sufficient explanation and test its parameter dependence and transferability. Explain what additional capability a more complex approach provides.
- Limits: This is a synthesis of moderate strength across collaborative papers, not a rule that "smaller models are always better" or "transferring shallow layers is always best."

### 8. Assign AI and physical models roles they can perform well

- Evidence: [S04](https://arxiv.org/html/2510.27066v3), Figure 1, the algorithm description, and Discussion.
- Supported inference: AI can be valuable by guiding expensive simulations without independently serving as the ultimate ground truth for extreme-event probabilities.
- Discussion recommendation: Define separate responsibilities for proposal/guidance, trajectory generation, probability estimation, and validation. Identify how errors propagate from each stage.
- Limits: Validation within PlaSim does not amount to real-world validation. Do not generalize the advantages of this hybrid approach into a claim that all hybrid methods are more reliable.

### 9. Baselines must reflect the information actually available and the user's problem

- Evidence: [S05](https://arxiv.org/html/2602.03767v1), Introduction and operational benchmarking methods; [S06](https://arxiv.org/html/2603.07893v1), Decision-theory and Discussion.
- Supported inference: Recent projects emphasize task definition, users' decisions, operational schedules, and genuinely additional information.
- Discussion recommendation: Use data available when the decision is made. Compare against reasonable baselines that update dynamically. Include false alarms, missed events, and different lead times, and do not select favorable initializations after the fact.
- Limits: This is collaborative evidence from the same related project. Agricultural examples do not imply that all his research must immediately lead to commercialization or policy applications.

### 10. Separate mathematical guarantees from empirical coverage and extreme-event performance

- Evidence: The method and guarantees in [S07](https://arxiv.org/html/2606.19642v1), §2.1, and the limitations concerning extremes, precipitation, and multiple variables in §4.
- Supported inference: Probabilistic scores, ensemble size, marginal coverage, conditional coverage, and joint physical consistency are different properties.
- Discussion recommendation: Accompany every guarantee with its applicable objects, time scales, assumptions, and cases not covered. Test important subgroups or extreme ranges and state whether correlation structures are disrupted.
- Limits: Asymptotic time-averaged marginal coverage does not imply reliability for every event. Do not claim that conformal prediction has solved all extreme-forecasting problems.

### 11. Be transparent about confounding, scope, and unconfirmed mechanisms in comparisons

- Evidence: Input differences and the limitations of historical experiments in [S17](https://arxiv.org/html/2511.00274v2), §4.2; the qualifications on "butterfly-like" in [S02](https://arxiv.org/html/2608.25835v1), §2.4; [S12](https://nadirjeevanjee.com/papers/jeevanjee2017a.pdf), §3.3.
- Supported inference: Valuable results do not need overextended interpretations to strengthen them. A model's differences from a numerical weather model do not by themselves establish that it is wrong.
- Discussion recommendation: Write results, mechanistic explanations, conjectures, and future questions separately. List the controls most likely to overturn the main conclusion. Disclose differences in inputs, boundary conditions, and versions.
- Limits: Do not elevate historical prescribed-ocean experiments into demonstrated validation of future coupled climate change.

## A Question Framework for Group Meetings

These are assistant-generated questions based on the evidence, not a claim to reproduce his own questions:

1. What exactly are we predicting or explaining, or which decision are we supporting? Why does this metric correspond to that objective? [S02, S05]
2. What is the strongest competing explanation? Which control can distinguish it? [S08, S12]
3. Does the result arise from more information, a different representation, improved optimization, or a physical mechanism? [S02, S14]
4. Which distributional boundary does the claimed generalization cross? Do the training data already contain similar dynamics? [S08, S09]
5. What information does the strongest reasonable baseline use? Does the evaluation take place under realistic operational conditions? [S05, S06]
6. Under what conditions does the claim fail? Which limitations have been demonstrated experimentally, and which are only concerns? [S03, S04, S07, S17]

## Priorities for Use

Use the latest material to update the question framework first, while assessing scientific evidence strength separately. Recent first-author work with explicit writing responsibility, S02, carries the most weight for the "current public position." Rigorous controlled experiments provide stronger grounds for mechanistic judgments; reviews with multiple authors, explanatory articles, and webpages provide background. The final publication year does not automatically update the content date of an older preprint. S09 has been updated to 2026-02-02 v3. The published status of S09 and S17 does not make their unread final texts verified.
