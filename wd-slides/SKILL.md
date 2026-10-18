---
name: "wd-slides"
description: "Create, edit, or review scientific presentations using the user's WD slide standards: Avenir, black bold titles, blue subtitles, dominant scientific figures, concise explanations, and dark red or blue highlights. Supports automatic, multi-agent team, and solo workflows. Literature reviews use verified paper plots, APA footers, a coherent synthesis, and science and visual review. Default to editable Google Slides; honor the user's chosen format."
---

# WD-slides

Create an editable Google Slides presentation by default; honor an explicitly requested or accepted alternative format. Apply the scientific standards below during both creation and review. For literature-review decks, also read [references/literature-review.md](references/literature-review.md). When the user asks only for feedback, use [references/review.md](references/review.md); do not create or alter a deck for a review-only request.

## Understand the talk

Use the supplied research, figures, data, and existing slides. If essential context is missing, ask one concise question covering only what is needed: topic, audience, talk duration, and purpose. Do not ask again for information already provided. A style reference alone is not evidence for a new scientific talk.

Use the available Presentations skill for deck handling and visual verification. For native Google Slides work, use a connected Google Slides/Drive capability or an authenticated browser workflow when available.

## Working mode

The user can select a mode in ordinary language; these are workflow preferences, not special tool parameters:

| Mode | Behavior |
| --- | --- |
| **Auto** (default) | Choose a proportionate workflow. Use a team when independent research, slide sections, or review can usefully run in parallel; handle small edits directly. |
| **Team** | Use multiple collaborating agents for research, building, science review, and WD visual review. Scale the team to the paper set or deck; honor a requested agent count within available capabilities. Read [references/team-workflow.md](references/team-workflow.md). |
| **Solo** | Complete the work without subagents, using separate science and visual self-review passes. Do not describe these as independent review. |

Examples: `$wd-slides — team mode, use 6 agents` or `$wd-slides — solo mode`. Requests such as “call the agent team” or “let several agents work together” select Team mode without another confirmation. If no mode is given, use Auto without asking the user to choose. When Auto selects delegation, follow [references/team-workflow.md](references/team-workflow.md); otherwise use separate science and visual self-review passes. A selected mode persists for the current deck until the user changes it. Mode selection does not expand a review-only request into permission to edit.

## Visual style

Inspect [references/slide-style-reference.png](references/slide-style-reference.png) when creating or restyling a deck. It defines the visual direction: a white canvas, a centered title with a subtitle directly below it, large scientific figures, aligned panels, and generous whitespace. Its scientific content is an example, not reusable evidence. Preserve the original image unchanged.

The user's requirements are Avenir typography, a **black bold title**, a **blue subtitle**, concise scientific writing, and colored emphasis limited to **dark red and blue**. Default to a 16:9 canvas for a new deck; preserve an existing deck's dimensions unless asked to change them.

Use these adjustable starting sizes; the user did not specify exact point sizes:

| Element | Default | Treatment |
| --- | --- | --- |
| Title | 36 pt | Avenir, bold, black; preferably one line |
| Subtitle | 28 pt | Avenir, blue; one concise quantitative or explanatory line |
| Body | 22 pt | Avenir, black; short statements |
| Figure labels and legends | 18 pt at final slide size | Avenir when editable; readable at presentation distance |
| Sources and secondary notes | 14 pt | Avenir, black or neutral gray; essential findings and limitations stay larger |

Use blue `#4285FF` and dark red `#8B0000` as the default accent shades. Bold selected words or values sparingly; add color only when it helps identify the key comparison, result, or limitation. Keep the title black. Do not introduce other highlight hues. Black, white, and neutral gray remain available for ordinary text, axes, and structure.

For newly generated figures, use consistent blue/dark red encodings where appropriate. Distinguish additional methods with symbols, line styles, and direct labels. Continuous blue–white–dark red scales are appropriate when scientifically meaningful. Preserve the quantitative meaning and established mappings of supplied figures; do not recolor a raster figure merely to match the accents. If a supplied figure needs restyling, use its data or editable source.

Keep figures dominant, crop unnecessary surrounding whitespace without removing scientific content, and align comparable panels and axes. Use a restrained blue or dark red outline or annotation when a comparison needs emphasis. Avoid decorative panels, gradients, stock imagery, and text-heavy layouts.

