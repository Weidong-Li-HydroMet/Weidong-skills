---
name: "wd-reading"
description: "Fast, structured read of a research paper (ML / deep learning, esp. emulators of physical dynamics, probabilistic forecasting, diffusion) so the user can decide quickly whether it deserves a deep read. Use whenever the user uploads a paper PDF, pastes an arXiv/OpenReview/DOI/conference link, or asks things like 'is this paper good', 'summarize this paper', 'should I read this', 'can I trust these results', 'is this reproducible', 'is this useful for my work', or types $wd-reading. Also use when the user asks about a paper by title or arXiv ID without attaching it. Three modes: quick (default — motivation, setup, method, one-sentence summary), normal (adds believability checklist and transfer analysis), detailed (adds a walkthrough of every figure and table). No verdict or score — analysis only."
---

# WD-reading

The user is a deep-learning researcher who wants to decide in a few minutes whether a paper is worth a full read. They care about four things, in this order: what problem and why, what the method actually is, how much the results can be believed, and whether the *idea* transfers to their own research (not whether they could rerun the experiments). They explicitly do not want a thumbs-up/thumbs-down — they want the evidence laid out so they can decide themselves.

## 0. Pick the mode

The three modes follow Keshav's three-pass method ("How to Read a Paper", 2007): pass 1 decides whether the paper deserves more time, pass 2 grasps the content via the figures, pass 3 virtually re-implements it and challenges every assumption.

| Mode | ≈ Keshav pass | When | Output |
|---|---|---|---|
| **quick** (default) | 1 | No mode mentioned, or "quick", "tl;dr", "briefly", "just the idea" | §5a: motivation, problem setup, method, one-sentence summary |
| **normal** | 2 | "normal", "full", "is it believable", "reproducible", "useful for my work", or any question about trust/transfer | §5b: quick + believability checklist + transfer + questions for authors |
| **detailed** | 3 | "detailed", "walk me through the figures", "explain every figure/table", "deep read" | §5c: normal + one entry per figure and table |

If the user asks a question that only one section answers (e.g. "is the baseline fair?"), answer that section in normal depth rather than running the whole template. Read the paper the same way regardless of mode — the mode changes what is written, not how carefully you look. In quick mode, still read the main results table so the summary sentence is not just the abstract paraphrased.

## 1. Get the paper

- **Uploaded PDF**: use the available PDF-reading skill and tools in the current environment to extract text *and* render pages as images. Look at the figures and read the numbers inside tables and figure panels — the abstract is marketing; the tables and appendix are where believability lives.
- **Link or arXiv ID**: use the available web, search, and document-retrieval tools to open the abstract or landing page and retrieve the PDF. If only a title is given, search for it first and confirm you have the right paper (title, authors, year) before analysing.
- Check whether code is linked (GitHub, project page) and whether it exists and is non-trivial. A repo link in the paper is not the same as a repo with training code.
- Never read linearly. Order: title + abstract → conclusion → figure 1 and the main results table → section headings → method → ablations → experimental appendix (hyperparameters, seeds, compute, baseline setup). Skim related work only to judge what is borrowed. The appendix is not optional: that is where the details that make or break reproducibility live.
- While skimming, answer Keshav's first-pass questions silently: what *kind* of paper is this (new method, analysis, benchmark, system, theory)? Which prior work does it build on? Do the assumptions look valid? What are the claimed contributions? Is it clearly written? These shape the motivation and method paragraphs.

If the paper, a figure, the appendix, or linked code cannot be accessed, say exactly what was unavailable and limit the analysis to material actually inspected. Do not imply that inaccessible material was checked.

Do not ask the user clarifying questions before reading unless the paper itself is missing or ambiguous. Read first, then analyse.

## 2. What to extract

**Motivation.** What gap or failure in prior work is claimed? Then the key question: does the paper *demonstrate* the gap (a figure, a failing baseline, a measured problem) or just *assert* it in the intro? Note which.

**Problem setup.** Not prose — a compact spec the user can scan in five seconds, in the style of a model-comparison table. Four lines, each a fragment, with the paper's own notation where it is short:

