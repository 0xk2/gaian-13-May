# Gaian Danang Policy Deck Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Build a new self-contained HTML deck for Gaian's Da Nang policy presentation with a 5-slide civic-first narrative and built-in presentation/notes modes.

**Architecture:** Keep the existing source deck untouched and create a new standalone HTML file. The new deck will use inline CSS and vanilla JavaScript, with one active slide rendered at a time and a `data-mode` toggle on `<body>` to switch between presentation and speaker-notes layouts.

**Tech Stack:** HTML, CSS, vanilla JavaScript

---

### Task 1: Brand-aligned deck shell

**Files:**
- Create: `2026-05-13/gaian-danang-policy-deck-260513.html`

- [ ] **Step 1: Define Gaian brand tokens in CSS**

Use the palette and typography direction from `brand.md`:

```css
:root {
  --gaian-ink: #163300;
  --gaian-ink-deep: #0a1f00;
  --gaian-accent: #9fe870;
  --gaian-accent-soft: #d8f2c4;
  --gaian-surface: #ffffff;
  --gaian-surface-tint: #f6fdf1;
  --gaian-border-soft: rgba(22, 51, 0, 0.1);
  --gaian-grid-line: rgba(22, 51, 0, 0.06);
}
```

- [ ] **Step 2: Create one reusable slide shell**

Use a shared structure for all slides:

```html
<section class="slide active">
  <div class="slide-shell">
    <div class="main-panel">...</div>
    <aside class="speaker-notes">...</aside>
  </div>
</section>
```

### Task 2: Rewrite the story into 5 slides

**Files:**
- Create: `2026-05-13/gaian-danang-policy-deck-260513.html`

- [ ] **Step 1: Write slide content for the civic-first narrative**

Slides:
1. Gaian starts from Da Nang
2. A real flow of money exists, but outside formal rails
3. Da Nang has an opportunity to lead
4. QR pay crypto to VND, current operating flow, and 21B VND processed
5. Value for Da Nang and the policy ask through Dragon Lab

- [ ] **Step 2: Keep detailed talking points in notes instead of cluttering slides**

Each slide should include concise note bullets for the speaker:

```html
<aside class="speaker-notes">
  <ul class="notes-list">
    <li>Key message...</li>
    <li>Talk track...</li>
  </ul>
</aside>
```

### Task 3: Add presentation and notes modes

**Files:**
- Create: `2026-05-13/gaian-danang-policy-deck-260513.html`

- [ ] **Step 1: Add a mode toggle UI**

```html
<button id="mode-toggle" type="button">Notes</button>
```

- [ ] **Step 2: Toggle the layout with vanilla JS**

```js
const body = document.body;
const modeToggle = document.getElementById("mode-toggle");

function setMode(mode) {
  body.dataset.mode = mode;
  modeToggle.textContent = mode === "notes" ? "Presentation" : "Notes";
}
```

### Task 4: Verify deck behavior

**Files:**
- Create: `2026-05-13/gaian-danang-policy-deck-260513.html`

- [ ] **Step 1: Check slide count and pagination**

Run: `rg -n "class=\"slide|pagination" 2026-05-13/gaian-danang-policy-deck-260513.html`
Expected: 5 slides with consistent `01 / 05` to `05 / 05` pagination.

- [ ] **Step 2: Check mode toggle wiring**

Run: `rg -n "mode-toggle|setMode|data-mode" 2026-05-13/gaian-danang-policy-deck-260513.html`
Expected: CSS and JS both reference the same presentation/notes mode contract.
