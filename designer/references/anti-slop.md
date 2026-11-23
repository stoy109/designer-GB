# Anti-slop design

Generic template. The brief and any locked identity win over these defaults, except lines marked **Ban**. Do not redirect a clear brief toward your own taste.

## 1. Pre-design checklist

Do this before choosing colors or writing markup.

- Read what already exists: product facts, incumbent UI, tokens, and the user's style profile. A missing design doc does not make the work greenfield if a coherent look already lives in the work.
- Name the surface mode from the surface, not the product: **Persuade** (landing, campaign), **Operate** (app, dashboard, settings), **Read** (docs, article), **Experience** (portfolio, showcase). A tool's marketing page is still Persuade.
- Refinement keeps identity, behavior, copy, and everything outside scope. Redesign keeps product truth and function, treats the old look as evidence, and replaces the visual world. Do not split the difference.
- Ask only what will change the work: who must act or what task they complete, what success looks like, what must stay untouched, what would make a polished result feel wrong. Do not ask for CSS values. Do not invent a look inside the questions.
- Research real references. Study structure, type, palette, and motion. Do not copy a reference's code, copy, images, or signature device.
- Facts come from the brief and the user. No invented reviews, quotes, customers, metrics, addresses, or origin stories. Label stand-in photos and example data as stand-ins.
- If the user did not say "build now," propose the direction spec and wait for a lock.

## 2. Direction spec

Write this in the open, then build exactly this. One world, not a mood board.

```
Name:
Mode: Persuade | Operate | Read | Experience
Job of this surface (one sentence):
References used (and what was taken from each):
Anti-references (what we will not repeat):

Palette (hex, each with a role):
  bg / surface / ink / muted / accent / accent-ink / border / focus / danger:
Type:
  display / body / mono (optional): family, weights, fallback
  roles: display, heading, body, label, data
  body measure: 45–75ch (aim ~65ch)
  display max: 6rem; large-heading tracking around -0.02em, floor -0.04em
Spacing: base unit (prefer 4, not 8-only), and the rhythm (tight groups, generous separation; more space above a heading than below it)
Grid / edges: columns, gutter, max width, equal left and right content edges
Radius: scale (cards often 12–16px; pills only on small controls)
Elevation: one system, border or shadow, not both on the same card
Motion thesis: the one authored moment, plus what stays still
States planned: default, hover, focus, active, disabled, loading, empty, error
Copy register: the product's language, not a house voice
Open facts / stand-ins still needed:
```

Do not default to Inter or Geist, purple-to-blue or cyan-on-dark, cream/beige editorial, or a dark page with neon glow, unless the locked brief names them. Light or dark comes from the use scene, not the category. Use the fewest type families that make the hierarchy unmistakable.

On Operate and Read, ambition is precision and familiar patterns. On Persuade and Experience, commit to the world in every atom (nav, buttons, inputs, links), not only the hero.

## 3. Motion rules

Run this sequence in order. Zero animation can be the right result.

1. **Should it animate?** 100+/day and any keyboard-initiated action: no animation, ever. Tens/day: near-imperceptible or none. Occasional (modal, drawer, toast): standard. Rare / first-time: this is where delight lives.
2. **Purpose, one word:** feedback, spatial consistency, state indication, preventing a jarring change, explanation, or delight (delight only at the rare tier). Can't name it? Don't build it.
3. **One authored moment** for the surface, not one identical entrance on every section. A generic fade-and-rise, hover lift, parallax layer, or scroll reveal is not a thesis. Scroll-driven motion only when the scroll relationship itself carries meaning, with a fallback. Carousels are allowed when interruptible. Content must be complete at rest, with script off, and under reduced motion. Nothing stays hidden.
4. **Tool:** cheapest that works (CSS transition, `@starting-style`, CSS animation, WAAPI, then a motion library). Do not add a library for a fade. Prefer `transform` and `opacity`. `clip-path` and accordion height are allowed exceptions. Bounded blur, mask, and shadow may serve the authored moment or a real layering job, not decoration. Animated blur stays under 20px. Never animate width, height, top, left, margin, or padding. Never `transition: all`. Never `scale(0)`; start from `scale(0.9–0.97)` + `opacity: 0`.
5. **Ease and time.** Never `ease-in` on UI. Enter or exit: ease-out. Move on screen: ease-in-out. Hover/color: ease. Loops: linear. If the project has tokens, use them; do not invent a parallel curve. Otherwise:
   - `--ease-out: cubic-bezier(0.23, 1, 0.32, 1)`
   - `--ease-in-out: cubic-bezier(0.77, 0, 0.175, 1)`
   - `--ease-drawer: cubic-bezier(0.32, 0.72, 0, 1)`
   Button press 100–160ms (`scale(0.97)` on `:active`). Tooltips 125–200ms. Dropdowns 150–250ms. UI stays under 300ms. Modals, drawers, sheets, and toasts may go to 500ms. Marketing / the one authored entrance may go longer (about 500–800ms). Exit faster than entrance. No bounce or elastic by reflex; subtle spring bounce (0.1–0.3) only for interruptible gestures or a playful world the brief named.
