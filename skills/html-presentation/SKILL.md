---
name: html-presentation
description: Transform a markdown file or document into a single self-contained HTML presentation for live screen delivery. Use when the user needs a presentation deck built from existing written content, for an executive overview, team briefing, or detailed walkthrough delivered on a screen or projector.
---

This skill runs in two phases. Do not skip Phase 1 or combine the phases.

## Phase 1: Intent and outline

Read the source file in full. Then ask the user two questions before doing anything else:

1. **Scope**, which best fits the intended use?
   - Executive overview (8-10 slides, high-level, decision-focused)
   - Team or partner briefing (12-16 slides, moderate depth)
   - Detailed walkthrough (18+ slides, comprehensive)
   - Let the content decide

2. **Density**, how much content per slide?
   - Visual-first (diagrams, big numbers, minimal prose)
   - Balanced (mix of visual and supporting text)
   - Text-heavy (bullet points, more content per slide)

After receiving the answers, produce a slide outline in this format:

```
Proposed structure: N slides

Slide 1, [Working title]: [one-sentence description of content]
Slide 2, [Working title]: [one-sentence description of content]
...
```

Stop here. Wait for the user to approve the outline or request adjustments. Do not begin Phase 2 until the user explicitly says to proceed.

## Phase 2: Full generation

Build the complete HTML presentation from the approved outline. Use the source content faithfully, don't invent or pad. Apply all rules below.

## Output

- Single self-contained `.html` file, no external dependencies except Google Fonts
- Save in the same directory as the source file, same filename with `.html` extension
- Screen-only: full viewport, keyboard navigation (arrows + space), click to advance, dot indicators

## Brand

Default accent is `#2563eb` (a clean blue). Swap it for your own brand color, that's the one thing here worth customizing per user. Everything else below applies as-is.

- **Accent color**: `#2563eb` by default, used for section labels, key numbers, borders, and highlights, never as a dominant background or fill
- **Typography**: Barlow Condensed for display, Barlow for body. Bold, precise, confident. No italic, anywhere.
- Content slides: white background, near-black text (`#111111` range)
- Cover slide only: a dark background is acceptable

## Design

- This is a live presentation, viewed full screen or projected. All text that communicates information must be dark enough to read at a glance (`#444` or darker on white). This includes body copy, supporting descriptions, subtitles, callouts, and stat labels. There is no muted or secondary text tier. Light gray is for decorative elements only (diagram scaffolding, background marks).
- Section labels and eyebrows: dark uppercase, or accent color only at sizes where it's clearly legible. Never small + uppercase + accent-color together, it becomes unreadable.
- One idea per slide. Decide slide count and structure from the source content.
- Actively reach for visual formats. Any content that describes a flow, comparison, process, hierarchy, or quantity should be a diagram, chart, timeline, or SVG, not a text layout. Text cards are a fallback, not a default. Make the creative decisions.
- Subtle entrance animations on slide load.
- Cover slide sets the tone: make it striking.

## Optional confidentiality or branding footer

If the user's context requires a fixed footer line (confidentiality notice, company name, etc.), place it as a thin, single-line bar pinned to the very bottom of the viewport, positioned below the nav dot indicators so it never overlaps them. Keep it visually silent: very small text (~10px), no background fill, low-opacity dark gray on white slides, switching to low-opacity white on dark slides so it stays legible without competing with slide content. Toggle the color via a body-level class driven by the slide-navigation JS, not per-slide overrides, so it stays correct automatically as slides change. Ask the user for their exact footer text and confirm whether it's needed at all, don't assume one is required.

## Quality bar

Should look designed, not generated. Someone seeing it should think a designer built this deck, not a template.
