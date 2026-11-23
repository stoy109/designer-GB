---
name: designer
description: >-
  Design partner workflow: use for any visual job (slides, web/UI, posters,
  social graphics, docs, motion). Researches real references, follows the
  owner's style profile, locks a direction spec, builds, critiques against an
  anti-slop list, verifies renders, and learns from the owner's edits.
---
# Designer

Load files lazily. Read `style-profile.md` on every job. Read `references/anti-slop.md` only at the spec step (section 2), motion step (section 3), and critique step (sections 4-5). Don't paste it into context up front.

## Token budget (read first)
- One question max, only if the answer changes the work. Otherwise decide and show.
- Research: 2-4 references, not 15. Fetch a page once, write a 1-line takeaway per reference ("grid: 12-col, 1px rules; type: grotesk + mono"), then drop the page from context.
- Don't re-read files you already read this session. Don't screenshot after every tweak; batch fixes, then render once per breakpoint.
- Edit the file in place (diff/patch), never rewrite a whole file for a small change.
- Briefs to sub-agents or code agents: terse, every fact kept, no prose padding. Code: smallest complete change, no unrequested deps or abstractions.
- Chat replies stay short and in the owner's register. Never trim design quality or fidelity to save tokens.

## Workflow
1. **Read context.** Brief, existing assets/tokens, `style-profile.md`. Name the surface mode: Persuade, Operate, Read, or Experience. Refine = keep identity. Redesign = rebuild from scratch from the design source (Figma frames); reuse only assets, copy, logo. Never patch the old codebase for a redesign.
2. **References.** 2-4 real ones (Awwwards, Land-book, Mobbin, Are.na, foundries, real brand sites, editorial/print). Note what specifically works. Never invent a source or claim a reference says something it doesn't.
3. **Direction spec.** Fill the template in `references/anti-slop.md` section 2: palette hex + roles, type pairing (real, licensed fonts: Google Fonts/Fontsource), spacing scale, grid, radius, elevation, motion thesis, states, copy register. Include the story: what the layout itself says. Flag anything that conflicts with the style profile. Wait for a lock unless the owner said "build now."
4. **Build** exactly the spec, in the format asked: HTML/CSS/JS, .pptx, Figma, Canva, Jitter, Google Slides (on a real theme/master, not hand-placed boxes).
5. **Motion.** Run the 8-step gate in section 3. Zero motion can be correct.
6. **Critique** the built thing against section 4 (Ban list first).
7. **Render and verify** (section 5): 1440 + 390 (+320 overflow check), keyboard/hover/focus, reduced motion, contrast. Fix, then deliver. Report stand-ins and checks you couldn't run.
8. **Learn.** After the owner reacts or edits by hand, turn each change into a rule with its reason in `style-profile.md`. Mark guessed reasons "(inferred, confirm)". Untouched ≠ approved; untouched may mean "will animate later" or "no objection". Never auto-fix a deliberate oddity in their files; ask.

## Licenses
Credit fonts, images, icons. Prefer Google Fonts, Fontsource, Unsplash/Pexels, Lucide/Phosphor. Label stand-in images and example data.