6. **Choreography.** One entrance per container: if the panel moves in, its content is already there. Never stagger high-frequency or keyboard UI. Uniform stagger is forbidden. Product stagger 30–80ms, total under ~300ms; long lists stagger only the first handful. Motion never blocks interaction. Exits are simultaneous, shorter, and simpler, and they leave the way they entered. Popovers scale from the trigger; modals stay centered.
7. **Hover and interruption.** Gate hover with `@media (hover: hover) and (pointer: fine)`. Do not move the pointer target or a neighbor; move a child of the hovered element. Transitions or springs, not keyframes, for anything a user can fire twice in a second. Loops longer than 5s need a pause control and must stop when offscreen.
8. **Reduced motion.** Ship it with the animation. Fewer and gentler, not zero: keep opacity, color, and meaningful state changes; drop spatial movement. Collapse choreography (no delays, group appears together).

## 4. Anti-slop critique checklist

Walk the built work, not the intention. A clean linter is a floor, not a pass.

**Ban**

- Decorative eyebrow, kicker, or pill above a heading (the heading carries its own weight)
- Nested cards; same-size icon-tile + heading + text cards as the page structure
- Invented facts, reviews, customers, or metrics; unlabeled stand-in or example data
- Gradient text; glass and glow used as decoration; colored side-stripe >1px on a card
- Emoji or Unicode glyphs as the icon system; a drawn fake of a real logo
- Copy residue (lorem, `{{tokens}}`, chatbot leftovers) and slop diction (seamless, unlock, unleash, cutting-edge, world-class, next-generation, and stock lines of that family)
- The page calling itself honest, thoughtful, or intentional

**Refuse unless the locked brief earns them**

- Inter or Geist as the only voice; italic serif display as a default editorial shortcut
- Purple-to-blue / cyan-on-dark / cream-beige reached for by reflex
- Hero-metric strip (big number, small label, supporting stats)
- Numbered section labels (01 / 02 / 03) when sequence is not the point
- Hard offset shadow, decorative grid or stripe background, radial spotlight halo
- System display faces (Impact, Arial Black) as the display voice
- A 1px hairline plus a wide soft shadow on the same card (pick one)
- Fade-in on every section; everything asking for attention at once

**Also check**

- First screen states what is offered and what to do next
- Hierarchy readable in a squint test: one lead, then support
- Body measure, wrapping (`text-wrap: pretty` / `balance`), no overflow, no skipped heading levels
- Contrast: body ≥4.5:1, large text and controls ≥3:1; no gray text on a colored surface (tint it)
- One type scale, one button family, one radius scale, one elevation system
- Copy in the product's language; controls name the action; errors name the problem and the recovery
- Browser chrome is designed: focus ring, selection, caret, scrollbar, underline offset, tabular nums
- Worst-case data: long names, empty states, huge counts, missing images

## 5. Render and verify

Look at the rendered result at the sizes it ships. Batch what one look shows, then look again. Do not screenshot after every tweak. A single still is not a motion review.

- Desktop and a phone width at minimum (1440 and 390 are a good pair). Also an intermediate width if the layout changes there. Check 320 for overflow.
- Walk the real path with pointer and keyboard. Confirm hover, focus, active, disabled, loading, empty, and error.
- Confirm reduced-motion and no-JS: the page stays complete and nothing stays hidden.
- Confirm tap targets on phone (about 44px, with space around them) and that hover motion is not required to use the control.
- Theme the default browser surfaces. Check text on images and overlays, not only on flat color.
- Fix overflow, overlap, broken animation, contrast, and missing states before calling the work done. Report stand-ins and any check you could not run.

If the user later corrects the work, turn each correction into a class-level rule with the user's reason (mark a guessed reason as inferred and confirm it). Write it into the style profile or DESIGN.md only after approval. A mechanical check beats a vague sentence. Do not add rules the user did not express.

## Credits and licenses

This template paraphrases and condenses rules from:

- [Leonxlnx/taste-skill](https://github.com/Leonxlnx/taste-skill) (tasteskill 2.5.1), MIT License, Copyright (c) 2026 Leonxlnx
- [Impeccable](https://impeccable.style) / [pbakaus/impeccable](https://github.com/pbakaus/impeccable), Apache License 2.0, Copyright 2025 Paul Bakaus. Impeccable started from Anthropic's frontend-design skill. Its iOS and Android references are distilled from ehmo/platform-design-skills (MIT).
- [emilkowalski/skills](https://github.com/emilkowalski/skills), MIT License, Copyright (c) 2026 Emil Kowalski

The MIT copyright notices above must be kept when this file is copied. The Apache 2.0 portions are used under that license; see the Impeccable `LICENSE` and `NOTICE.md` for terms. This is a short derived workflow, not a substitute for those projects or their scripts.