Use Avenir for editable slide text and regenerated figure labels. Check whether the chosen target application actually renders Avenir; setting a font name alone is not proof. If unavailable, report the limitation and resolve a substitute with the user before describing the typography as final. Do not flatten slide text into images just to simulate the font. Preserve mathematical notation and supplied scientific graphics when their editable sources are unavailable.

## Scientific standards

- **S1 — Finding-led titles.** State the supported result rather than a generic topic. For planned work, state the objective or test explicitly; never present a planned outcome as an observed finding.
- **S2 — Consistent method encoding.** Keep each model or method's color, symbol, and line style fixed in newly created graphics. Preserve original paper encodings; when papers use different mappings, retain their legends and explain the difference rather than recoloring the evidence. Restrict new accent colors to blue and dark red.
- **S3 — About six figure panels maximum.** Split denser comparisons across slides or move secondary evidence to the appendix. The reference image has ten panels; reproduce its hierarchy, not its density, unless the user explicitly requests an exact reproduction.
- **S4 — Readable figures.** Check axes, ticks, legends, panel labels, and annotations at final slide size. Enlarge, simplify, or split the slide before shrinking essential text.
- **S5 — Visible limitations.** Put material limitations of the evidence, including published studies, on the slide where it appears. Keep caveats brief and legible; reserve secondary qualifications for speaker notes.

Write concise, precise scientific prose. Give each slide one main message. Prefer a quantitative statement supported by a figure to a paragraph of narration. Use consistent notation, units, significant figures, and terminology. Distinguish observation, interpretation, hypothesis, and plan; distinguish association from causation. Do not invent data, metrics, uncertainty estimates, citations, or results. Define an unfamiliar metric before interpreting it.

Check that titles, subtitles, bullets, figures, and summary tables agree. Identify missing baselines, controls, uncertainty, and analyses that materially affect the claim. Qualify or remove unsupported claims. Put detailed derivations and secondary checks in speaker notes or the appendix when they are not needed for the main message.

For literature reviews, build the explanation around original primary-paper plots, with only the text and equations needed to interpret them. Put the source figure/panel and an APA citation at the bottom of every evidence slide. End with a story-summary slide that answers the motivating questions and distinguishes supported conclusions from proposed criteria. Keep the user's prior results out of a literature-only deck unless explicitly requested.

## Create and verify the deck

1. Map the supplied evidence into a short narrative suited to the audience and purpose. Organize literature around the questions it answers, rather than one unconnected paper per slide. Use existing context to choose a reasonable slide count. Keep main-deck and appendix roles clear.
2. Build the slides with editable titles, subtitles, body text, annotations, and shapes. Use supplied or faithfully generated scientific figures; do not use generated illustrations as scientific results. Apply the visual style and S1–S5 throughout.
3. For the default Google Slides workflow, create a native presentation and return its working link. A local PPTX can be an intermediate source, but it is not completion of an explicit Google Slides request. If the required Google connection is unavailable, continue preparing the content and editable source, explain the specific blocker, and request only the missing connection. If the user has chosen another format, finish that format without making Google sign-in a requirement. Do not substitute a different cloud presentation service without the user's agreement.
4. Render and inspect every slide, including figure-panel numbers, at presentation scale. Verify the resulting deck in the chosen target application after creation or import; check font rendering, clipping, overlap, image resolution, color consistency, slide order, and scientific accuracy. Fix issues before delivery. For Google Slides, inspect the native imported/created deck. If only a local export can be inspected, state the limit of that verification without requiring an unrelated application.
5. Complete science and WD visual reviews before delivery. In Team mode, follow [references/team-workflow.md](references/team-workflow.md); in Solo mode, use separate self-review passes. Return findings to the builder and recheck the repaired slides; do not treat a draft or an earlier revision's approval as final approval.
6. Deliver the chosen editable format and, when useful, a visually checked PDF plus speaker notes/source guide. Give a concise note about additions and any unresolved source, font, or native-rendering limitation. Keep internal review logs out of the user-facing deck unless requested. Do not change sharing permissions or publish the deck unless requested.

For an existing deck, apply changes within the user's requested scope. For a review request, read the review reference and evaluate the same typography, writing, visual, and scientific standards.
