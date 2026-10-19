# Multi-Agent LLM Systems Research

A single static page that explains research and art projects on long-running, multi-agent LLM dialogue. It is an interactive explainer, not an agent runtime. No model is called, and no conversation is generated from this repo.

## What it is

`index.html` is the whole project. From the `md` breakpoint (768px) up, a sidebar links six sections and scrolls with the page. Below that width the sidebar is translated off-canvas, and the page has no control that opens it. The sections are an introduction to continuous AI dialogue, a card grid of named projects, an accordion of dialogue challenges, a horizontal bar chart, an AutoGen role diagram, and a short conclusion.

## Problem

Long multi-agent conversations are hard to compare from papers and project sites alone. This page puts a few of those projects, failure modes, and framework ideas on one page.

## Approach

```text
index.html
  ├─ landscape cards (click to open a modal)
  │    infinitebackrooms.com, Infinite Convo, AutoGen,
  │    Jeda.ai, DreamLLM-3D, MAEBE Framework
  ├─ challenge accordion
  │    Context Degradation / 'Lost in Conversation',
  │    Dialogue Diversity Decline, Coordination of Reasoning,
  │    Emergent Harmful Behaviors
  ├─ Chart.js horizontal bar chart
  │    x-axis title "Predictability Score (Illustrative)"
  │    hardcoded 85 (isolated agent) and 30 (ensemble)
  │    in createMoralBrittlenessChart, not a measurement here
  └─ AutoGen diagram
       User Input → AutoGen Conversation
       (Manager Agent, Coder Agent, Critic Agent, Human Input)
       → Task Solution
```

Project blurbs and challenge text are embedded in a `reportData` object in the page. The chart numbers are not in that object. The chart axis is explicitly illustrative.

## Run

The page loads Tailwind and Chart.js from public CDNs, and Inter from Google Fonts, so it needs network access.

```bash
python3 -m http.server 8080
# http://localhost:8080
```

Opening `index.html` directly in a browser also works if those CDN scripts and the font stylesheet are allowed.

## Tech

HTML, CSS, and JavaScript. Tailwind and Chart.js via CDN. Inter via Google Fonts. No package manager, no build, no tests.