```
Input → Output:  X_t, X_{t-1}, b_t  →  X_{t+1}, X_{t+2}   (what, resolution/dims, horizon)
Architecture:    UNet (ConvNeXt blocks) + FiLM conditioning on noise ε
Loss:            Σ_k Σ_c λ_{k,c} ‖x̂ − x‖²  over a 6-step rollout   (write the formula if it fits on one line)
Training:        teacher-forced 1-step, then 6-step rollout fine-tune; 4×A100, 2 days
```

Then at most one sentence for data (dataset, scale, train/test split) and one sentence for the assumption that quietly makes the problem easier than the headline suggests (oracle access, teacher-forcing at eval, known horizon, in-distribution eval only). If the paper compares several variants, give the spec for the main one and name how the others differ in a few words each.

**Method.** The core idea in your own words, in 2–4 sentences, without the paper's branding. Separate what is new from what is borrowed. Identify the one or two design choices that actually carry the result (the ablations usually reveal this). If the method has a non-obvious cost (extra compute, extra data, a second model, inference latency), say so.

**Believability / reproducibility.** Fill in the checklist in §3 with evidence, not impressions. Every row cites where in the paper the evidence comes from (table, figure, section, appendix) or says "not stated".

**Transfer to the user's research.** See §4.

## 3. Believability checklist

Mark each row ✓ / ✗ / ~ (partial or unclear) and give the evidence location. Why this matters: a paper with ✗ on baselines or seeds can still have a great idea, but its numbers should not be used as a reason to adopt it.

| Check | What to look for |
|---|---|
| Code released | Link present; repo exists; includes training code, not only inference/weights |
| Data available | Public, or described well enough to rebuild |
| Hyperparameters & compute stated | LR, schedule, batch size, epochs/steps, hardware, wall-clock; *and* the search range/budget used to pick them — a tuned method vs untuned baselines is the commonest unfair comparison |
| Baselines fair | Baselines retuned or taken from their papers under the same setup? Same compute/data budget? Strongest recent baseline included? Is a trivial baseline (persistence, climatology, linear, last-value) reported? |
| No leakage | Train/val/test split stated; no temporal or spatial overlap; no tuning on test; benchmark not seen during pretraining |
| Ablations isolate the claim | Each claimed component removed separately; gains don't vanish |
| Variance reported | Multiple seeds, error bars or CIs; are the gaps larger than the noise? |
| Held-out evaluation | Results beyond the benchmark the method was developed on; any OOD or scale sweep |
| Claims match evidence | Does the title/abstract claim more than the tables show? Any cherry-picked metric or subset? Is a result on one benchmark family written as a general method claim? Is the metric defined precisely? |
| Source of gains identified | Does the paper explain *why* it works with evidence, or only speculate? Watch for mathiness and suggestive language standing in for an ablation (Lipton & Steinhardt, 2018) |
| Negative results / limitations disclosed | Where did it not work? A paper with no failures is suspicious |

After the table, add 2–3 sentences: which rows most threaten the headline claim, and the *first experiment* a sceptical reviewer would ask for. Most reproduction failures come from preprocessing, data splits, and undocumented details rather than from the method itself, so weight those rows accordingly.

## 4. Transfer to the user's research

The user's area: **deep-learning emulators of physical dynamics (ocean/climate), with a focus on probabilistic forecasting** — autoregressive rollouts of gridded fields, UNet/ConvNeXt and DiT-style backbones, diffusion and stochastic-interpolant samplers, ensemble generation (perturbed ICs, lagged ensembles, FiLM-conditioned noise), and probabilistic losses such as CRPS alongside rollout MSE. Typical concerns: long-horizon stability, spread/skill calibration, boundary forcing, and cost per ensemble member. (If the user names a different topic in the conversation, use that instead.)

Answer, in prose:
- What is the *portable idea* — the principle that survives if you throw away the specific architecture, dataset and task?
- What conditions does the result depend on (data scale, modality, supervision, compute, a particular inductive bias)? Which of those hold for gridded spatio-temporal fields with autoregressive rollout, and which do not (e.g. the method assumes i.i.d. samples, fixed-length sequences, or no error accumulation)?
- What would most likely break when moved to a different setting, and is there a cheap experiment that would tell you?
- Is there anything in the paper worth stealing even if the main claim is weak — a trick, an evaluation protocol, a dataset, a framing?

