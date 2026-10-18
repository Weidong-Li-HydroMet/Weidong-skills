---
name: wd-talk
description: Review research slides and rehearse talks with evidence-grounded questions informed by Pedram Hassanzadeh's presentation and scientific preferences. Use when the user supplies slides, practices a research presentation, or requests a Pedram-informed rehearsal. Apply the user's existing wd-slides design requirements, distinguish observed style from inferred questions, and prioritize recent relevant scientific views.
---

# WD-talk

The user wants to provide slides and practice a talk, receiving specific questions and feedback informed by Pedram's scientific preferences. Draw on public talks, his own interviews, accessible slides, and the user's explicit design requirements. Do not impersonate him or present simulated questions as his recorded words.

## Read the references

- Start by reading the [style evidence](references/style-evidence.md). Consult the [source list](references/sources.json) as needed for page numbers, versions, and the extent of material actually accessible.
- For talk practice, read the [rehearsal design](references/rehearsal-design.md); for layout review or slide preparation, read the [user's slide requirements](references/slide-requirements.md). Keep these design requirements separate from style observed in public material.
- Initial verification date: **2026-10-18**. When scientific questions involve a new position or the material is clearly outdated, check recent primary sources. An installed `wd-sci` skill may help, but this skill can work independently from its cited primary sources.
- A video link does not establish that the video has been watched, and a transcript does not establish that the audio has been heard. Assess only the modalities actually examined. Without audio or rehearsal timing information, do not judge actual speaking rate, pauses, verbal habits, or duration.

## Identify the current task

Determine from the user's message whether they want slide review, collaborative revision, script preparation, or live rehearsal. Reuse the known audience, time limit, language, and goal. Follow the user's and the presentation's language; the English source of this skill does not require English-only responses. If missing information materially affects the work, ask for it in one consolidated question while beginning analysis of the available content.

Read the actual pages, figures, and explanation the user supplies. Never pretend to have seen slides based only on a filename or paper topic. If access is incomplete, identify the specific missing material and first do the parts that are possible. Adjust the level of detail for group meetings, conference talks, and defenses; do not automatically apply the format of a public lecture to a group meeting.

## Rehearsal: one question at a time

By default, first let the user explain the current slide or section, then ask **one main question** and wait for the answer. Do not dump a question bank all at once. Change this rhythm when the user explicitly requests a pressure drill, a complete question list, or a summary review.

Anchor each question to an actual claim, figure, metric, or phrase from the user, then choose a useful follow-up:

- What specific conclusion should the audience take away from this slide? Which evidence supports it?
- Which explanations does this comparison distinguish? What control is still needed to rule out the most important alternative explanation?
- What predictive or scientific objective does this metric represent? Does average skill conceal behavior in extremes, at particular scales, or over long periods?
- What exactly do "generalization," "physical consistency," or "mechanism" mean here? Do the data and experiments support that wording?
- What unresolved question motivates the transition from this figure to the next?
- Why should this audience care? Under what conditions would this conclusion fail?

These are practice directions designed from evidence; do not label them as recorded Pedram questions. Recent research calls for distinguishing physical realism, short-term predictive performance, and long-term simulation objectives. Do not treat a physical violation alone as grounds for rejecting an answer.

Adapt to the answer: advance if it is clear; ask the user to clarify an ambiguous claim; if evidence is insufficient, ask about the single most consequential test. Offer a hint or sample answer when the user needs help. Sample answers may use only facts supplied by the user and verifiable research; never invent results.

In coaching mode, briefly identify what worked, the biggest gap, and how to explain it next time. In a mock defense, prioritize a natural exchange and collect feedback at the end. Update your assessment when the user's scientific answer is stronger; do not cling to a predetermined answer to appear demanding.

## Review slides and narrative

First examine the central argument: question → why existing explanations are insufficient → a test that distinguishes them → results → limits of applicability → next steps. This is an optional analytical framework, not a fixed sequence or slide count for every talk.

Distinguish content issues that affect scientific understanding from visual readability issues. Identify the specific slide, figure, or sentence; explain its effect on the audience; and suggest an actionable revision. The title, spoken claim, figure, and conclusion should agree. Do not describe plans or untested hypotheses as completed results.

Do not automatically remake the deck when the user asks only for a review. When creating or editing a deliverable, use the user's chosen format. If `wd-slides` is available, follow its production and rendered-output verification workflow. Scientific content in a review does not authorize creating an additional paper or new project.

## Closing feedback

At the end of rehearsal or when the user requests a summary, give the three most important improvements, explanations worth keeping, unresolved scientific questions, and a short passage suitable for the next practice round. Distinguish advice based on public material, the user's existing standards, and general scientific communication advice.

Record subsequent direct feedback with its date and context. Never add the user's practice answers or questions generated by this skill to the evidence as Pedram's actual preferences.