Do not write "this could be applied to many domains". Be specific or say the transfer is unclear and why.

## 5. Output formats

All modes default to chat; detailed mode uses the Markdown-file exception below when the output would exceed ~2 screens. Shared rules:
- No verdict, score, or recommendation to read/skip. Lay out evidence; the user decides.
- Quote exact numbers from tables when they matter ("+1.2 BLEU on WMT14 en-de, Table 2, single seed").
- Prefer "not stated" over guessing. If you could not open a figure or the appendix, say which.
- End with one line offering the next mode up ("Say *normal* for the believability check" / "Say *detailed* for a figure-by-figure walkthrough"). Skip this in detailed mode.

### 5a. quick (default) — under half a screen; every line a fragment, no filler

````markdown
**<Paper title>** — <authors, venue/year>, code: <link or "none">

**Motivation.** …(2–3 sentences; demonstrated vs asserted)
**Problem setup.**
```
Input → Output:  …
Architecture:    …
Loss:            …
Training:        …
```
…(≤1 sentence data, ≤1 sentence hidden assumption)
**Method.** …(2–4 sentences; new vs borrowed; load-bearing choices; cost)

**In one sentence:** <what they did, the headline number from the main table, and the one caveat that matters most>
````

The one-sentence summary is the part the user will remember, so make it carry information: a concrete claim with its evidence and its biggest weakness, not a restatement of the title. Bad: "A new method for efficient attention that outperforms baselines." Good: "Replaces softmax attention with a kernel approximation and matches the Transformer within 0.3 perplexity on WikiText-103 (Table 1) at 4× lower memory, but only at sequence lengths ≥ 4k and with a single seed."

### 5b. normal — roughly one screen

Everything in 5a, then:

```
**Believability**
| Check | ✓/✗/~ | Evidence |
… (11 rows from §3)
<2–3 sentences on the biggest threats to the claim>

**Transfer to your research.** …(1 short paragraph, per §4)

**Three questions I'd ask the authors.**
1. …
2. …
3. …
```

### 5c. detailed — as long as the paper needs

Everything in 5b, then a **Figures & tables** section with one entry per figure and table in the main text (appendix figures only if they bear on the believability checklist), in paper order:

```
**Figure N — <caption, shortened>**
- Shows: what is plotted — axes, units, conditions, which model is which colour/marker
- Says: the claim the authors draw from it
- Actually: what you read off it yourself — the real numbers, the gap size vs the noise, anything the caption or text glosses over (crossing curves, missing error bars, a baseline that wins on one subset, log axes that flatter the method)
```

For tables, "Shows" lists the rows/columns and the metric; "Actually" quotes the specific cells that make or break the headline claim and notes bolding that hides a near-tie.

This mode is Keshav's third pass: virtually re-implement the paper in your head, identify and challenge every assumption, and note what you would have done differently. This is where the rasterized pages pay off: look at every figure image, not the extracted text. If a figure is unreadable at the available resolution, say so rather than paraphrasing the caption.

In detailed mode, if the output would exceed ~2 screens, write it to a Markdown file (`<short-paper-name>-reading.md`), present it, and put the quick-mode block in chat as a preview.

## 6. Follow-ups the user may ask

- "Compare with <other paper>" → same checklist side by side, then a paragraph on where they disagree.
- "Is the baseline fair?" → go to the experimental appendix and quote the setup of each baseline.
- "Give me the math" → restate the key equations in plain notation with each symbol defined, and note any step that is asserted without derivation.

## 7. Sources this skill draws on

- S. Keshav, *How to Read a Paper*, ACM SIGCOMM CCR 37(3), 2007 — three-pass method; first-pass five Cs (category, context, correctness, contributions, clarity).
- J. Pineau et al., *Improving Reproducibility in Machine Learning Research*, JMLR 22, 2021 — the NeurIPS ML Reproducibility Checklist (runs, variance, hyperparameter ranges, compute, splits).
- Z. Lipton & J. Steinhardt, *Troubling Trends in Machine Learning Scholarship*, 2018 — explanation vs speculation, failure to identify sources of gains, mathiness, misuse of language.
- Kapoor et al., *REFORMS: Consensus-based Recommendations for ML-based Science*, Science Advances 2024 — leakage and evaluation pitfalls.