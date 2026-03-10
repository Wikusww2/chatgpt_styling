---
name: uncodixfy
description: A design philosophy, formal reasoning framework, and anti-pattern system for AI-generated output. Combines rigorous logical problem-solving with actionable design systems for color, type, spacing, motion, and composition — preventing generic defaults without dictating a single house style.
---

# Uncodixify

A design philosophy for AI that generates visual output.

The problem is convergence. Every AI tends toward the same rounded cards, the same muted dark palettes, the same dashboard skeletons, the same hollow "premium" polish. This document exists to break that pattern — not by replacing it with another fixed style, but by teaching *how to think about design decisions*.

**IMPORTENT TO READ AND FOLLOW ALWAYS**

Do not select a palette from the reference tables by default. Derive the color direction from the specific brand, audience, and mood of the task. The reference palettes exist only as fallbacks when no contextual direction exists.

**Use this as a filter, not a template.**

---

## 0. Formal Logic & Reasoning Framework

Design does not exist in a vacuum. Every visual decision ultimately serves a goal, operates within constraints, and must hold up to scrutiny. Before any creative work begins — before color, type, layout, or motion — apply the same formal reasoning you would to any engineering or analytical problem.

This section is domain-agnostic. It applies equally to UI design, data visualization, document layout, slide decks, code architecture, mathematical proofs, and plain-language problem solving.

### The Reasoning Protocol

For every prompt, every task, every request — before producing output:

```
1. IDENTIFY THE GOAL
   What is actually being asked?
   Not what it sounds like on the surface — what is the real objective?
   What would "success" look like? Define it precisely.

2. GATHER FACTS & CONTEXT
   What is known? What exists already?
   What is the environment (brand, audience, medium, platform, constraints)?
   What prior work, data, specifications, or standards apply?
   Read the room — context shapes every decision.

3. SURFACE CONSTRAINTS
   What are the hard limits? (time, budget, platform, accessibility, performance)
   What are the soft limits? (brand tone, user expectations, cultural norms)
   What cannot change? What has flexibility?

4. STATE ASSUMPTIONS EXPLICITLY
   What are you assuming that has not been confirmed?
   Which assumptions are safe? Which are risky?
   Flag uncertain assumptions before they become invisible foundations.

5. MAP DEPENDENCIES
   What depends on what?
   What must be resolved first before downstream decisions make sense?
   Where are the bottlenecks, blockers, or circular dependencies?

6. IDENTIFY EDGE CASES
   What happens at the extremes? Empty data? Massive data? Long strings?
   Edge cases in design: What if there are 0 items? 1 item? 10,000 items?
   Edge cases in logic: What if an input is null, negative, or out of range?
   What if the user does something unexpected?

7. DECOMPOSE INTO VALID STEPS
   Break the task into discrete, verifiable sub-tasks.
   Each step should have a clear input, a clear output, and a clear success criterion.
   Steps should follow logically — no leaps of faith.

8. EXECUTE WITH EVIDENCE
   Every conclusion must trace back to a fact, a constraint, or a stated assumption.
   "It looks right" is not evidence. "It satisfies constraint X and serves goal Y" is.
   Show the reasoning, not just the result.

9. VERIFY & CROSS-CHECK
   Does the output actually answer the original question?
   Are all constraints satisfied?
   Are units, definitions, and terminology consistent?
   Does the result make sense in the real-world context?
   Would a domain expert find this answer credible?

10. RESOLVE AMBIGUITY
    If the request is ambiguous, resolve it from context first.
    If context is insufficient, state the ambiguity and the interpretation chosen.
    Never silently guess — either resolve or surface.
```

### How This Applies to Design

| Reasoning Step | Design Translation |
|---------------|-------------------|
| Identify the goal | What is this interface for? What action should the user take? |
| Gather facts | What brand exists? What platform? What content? |
| Surface constraints | Screen size, accessibility requirements, performance budgets |
| State assumptions | "I'm assuming this is a desktop-first audience" — say it |
| Map dependencies | Navigation structure must be decided before page layout |
| Identify edge cases | What does this page look like with no data? With 500 items? |
| Decompose into steps | Information architecture → layout → typography → color → interaction |
| Execute with evidence | "I chose this layout because the data is tabular, not comparative" |
| Verify | Does this actually solve the user's problem, or just look good? |
| Resolve ambiguity | "Landing page" could mean marketing or could mean login — clarify |

### How This Applies Beyond Design

This framework is universal. Apply it to:

- **Code architecture** — Identify the goal (what problem does this function solve?), surface constraints (performance, memory, API contracts), identify edge cases (null inputs, race conditions), verify (does it handle all specified inputs correctly?)
- **Data analysis** — Gather facts (source, freshness, biases), state assumptions ("I'm treating missing values as zero"), cross-check (do the numbers add up? are the units consistent?)
- **Mathematical problems** — Define the domain, state givens, identify what's being solved for, decompose into solvable sub-problems, verify the solution satisfies all constraints
- **Writing & communication** — Identify the audience and purpose, gather relevant context, structure the argument logically, verify the conclusion follows from the premises
- **Debugging** — Identify what's actually wrong (not just the symptom), gather facts (logs, reproduction steps, environment), form hypotheses, test against evidence, verify the fix doesn't break adjacent behavior

### Logic Failures to Watch For

| Failure | Description | How to Catch It |
|---------|------------|----------------|
| **Confirmation bias** | Seeking evidence that supports your first instinct, ignoring contradictions | Actively look for reasons your approach could be wrong |
| **Premature commitment** | Locking into a solution before fully understanding the problem | Re-read the original request after drafting your plan |
| **Scope drift** | Answering a different question than the one asked | State the question you're answering and verify it matches |
| **Assumed context** | Filling in gaps with your own experience instead of the user's reality | Flag every assumption explicitly |
| **False precision** | Giving exact-sounding answers when the inputs are approximate | Match the precision of your output to the precision of your inputs |
| **Missing negation** | Failing to consider what should NOT happen | For every "it should do X," also ask "what should it NOT do?" |
| **Untested boundaries** | Verifying the happy path but not the edges | Always test with 0, 1, many, and invalid inputs |

---

## I. The Hierarchy of Design Decisions

Every design decision should pass through these gates, in order:

```
1. PURPOSE    →  What is this thing for? Who uses it? What should they feel?
2. STRUCTURE  →  What information architecture serves that purpose?
3. HIERARCHY  →  What do people need to see first, second, never?
4. TONE       →  What personality fits? Clinical? Warm? Bold? Invisible?
5. SYSTEM     →  What visual language (color, type, spacing) supports all of the above?
6. POLISH     →  What refinements make it feel finished without feeling decorated?
```

If you jump to step 5 or 6 before resolving 1–4, you will produce pretty garbage. This is the central failure mode of AI-generated design: **decoration before intention**.

---

## II. The Anti-Pattern Index

These are strong signals of unconsidered, default AI output. Not automatically banned — but always suspicious.

### Structural Defaults

| Pattern | Why It's Suspicious |
|---------|-------------------|
| Sidebar + content + right rail | Assumed without questioning whether the data model needs three columns |
| Hero → features grid → testimonials → CTA | The "landing page" skeleton applied to everything |
| KPI cards as the opening move | Often decoration disguised as data |
| Identical card grids | Treats all content as equally important |
| Centered single-column marketing blocks for operational content | Wrong density for the task |
| Dashboard layout for non-dashboard content | Cargo-culting structure |

### Visual Defaults

| Pattern | Why It's Suspicious |
|---------|-------------------|
| Glassmorphism everywhere | Used as a substitute for actual spatial hierarchy |
| Oversized border radius on everything | Makes unrelated elements feel identically soft |
| Blue-black gradients | The "modern" shortcut that signals nothing |
| Decorative glows and hazes | Depth that the layout didn't earn |
| Muted gray-blue body text | Sacrifices readability for "aesthetics" |
| Pill shapes on everything | Removes visual differentiation between element types |
| Dramatic shadows on flat content | Fake dimensionality |
| Gradient borders | Almost never functionally justified |

### Copy Defaults

| Pattern | Why It's Suspicious |
|---------|-------------------|
| "Operational clarity" / "command center" / "live pulse" headings | Startup theater |
| Tiny uppercase eyebrow labels everywhere | Decorative hierarchy that adds noise |
| Explanatory notes under every section | If the UI needs explaining, the UI is wrong |
| Abstract motivational product copy | Says nothing, takes space |
| Heading stacks (eyebrow + title + subtitle + description) | Four levels where one would do |

---

## III. The Freedom Principle

You are not restricted to minimalism. You are not restricted to anything.

The correct visual language depends entirely on the brief:

| Context | Appropriate Direction |
|---------|---------------------|
| Medical records system | Calm, clinical, high-legibility, institutional |
| Music production app | Dark, dense, tactile, performance-oriented |
| Children's education platform | Warm, playful, colorful, forgiving |
| Legal document system | Sober, typographic, quiet, trustworthy |
| Creative portfolio | Expressive, editorial, art-directed, memorable |
| Developer tool | Compact, monospaced-friendly, information-dense |
| Luxury product page | Restrained, cinematic, high-contrast, photographic |
| Data journalism | Editorial, narrative, visualization-forward |

**Allowed creative tools** (when earned by the brief):

- Asymmetric layouts and broken grids
- Strong editorial hierarchy with dramatic scale contrast
- Image-led and photographic composition
- Expressive or display typography
- Dense information systems with tight spacing
- Brutal simplicity and aggressive whitespace
- Cinematic pacing across sections
- Deliberate ornament and pattern
- Atmospheric color and light
- Unconventional navigation and interaction

**Never allowed** regardless of brief:

- Decoration without communicative purpose
- Style-stacking (mixing trends hoping something sticks)
- Novelty that damages usability
- Complexity that serves the designer's ego, not the user's task

---

## IV. Color System

### Philosophy

Color is not decoration. It is a functional layer that creates hierarchy, conveys tone, signals state, and establishes identity.

**Decision process:**

```
1. Does the project have existing brand colors?  →  Use them. Extend, don't replace.
2. No brand exists?  →  What tone does the product need?
3. Choose a family:
   - Warm    (amber, terracotta, sand)     →  approachable, human, editorial
   - Cool    (slate, steel, ice)           →  clinical, technical, professional
   - Deep    (navy, wine, forest)          →  serious, premium, institutional
   - Vivid   (electric, neon, saturated)   →  energetic, creative, youthful
   - Neutral (gray, stone, chalk)          →  invisible, utilitarian, content-first
4. Build a palette: 1 background + 1 surface + 1 primary + 1 accent + 1 text
5. Test: can you remove any color and still have a working hierarchy?
```

### Rules

- **Contrast first.** WCAG AA minimum. No exceptions for aesthetics.
- **Economy.** Let 1–2 colors do the heavy lifting. A 6-color palette is almost always a failure of hierarchy.
- **Accent means rare.** If your accent color appears more than 3–4 times on a screen, it's not an accent.
- **Dark ≠ premium.** Light ≠ boring. The choice is tonal, not aspirational.
- **Same project, different outputs → same palette family.** Different projects → *should* look different.

### Reference Palettes

Use these as departure points. Modify freely. Never copy wholesale across projects.

#### Dark Foundations

| Name | Background | Surface | Primary | Accent | Text | Character |
|------|-----------|---------|---------|--------|------|-----------|
| Midnight Canvas | `#0a0e27` | `#151b3d` | `#6c8eff` | `#f472b6` | `#e2e8f0` | Deep, contemplative, creative |
| Obsidian Depth | `#0f0f0f` | `#1a1a1a` | `#00d4aa` | `#ff6b9d` | `#f5f5f5` | High-contrast, modern, sharp |
| Carbon Elegance | `#121212` | `#1e1e1e` | `#bb86fc` | `#cf6679` | `#e1e1e1` | Material-influenced, balanced |
| Void Space | `#0d1117` | `#161b22` | `#58a6ff` | `#f78166` | `#c9d1d9` | Developer-native, GitHub-adjacent |
| Twilight Mist | `#1a1625` | `#2d2438` | `#9d7cd8` | `#ff9e64` | `#dcd7e8` | Atmospheric, soft, contemplative |
| Onyx Matrix | `#0e0e10` | `#1c1c21` | `#00ff9f` | `#ff0080` | `#f0f0f0` | Cyberpunk, high-energy, technical |

#### Light Foundations

| Name | Background | Surface | Primary | Accent | Text | Character |
|------|-----------|---------|---------|--------|------|-----------|
| Cloud Canvas | `#fafafa` | `#ffffff` | `#2563eb` | `#dc2626` | `#0f172a` | Clean, professional, versatile |
| Linen Soft | `#fef7f0` | `#fffbf5` | `#d97706` | `#0284c7` | `#292524` | Warm, editorial, approachable |
| Ivory Studio | `#f5f5f4` | `#fafaf9` | `#0891b2` | `#f59e0b` | `#1c1917` | Natural, calm, creative |
| Arctic Breeze | `#f0f9ff` | `#f8fafc` | `#0284c7` | `#f43f5e` | `#0c4a6e` | Cool, crisp, airy |
| Sand Warm | `#faf8f5` | `#ffffff` | `#b45309` | `#059669` | `#451a03` | Earthy, organic, grounded |
| Frost Bright | `#f1f5f9` | `#f8fafc` | `#0f766e` | `#e11d48` | `#0f172a` | Fresh, clinical, trustworthy |

---

## V. Typography System

### Philosophy

Type is the single most impactful design tool. A design with great typography and no color will outperform a design with great color and bad typography every time.

### Decision Framework

```
What is the content density?
├── High (dashboards, tools, data)
│   → System fonts or geometric sans (Inter, SF Pro, Geist)
│   → Smaller base size (13–14px), tighter line-height (1.4)
│   → Weight contrast for hierarchy, not size contrast
│
├── Medium (apps, documents, marketing)
│   → Humanist sans (Inter, Plus Jakarta Sans, Source Sans 3)
│   → Standard base (15–16px), comfortable line-height (1.5–1.6)
│   → Mix of size and weight for hierarchy
│
├── Low (editorial, landing, portfolio)
│   → Serif or display (Fraunces, Playfair Display, DM Serif)
│   → Larger base (17–20px), generous line-height (1.6–1.8)
│   → Dramatic scale contrast between heading and body
│
└── Specialized
    ├── Code-heavy  → Monospace (JetBrains Mono, Fira Code, Berkeley Mono)
    ├── Legal/Gov   → Neutral serif (Charter, Georgia, Noto Serif)
    └── Playful     → Rounded sans (Nunito, Quicksand, Baloo 2)
```

### Pairing Strategies

Strong pairings share a structural relationship but differ in voice:

| Heading | Body | Relationship | Mood |
|---------|------|-------------|------|
| Fraunces | Inter | Serif display + geometric sans | Editorial + functional |
| Space Grotesk | DM Sans | Geometric + humanist | Technical + approachable |
| Playfair Display | Source Sans 3 | High-contrast serif + neutral sans | Elegant + readable |
| Outfit | Inter | Geometric display + geometric body | Modern + clean |
| Sora | Plus Jakarta Sans | Geometric + soft humanist | Futuristic + friendly |
| DM Serif Display | Geist | Transitional serif + system-like sans | Classic + contemporary |
| Cabinet Grotesk | Satoshi | Grotesque + neo-grotesque | Bold + refined |

### Type Scale

Use a consistent ratio. Pick one per project:

| Ratio | Scale (base 16px) | Character |
|-------|-------------------|-----------|
| 1.200 (Minor Third) | 16 → 19 → 23 → 28 → 33 | Compact, functional |
| 1.250 (Major Third) | 16 → 20 → 25 → 31 → 39 | Balanced, versatile |
| 1.333 (Perfect Fourth) | 16 → 21 → 28 → 38 → 50 | Editorial, dramatic |
| 1.500 (Perfect Fifth) | 16 → 24 → 36 → 54 → 81 | High-impact, display |

### Rules

- **One typeface is enough.** Two is a pairing. Three is almost always a mess.
- **Weight does more work than size.** Use 400/500 for body, 600/700 for emphasis, 800/900 for display impact.
- **Letter-spacing is not decoration.** Tighten headings slightly (-0.01em to -0.03em). Leave body alone. Only widen uppercase labels if they're short.
- **Line length matters.** 55–75 characters per line for body text. Anything wider kills readability.
- **Don't fake hierarchy.** If you need uppercase + letter-spacing + small size + muted color to make a label feel like a label, the information architecture is broken.

---

## VI. Spacing & Density System

### Philosophy

Spacing is not padding. It is rhythm. It tells the eye what belongs together, what is separate, and how important each group is.

### Base Unit

Pick a base unit and derive everything from it:

| Base | Character | Good For |
|------|-----------|----------|
| 4px | Tight, technical | Dashboards, data tables, dev tools |
| 6px | Compact, functional | Dense apps, admin panels |
| 8px | Balanced, versatile | Most applications, websites |
| 12px | Generous, editorial | Marketing, editorial, portfolios |

Scale using the base: `base × 1, 2, 3, 4, 6, 8, 12, 16, 24`

### Proximity Principle

```
Related items     →  1–2 base units apart
Sibling groups    →  3–4 base units apart
Distinct sections →  6–8 base units apart
Major landmarks   →  12–24 base units apart
```

### Density Guidance

| Content Type | Density | Spacing Pattern |
|-------------|---------|----------------|
| Data tables, code | Very tight | 4–8px cells, minimal padding |
| Tool interfaces, forms | Tight | 8–12px component padding |
| Standard app UI | Medium | 16–24px section spacing |
| Marketing pages | Generous | 32–64px section spacing |
| Editorial, portfolio | Very generous | 64–120px section spacing |

### Rules

- **Consistent internal padding.** A card with 16px padding on top and 24px on bottom looks broken.
- **Whitespace is structural.** Don't pad everything equally to "look clean" — vary spacing to create hierarchy.
- **Overpadding is a tell.** Excessive padding used to simulate elegance is a common AI default. Earn your whitespace.
- **Touch targets: 44px minimum.** On interactive elements, density cannot compromise usability.

---

## VII. Layout & Composition

### Philosophy

Layout is the skeleton. If the skeleton is wrong, no amount of visual polish will save it.

### Layout Selection

Don't default. Diagnose:

| Question | If Yes → |
|----------|----------|
| Is there a primary content stream? | Single column with optional sidebar |
| Does the user compare items? | Grid or multi-column |
| Is there deep navigation? | Sidebar or collapsible nav |
| Is the data tabular? | Table (not cards pretending to be a table) |
| Is it narrative/sequential? | Single column, vertical scroll, editorial pacing |
| Is it a workspace with many tools? | Panels, possibly resizable |
| Is it a form? | Single column, grouped sections, clear progression |
| Is it a landing page? | Full-width sections, strong typographic hierarchy |

### Composition Principles

- **Alignment creates trust.** Align elements to a grid. Arbitrary positioning feels unfinished.
- **Repetition creates rhythm.** Repeat structural patterns (spacing, sizing) to build coherence.
- **Contrast creates hierarchy.** One thing should be biggest. One thing should be boldest. If everything shouts, nothing is heard.
- **Proximity creates meaning.** Things that are close together are perceived as related. Use this deliberately.
- **Asymmetry is allowed.** But it must be *balanced* asymmetry — visual weight distributed with intent, not randomness.

### Grid Guidance

| Layout Type | Columns | Gutter | Margin | Notes |
|-------------|---------|--------|--------|-------|
| Mobile | 4 | 16px | 16–20px | Stack by default, selective side-by-side |
| Tablet | 8 | 20px | 24–32px | Introduce columns selectively |
| Desktop | 12 | 24px | 32–80px | Full grid, responsive breakpoints |
| Wide content | 16 | 24px | auto (max-width) | Cap content width at 1200–1440px |

---

## VIII. Motion & Interaction

### Philosophy

Motion is communication. It tells the user what happened, what's related, and where to look. If it doesn't serve one of those purposes, cut it.

### Timing Principles

| Action Type | Duration | Easing | Example |
|------------|----------|--------|---------|
| Micro-interaction | 100–150ms | `ease-out` | Button press, toggle switch |
| State change | 150–250ms | `ease-in-out` | Panel open, tab switch |
| Content transition | 250–400ms | `ease-out` or custom cubic-bezier | Page transition, modal appear |
| Emphasis/attention | 400–700ms | `ease-in-out` | Notification entrance, success animation |
| Ambient/decorative | 1000ms+ | `linear` or gentle `ease` | Background gradient shift, idle state |

### Useful Easings

```css
/* Snappy, responsive — good for UI interactions */
--ease-out-expo: cubic-bezier(0.16, 1, 0.3, 1);

/* Smooth, natural — good for content transitions */
--ease-out-quart: cubic-bezier(0.25, 1, 0.5, 1);

/* Energetic entrance — good for elements appearing */
--ease-out-back: cubic-bezier(0.34, 1.56, 0.64, 1);

/* Gentle, organic — good for hover states */
--ease-in-out-quad: cubic-bezier(0.45, 0, 0.55, 1);

/* Spring-like — good for playful interactions */
--spring: cubic-bezier(0.175, 0.885, 0.32, 1.275);
```

### Interaction States

Every interactive element needs these states, no exceptions:

| State | Visual Treatment |
|-------|-----------------|
| Default | Base appearance |
| Hover | Subtle shift — color, elevation, or scale (pick one, not all) |
| Focus | Visible outline or ring — accessibility requirement, not optional |
| Active/Pressed | Slight depression — darker shade, inward shadow, or scale(0.98) |
| Disabled | Reduced opacity (0.4–0.5) + `cursor: not-allowed` |
| Loading | Skeleton, spinner, or pulsing placeholder — never frozen UI |

### Rules

- **Hover ≠ circus.** One property change on hover. Not scale + shadow + color + glow simultaneously.
- **Respect `prefers-reduced-motion`.** Always. Provide a reduced or no-motion fallback.
- **Entrance animations once.** Don't re-animate content that the user has already seen.
- **Loading states are mandatory.** A blank screen while fetching data is a bug, not a design choice.

---

## IX. Iconography & Imagery

### Icons

- **Pick one icon set and stick with it.** Mixing Lucide, Heroicons, and Material icons in one project is visual noise.
- **Consistent size.** Decide on 16px, 20px, or 24px and use it everywhere. Don't mix sizes within the same context.
- **Consistent stroke weight.** Match the icon stroke weight to your body font weight.
- **Icons supplement, not replace.** An icon next to a label is clearer than an icon alone (except for universally understood icons: ✕, ☰, ←, 🔍).

### Imagery

- **No placeholder images in production.** If you need an image, use a real one or generate one. Gray boxes are never acceptable.
- **Aspect ratio consistency.** Pick ratios per context (16:9 for heroes, 1:1 for avatars, 4:3 for cards) and maintain them.
- **Image treatment should match tone.** Desaturated photos for clinical. Vivid for energetic. Duotone for editorial.

---

## X. Accessibility Baseline

This is not optional. It is not a polish step. It is a structural requirement.

| Requirement | Standard |
|------------|----------|
| Color contrast (body text) | ≥ 4.5:1 (WCAG AA) |
| Color contrast (large text/headings) | ≥ 3:1 (WCAG AA) |
| Color contrast (interactive elements) | ≥ 3:1 against background |
| Focus indicators | Visible on every interactive element |
| Touch targets | ≥ 44×44px |
| Color not sole indicator | Never use color alone to convey meaning |
| Text scaling | Layout must not break at 200% zoom |
| Semantic HTML | Headings in order, landmarks present, lists are lists |
| Alt text | Every informational image has descriptive alt text |
| Keyboard navigation | Every action reachable without a mouse |

---

## XI. Responsive Thinking

### Philosophy

Responsive design is not "make it narrower." It is rethinking information priority at each breakpoint.

### Breakpoint Strategy

| Name | Width | Approach |
|------|-------|----------|
| Mobile | < 640px | Single column, stacked, essential content only |
| Tablet | 640–1024px | Selective multi-column, collapsible navigation |
| Desktop | 1024–1440px | Full layout, all features visible |
| Wide | > 1440px | Capped content width, increased margins |

### What Changes at Each Break

- **Navigation:** Hamburger → sidebar → top bar (or vice versa, depending on information architecture)
- **Grid:** 1 col → 2 col → 3–4 col (not automatic — only when content density warrants it)
- **Typography:** Scale down heading sizes, maintain body size
- **Spacing:** Reduce section spacing, maintain component internal spacing
- **Features:** Consider hiding secondary features on mobile, not just shrinking them

---

## XII. The Quality Checklist

Before shipping, run through this:

### Intention
- [ ] Every visual decision traces back to a purpose
- [ ] The layout was chosen for the content, not copied from a template
- [ ] The color palette fits the tone, not just "looks nice"
- [ ] Typography was selected, not defaulted

### Craft
- [ ] Spacing is consistent and rhythmic
- [ ] Alignment is deliberate — elements sit on a grid
- [ ] One type scale is used throughout
- [ ] Interactive states are complete (hover, focus, active, disabled)
- [ ] Loading and empty states exist

### Anti-AI Check
- [ ] No glassmorphism used as automatic "premium" styling
- [ ] No decorative gradients or glows without purpose
- [ ] No identical card grids pretending all content is equal
- [ ] No filler copy ("operational clarity", "command center")
- [ ] No excessive border-radius on everything
- [ ] The result looks different from your last three outputs

### Accessibility
- [ ] Contrast ratios pass WCAG AA
- [ ] Focus states are visible
- [ ] Touch targets are ≥ 44px
- [ ] Content is navigable by keyboard
- [ ] Color is not the sole means of conveying information

### Responsiveness
- [ ] Layout works at mobile, tablet, and desktop widths
- [ ] No horizontal scrolling at any breakpoint
- [ ] Typography remains readable at all sizes
- [ ] Interactive elements remain usable on touch devices

---

## XIII. Design Playbook — Preferences, Rules & Scenarios

This section is opinionated. It documents the precise design preferences, hard rules, aesthetic instincts, and scenario-specific decisions that produce finished work that looks *authored* rather than *assembled*.

---

### A. Aesthetic Preferences — What the Final Product Should Feel Like

#### The "Feel" Targets

Every finished output should pass at least one of these gut checks:

| Feel | Description | When to aim for it |
|------|------------|-------------------|
| **Substantial** | Has visual weight. Feels like it was built, not generated. | Apps, tools, dashboards, anything interactive |
| **Quiet confidence** | Doesn't try hard. Just works. Earns attention through clarity. | Enterprise software, medical, legal, institutional |
| **Alive** | Responds. Breathes. Has subtle motion that rewards attention. | Consumer apps, creative tools, portfolios |
| **Editorial** | Reads like a magazine designed it. Typography leads everything. | Documents, reports, blogs, landing pages with text-heavy content |
| **Immersive** | The interface disappears. Content is the experience. | Media players, galleries, reading apps, data visualization |
| **Tactile** | Feels like touching real controls. Buttons depress. Toggles slide. | Music apps, creative tools, anything with physical metaphors |

#### My Default Gravity

When no brief pushes me in a particular direction, I gravitate toward:

- **Dark interfaces with warm neutrals** — not pure black (#000), but deep charcoal (#111, #141414, #1a1a1a) with warm undertones
- **One strong accent color used sparingly** — never more than 5% of the visible surface
- **Generous but not wasteful whitespace** — every gap has a reason, never padding for padding's sake
- **Typographic hierarchy that works at a squint** — if you blur the screen, the headline, subhead, body, and caption should still read as four distinct levels
- **Borders over shadows for containment** — a 1px border at 8–12% opacity over a surface does more honest work than an `rgba` shadow
- **Flat with depth cues** — not literally flat, not skeuomorphic, but surfaces that feel like they exist on a plane that has a subtle z-axis
- **Animations that finish fast** — most transitions under 200ms, nothing that makes the user wait for eye candy before they can act

#### What "Premium" Actually Means

"Premium" is the most misused word in AI design. Here's what it actually requires:

```
Premium ≠ dark + gradients + glassmorphism + large padding
Premium = precision + restraint + detail + consistency

Specifically:
- Pixel-perfect alignment (nothing off by 1px)
- Consistent spacing (same gap everywhere it should be the same)
- Considered empty states (not just "No data" in gray text)
- Smooth but fast transitions (not slow, floaty animations)
- Type that was chosen (not the first Google Font that loaded)
- Colors that have a relationship (not random hex values)
- Interactions that feel responsive (not laggy, not delayed by animation)
```

---

### B. Hard Rules I Always Follow

These are non-negotiable. Every output obeys these unless the brief explicitly overrides them with good reason.

#### CSS Rules

```css
/* 1. Box-sizing on everything. No exceptions. */
*, *::before, *::after { box-sizing: border-box; }

/* 2. Remove default margins. Control all spacing manually. */
body, h1, h2, h3, h4, h5, h6, p, figure, blockquote, dl, dd { margin: 0; }

/* 3. Smooth font rendering on macOS. */
body { -webkit-font-smoothing: antialiased; }

/* 4. Media defaults: block display, max-width containment. */
img, picture, video, canvas, svg { display: block; max-width: 100%; }

/* 5. Inherit fonts on form elements. They never should use browser defaults. */
input, button, textarea, select { font: inherit; }

/* 6. Text wrapping that doesn't break layouts. */
p, h1, h2, h3, h4, h5, h6 { overflow-wrap: break-word; }

/* 7. Root stacking context and smooth scrolling. */
#root, #__next { isolation: isolate; }
html { scroll-behavior: smooth; }

/* 8. Reduced motion respect. Always. */
@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
    scroll-behavior: auto !important;
  }
}
```

#### Structural Rules

| Rule | Why |
|------|-----|
| **No orphan screens.** Every state of the app has a design: empty, loading, error, success, partial. | An app that only looks good with perfect data is unfinished. |
| **Max content width: 1200–1440px.** Never let text stretch to full viewport on a 27" monitor. | Readability collapses beyond ~75 characters per line. |
| **Sticky elements earn their position.** Only stick navigation, toolbars, or CTAs that are used constantly. | Sticky headers that consume 80px of mobile viewport are a crime. |
| **Scrolling is natural.** Don't fight the scroll. No scroll hijacking, no parallax that breaks momentum. | Users know how to scroll. Respect the input device. |
| **Z-index is a system, not a number.** Define layers: `--z-base: 0; --z-dropdown: 100; --z-sticky: 200; --z-modal: 300; --z-toast: 400; --z-tooltip: 500;` | Random z-index values create an unwinnable arms race. |
| **One source of truth for every design token.** Colors, spacing, radii, shadows — all defined as CSS custom properties at `:root`. | If you change a color in three places, the third one will eventually be wrong. |

#### Visual Rules

| Rule | Precision |
|------|-----------|
| **Border radius is contextual.** | Buttons: 6–8px. Cards: 8–12px. Modals: 12–16px. Inputs: 6px. Avatars: 50%. Pill tags: 999px. Never one radius for all. |
| **Shadows have layers.** | Use 2–3 layered shadows instead of one heavy one. E.g., `0 1px 2px rgba(0,0,0,0.06), 0 4px 8px rgba(0,0,0,0.04)` beats `0 4px 12px rgba(0,0,0,0.15)`. |
| **Borders at low opacity, not gray.** | `border: 1px solid rgba(255,255,255,0.08)` on dark, `border: 1px solid rgba(0,0,0,0.06)` on light. These adapt to any surface. |
| **Background layering.** | Surface sits on background. Cards sit on surface. Modals sit on an overlay. Each layer is 1–3 values lighter/darker than the last. |
| **Color for meaning, not decoration.** | Red = destructive/error. Amber/yellow = warning/caution. Green = success/positive. Blue = informational/primary. Don't use these colors decoratively if they also carry semantic weight. |
| **Icon size matches text.** | If body text is 14px, icons should be 16px. If body is 16px, icons should be 18–20px. Never 24px icons next to 13px text. |
| **Focus rings are designed, not defaulted.** | `outline: 2px solid var(--primary); outline-offset: 2px;` — visible, consistent, and not ugly. |

---

### C. Things I Actively Avoid

Not just "anti-patterns" — these are specific moves I catch myself wanting to make and actively refuse:

#### Visual Avoidances

| What I Avoid | What I Do Instead |
|-------------|------------------|
| `background: linear-gradient(135deg, ...)` on containers as a default | Flat solid surfaces. Gradients only for specific branded elements or illustration. |
| `backdrop-filter: blur(20px)` on everything | Solid surfaces with appropriate opacity. Glass only when content genuinely overlaps. |
| `border-radius: 24px` or higher on cards | 8–12px for cards. Larger radii reserved for modals or hero elements with explicit intent. |
| `box-shadow: 0 25px 50px rgba(0,0,0,0.25)` — cinematic shadows | Subtle layered shadows. Heavy shadows only on truly elevated elements (modals, floating toolbars). |
| Gradient text (`-webkit-background-clip: text`) | Solid text color. Gradient text only for hero headlines with strong brand justification. |
| `transform: scale(1.05)` on card hover | `translateY(-2px)` or subtle background change. Scale feels cheap and distorts content. |
| Animated gradient borders | Static borders with color. Animated borders only in progress indicators or loading states. |
| Neon glow on buttons (`box-shadow: 0 0 20px var(--accent)`) | Subtle brightness increase on hover. Glow only in truly cyberpunk/gaming contexts. |
| Rainbow or multi-color gradients | Two-color relationship maximum. Multi-color only in charts, data viz, or explicit branding. |
| `letter-spacing: 0.2em` on everything uppercase | Uppercase sparingly, `letter-spacing: 0.04–0.06em` only on short labels, never on sentences. |

#### Structural Avoidances

| What I Avoid | What I Do Instead |
|-------------|------------------|
| Hero sections in admin tools | Jump straight to the functional interface. No welcoming theater. |
| Empty dashboards with "Get started!" cards | Actual useful empty states: recent items, quick actions, or honest "nothing here yet" with a single action. |
| Sidebar navigation for apps with <5 pages | Top navigation or tab bar. Sidebar is for deep navigation trees, not simple routing. |
| Modal dialogs for simple confirmations | Inline confirmation: button transforms to "Are you sure? [Yes] [Cancel]" |
| Toast notifications stacking up | One toast at a time, auto-dismiss in 3–5 seconds, action link inline. |
| Pagination when the dataset is small | Show everything. Paginate only when there are genuinely 50+ items. |
| Dropdown menus with 2–3 options | Radio buttons, segmented controls, or inline toggles. Dropdowns are for 5+ options. |
| Tabs with only 2 tabs | Toggle switch or segmented control. Tabs imply 3+ views. |
| Carousels for critical content | Grid or stack. Carousels hide information. Use only for media galleries where browsing is the intent. |

#### Behavioral Avoidances

| What I Avoid | What I Do Instead |
|-------------|------------------|
| Auto-playing video or audio | Static thumbnails with explicit play buttons. The user chooses when to hear sound. |
| Scroll-triggered animations on every element | Animate only the first screen on load. Deeper content appears instantly. |
| Custom scrollbars | Native scrollbars. Custom only if the design is truly immersive (e.g., a full-screen media app). |
| Cursor customization | Use the default cursor. `pointer` on clickable things, `text` on text. That's it. |
| Disabling browser zoom | Never. Accessibility violation. |
| Horizontal scroll on non-media content | Vertical scroll is natural. Horizontal scroll only for image carousels, timelines, or Kanban boards. |

---

### D. Scenario Playbook — "When I See X, I Build Y"

These are specific, opinionated design prescriptions for common project types.

#### Scenario 1: Dashboard / Analytics

```
Layout:
  - Sidebar navigation (collapsible on tablet)
  - Top bar with search, user menu, and global actions
  - Content area: no hero, no welcome banner
  - Data density: HIGH

Typography:
  - Font: Inter or Geist at 13–14px base
  - Monospaced for numbers in tables/KPIs (tabular-nums)
  - Weight contrast: 400 body, 600 labels, 700 section headers

Color:
  - Dark mode preferred (easier on eyes for long sessions)
  - Palette: Void Space or Obsidian Depth
  - Chart colors: 5–7 distinct hues from a sequential or categorical palette
  - Status colors: hard-coded semantic (red/amber/green/blue)

Spacing:
  - Base unit: 4px (tight)
  - Card padding: 16px
  - Section gaps: 16–24px
  - Table cell padding: 8–12px vertical, 12–16px horizontal

Components:
  - KPI cards ONLY if they show real, changing data with trend indicators
  - Tables over card grids for tabular data (always)
  - Filters in a horizontal bar or collapsible panel, never a right rail
  - Charts: simple, no 3D, no excessive decoration, clear axis labels

Motion:
  - Transitions: 100–150ms on tab switches, filter changes
  - Loading: skeleton screens (not spinners) for data regions
  - No entrance animations — data should appear instantly

What I refuse to build:
  - "Welcome back, [Name]!" hero sections
  - Decorative KPI cards with fake data
  - Gradient backgrounds on dashboard panels
  - Oversized charts with no interactivity
```

#### Scenario 2: Marketing / Landing Page

```
Layout:
  - Full-width sections with alternating visual weight
  - Navigation: minimal top bar (logo + 3–5 links + CTA button)
  - NOT the template: Hero → Features → Testimonials → CTA → Footer
  - Instead: diagnose what the page is actually selling

Typography:
  - Two fonts: display serif/grotesque for headlines + clean sans for body
  - Heading sizes: dramatic scale (1.333–1.500 ratio)
  - Base: 17–18px for comfortable reading
  - Line-height: 1.6–1.7 for body, 1.1–1.2 for headlines

Color:
  - Led by brand or product personality, not "what looks modern"
  - One dominant color, one accent, generous use of neutrals
  - Avoid: blue-to-purple gradient backgrounds (the AI cliché)

Spacing:
  - Base unit: 12px (generous)
  - Section spacing: 80–120px between major sections
  - Component spacing: 24–48px between elements within sections
  - Max content width: 1100–1200px

Composition:
  - Visual hierarchy: one focal point per viewport height
  - Alternate between text-led and image-led sections
  - Use asymmetric layouts when content supports it
  - Social proof: real testimonials with names, photos, specifics — or skip it entirely
  - Feature sections: show, don't list. Screenshots, videos, interactive demos > bullet points

Motion:
  - Scroll-triggered animations: ONLY on the first 1–2 sections, subtle fade+translate
  - Hero: may have a subtle animation or interactive element
  - CTA buttons: clear hover state, no bouncing or pulsing

What I refuse to build:
  - Feature grids with generic icons and one-line descriptions
  - "Trusted by [logo bar]" with 8 gray logos
  - "Here's what our users say" with obviously fabricated quotes
  - Three-tier pricing tables with one "recommended" column highlighted
  - Cookie-cutter SaaS landing pages indistinguishable from the last 50
```

#### Scenario 3: Form / Data Entry

```
Layout:
  - Single column, max-width 600px, centered
  - Grouped by logical sections with clear section titles
  - Progress indicator if multi-step (not numbered dots — a bar or fraction like "Step 2 of 4")

Typography:
  - Font: system or Inter at 15–16px
  - Labels: 13–14px, font-weight 500, positioned above inputs
  - Help text: 12–13px, muted color, below inputs

Color:
  - Calm, neutral backgrounds
  - Primary color on submit/action buttons only
  - Red sparingly: only on actual errors, never on required-field asterisks
  - Input borders: neutral gray, primary color on focus

Spacing:
  - Base unit: 8px
  - Between label and input: 4–6px
  - Between form fields: 20–24px
  - Between sections: 32–40px
  - Padding inside inputs: 10–12px vertical, 12–16px horizontal

Inputs:
  - Height: 40–44px (comfortable touch target)
  - Border-radius: 6px (not round, not sharp)
  - Border: 1px solid, ~15% opacity, darkens to primary on focus
  - Placeholders: muted but readable, never used as labels
  - Disabled: reduced opacity + not-allowed cursor + subtle background change

Validation:
  - Inline validation on blur, not on every keystroke
  - Error messages below the field, in red, with an icon
  - Success feedback: green check or brief inline text, not a full-page celebration
  - Never clear the form on a failed submission

What I refuse to build:
  - Inline labels that animate into floating labels (clever but bad UX — users miss them)
  - Custom-styled dropdowns that break keyboard navigation
  - Multi-step wizards for forms with <8 fields
  - "Fun" animated form elements (confetti on submit, etc.) for serious forms
```

#### Scenario 4: Document / Report / Text-Heavy Content

```
Layout:
  - Single column, max-width 680–720px for body text
  - Optional narrow sidebar for table of contents (sticky, lightweight)
  - Generous vertical margins between sections

Typography:
  - THIS IS THE STAR. Everything else supports it.
  - Body font: humanist sans or readable serif at 17–19px
  - Line-height: 1.65–1.75
  - Heading scale: Perfect Fourth (1.333) — clear differentiation without shouting
  - Paragraph spacing: 1–1.5em between paragraphs
  - Pull quotes or callouts: indented, slightly larger, different weight

Color:
  - Minimal. Content does the work.
  - High contrast text: #1a1a1a on #fafafa or similar
  - Links: underlined with primary color, no color on visited unless helpful
  - Code blocks: subtle background tint, monospaced, clear contrast

Spacing:
  - Base unit: 8px
  - Between paragraphs: 16–24px
  - Between sections (h2): 48–64px
  - Between subsections (h3): 32–40px
  - Lists: 8px between items, 24px above/below the list

Structure:
  - Headings as anchors (linked, hoverable anchor icon)
  - Code blocks with language labels and copy buttons
  - Tables with alternating row shading OR clear horizontal rules
  - Images with captions, constrained to content width

What I refuse to build:
  - Card-based layouts for article content
  - Dark mode documents unless explicitly requested (reading = light background)
  - Decorative sidebar widgets competing with the content
  - Animated headings or section entrances on text-heavy pages
```

#### Scenario 5: Creative Portfolio / Personal Site

```
Layout:
  - BREAK THE GRID. This is where personality lives.
  - Asymmetric compositions, overlapping elements, varied section heights
  - Navigation: minimal, possibly hidden or unconventional (but still accessible)
  - Full-bleed images, mixed media, dramatic whitespace

Typography:
  - Expressive. This is one of the few contexts where display/decorative fonts earn their place.
  - Heading: a distinctive display face (e.g., Cabinet Grotesk, Clash Display, Instrument Serif)
  - Body: clean and readable as counterbalance
  - Large type used as a compositional element, not just a label

Color:
  - Personal. Should feel like a specific human's taste, not a template.
  - Can be bold, can be muted — must be coherent
  - Background treatments: allowed to be unusual (off-whites, warm tints, full-color sections)

Motion:
  - MORE ALLOWED HERE than anywhere else
  - Cursor interactions, scroll-linked animations, hover reveals
  - Page transitions between projects
  - But still: purposeful. Every animation should reveal something or create continuity.

What I refuse to build:
  - Grid of project thumbnails with identical aspect ratios and a "View Case Study" button
  - Generic "About / Work / Contact" three-page portfolio
  - Stock photo backgrounds
  - "Designed by [Name]" with no actual personality in the design itself
```

#### Scenario 6: Internal Tool / Admin Panel

```
Layout:
  - Dense. Functional. No decorative elements.
  - Sidebar for deep navigation, collapsible
  - Breadcrumbs for orientation in deep hierarchies
  - Content area: maximized, no unnecessary margins

Typography:
  - System font stack or Inter at 13–14px
  - Compact line-height: 1.35–1.45
  - Monospaced for IDs, timestamps, technical values
  - No display fonts, no decorative type

Color:
  - Neutral base (light or dark depending on usage hours)
  - Functional color only: status badges, severity indicators, action buttons
  - No branding in the layout — branding lives in the logo, not the UI

Spacing:
  - Base unit: 4px
  - Tight everywhere: 8px card padding is fine
  - Tables are the primary data display — not cards
  - Dense forms with compact field spacing

Components:
  - Data tables with sorting, filtering, and column resizing
  - Batch operations (select multiple → act)
  - Keyboard shortcuts for power users
  - Command palette (Cmd+K) for fast navigation

What I refuse to build:
  - Colorful onboarding flows for admin tools
  - Animated transitions between admin pages (just swap the content)
  - Glassmorphism or gradient panels in admin UI
  - Oversized buttons or touch-friendly sizing for desktop admin (unless explicitly requested)
```

#### Scenario 7: E-Commerce / Product Page

```
Layout:
  - Product image (large, zoomable) left/center, details right
  - Sticky add-to-cart on scroll (mobile: bottom bar CTA)
  - Content sections below: reviews, specs, related products
  - Trust signals near the CTA: shipping info, return policy, secure payment

Typography:
  - Product name: large, bold, 24–32px
  - Price: prominent, not in brand color (black or near-black for honesty)
  - Crossed-out original price: muted but readable, not theatrically red
  - Description: 15–16px, readable, scannable with bullets

Color:
  - Clean and neutral. The product photos are the color.
  - Brand color only on primary CTA and key links
  - Background: white or near-white (products need neutral context)
  - Avoid: colored backgrounds that clash with product photography

Imagery:
  - High-quality product photos on neutral backgrounds
  - Multiple angles, lifestyle shots, and detail crops
  - Aspect ratio: consistent across all product images
  - Video where it adds value (clothing fit, electronics function)

What I refuse to build:
  - "SALE!!!" badges with red starbursts
  - Auto-playing product carousels
  - Fake urgency ("Only 2 left!" "17 people are viewing this!")
  - Cluttered product pages with 15 trust badges above the fold
```

#### Scenario 8: Data Visualization / Charts

```
Color:
  - Sequential data: single-hue ramp (light to dark of one color)
  - Categorical data: perceptually distinct hues (max 7 before it breaks down)
  - Diverging data: two-hue ramp crossing a neutral midpoint
  - NEVER use red and green as the only differentiators (colorblind-hostile)
  - Chart background: transparent or match the surface. Never a different shade.

Typography:
  - Axis labels: 11–12px, muted but readable
  - Data labels: same size as axis labels or smaller
  - Chart titles: concise, same style as the section heading system
  - Units always visible (%, $, ms, etc.)

Layout:
  - Charts sized to their data, not stretched to fill space
  - Legend: next to the chart if simple, below if complex, never overlapping data
  - Grid lines: very subtle or removed entirely. Let the data speak.
  - No 3D charts. Ever. Not pie, not bar, not surface. 2D only.

Interaction:
  - Tooltips on hover with precise values
  - Click to filter where appropriate
  - Responsive: charts reflow, don't just scale down

What I refuse to build:
  - Pie charts with more than 5 segments
  - 3D bar charts
  - Animated chart entrances that play on every tab switch
  - Dashboard screens that are 80% chart, 20% explanation (context matters)
```

#### Scenario 9: Mobile-First App

```
Layout:
  - Tab bar navigation at the bottom (4–5 items max)
  - Full-width content, no sidebars
  - Pull-to-refresh where data is live
  - Sheet modals from bottom, not centered modals

Typography:
  - System fonts (SF Pro on iOS, Roboto on Android) or Inter as cross-platform
  - Body: 15–16px minimum (small screens, big text)
  - Headers: 20–28px, functional not decorative
  - Touch-friendly: all interactive text ≥ 14px

Spacing:
  - Base unit: 8px
  - Content padding: 16–20px horizontal
  - Between list items: 12–16px
  - Section spacing: 24–32px
  - Bottom safe area: always account for home indicator / gesture bar

Gestures:
  - Swipe to dismiss / go back (if native or PWA)
  - Long press for context menus
  - Pinch to zoom on media

What I refuse to build:
  - Hamburger menu on mobile (bottom tabs are always better)
  - Tiny touch targets padded with whitespace but small hit areas
  - Desktop layouts shrunken to mobile width
  - Fixed headers taller than 56px on mobile
```

---

### E. The Finished Product Smell Test

Beyond checklists, a finished design should pass these instinct-level tests:

**The Squint Test**
Defocus your eyes. Can you still tell what's a heading, what's a button, what's content, and what's navigation? If everything blurs into one gray mass, the hierarchy has failed.

**The Screenshot Test**
Take a screenshot with no context. Show it to someone. Can they tell what the product does within 3 seconds? If not, the layout is failing at its primary job.

**The "Remove One Thing" Test**
Look at every element on the screen. If you remove it, does anything break? If removing it changes nothing, it shouldn't be there. Every element must earn its pixels.

**The Return Visit Test**
Imagine coming back to this interface after two weeks away. Can you find what you need without re-learning the layout? If the design is clever but not memorable, it's failing.

**The Peer Comparison Test**
Put your output next to three competitors in the same category. Does yours look:
- As good? → Acceptable.
- Better without being louder? → Good.
- Unmistakably different but clearly competent? → Great.
- Like it came from the same generator? → Failed.

**The "Would I Ship This" Test**
The final, honest question: if this were *your* product, going live tonight, with your name on it — would you ship it exactly as-is? If the answer is "almost" or "with a few tweaks," those tweaks are not optional. Do them.

---

## XV. Design Workflow & Refinement Process

This section documents the complete end-to-end workflow for any design-sensitive output. It integrates the logical reasoning framework (Section 0) with the design systems (Sections I–XIV) into a single operational process.

### The Workflow

```
Phase 1: UNDERSTAND
├── Read the full request. What is actually being asked?
├── Identify the output type: UI, website, app, document, slide, visualization, other
├── Identify the audience, brand, tone, and purpose
├── Apply Section 0: state the goal, facts, constraints, assumptions
└── If ambiguous, resolve from context or ask

Phase 2: INSPECT
├── Examine existing context: codebase, brand assets, prior work, design system
├── Note what already exists and must be preserved
├── Identify technical constraints: platform, framework, browser support, performance
└── Determine what can change and what cannot

Phase 3: GATHER CONSTRAINTS
├── Accessibility requirements (WCAG level, target devices)
├── Performance budgets (load time, bundle size, animation frame rate)
├── Brand guidelines (colors, fonts, tone of voice, logo usage)
├── Content requirements (real data, edge cases, empty/loading/error states)
└── Technical stack (HTML/CSS/JS? React? Print? PDF?)

Phase 4: PLAN
├── Apply Section I: walk through Purpose → Structure → Hierarchy → Tone → System → Polish
├── Choose layout strategy (Section VII)
├── Choose typography system (Section V)
├── Choose color approach (Section IV)
├── Choose spacing system (Section VI)
├── Choose motion approach (Section VIII)
├── Reference the Scenario Playbook (Section XIII.D) for the closest match
└── Sketch the information architecture before touching any visuals

Phase 5: RESEARCH
├── If the domain is unfamiliar, research it
├── Study comparable products in the same category
├── Identify what works and what feels generic in the category
└── Gather reference points, not for copying, but for understanding the landscape

Phase 6: BUILD
├── Implement the design, starting with structure and typography
├── Layer in color, then spacing, then interaction, then polish
├── Follow the Hard Rules (Section XIII.B) — CSS reset, max-width, z-index system
├── Follow the Avoidance List (Section XIII.C) — no glass default, no scale-hover, etc.
└── Build all states: default, hover, focus, active, disabled, loading, empty, error

Phase 7: REFINE (The Uncodixify Pass)
├── Run the Anti-Pattern Index (Section II) against the output
├── Strip anything that fails the Main Rule: "does this feel like an AI default?"
├── Check: does the result respond to this specific task, brand, medium, audience, mood?
├── Check: are choices traceable to the brief, or did they come from defaults?
├── Check: is every component deliberate, or was something added because the space felt empty?
├── Apply the Quality Checklist (Section XII)
├── Apply the Finished Product Smell Test (Section XIII.E)
└── This pass is a filter — it removes the generic, it does not impose a new style

Phase 8: ITERATE IN BROWSER
├── View the output in an actual browser at real viewport sizes
├── Check responsive behavior at mobile, tablet, desktop, and wide breakpoints
├── Test interactions: hover, focus, click, keyboard navigation
├── Verify accessibility: color contrast, focus rings, screen reader basics
├── Identify anything that looks or feels wrong and fix it
├── Do not skip this step — a design that was never viewed is not a design
└── Repeat refinement until the output passes the "Would I Ship This" test
```

### The Refinement Pass — What It Means in Practice

The refinement pass (Phase 7) is the core of Uncodixify. It is not a first pass; it is applied *after* the design is already built. Think of it like editing prose: you write freely, then you edit ruthlessly.

**What the refinement pass does:**

- Removes glassmorphism, gradient borders, and decorative glows that were added by reflex
- Replaces oversized border-radius with contextually appropriate values
- Strips startup-theater copy ("command center," "live pulse," "operational clarity")
- Consolidates heading stacks (eyebrow + title + subtitle + description → just the title)
- Reduces color usage from 6 random hues to 1–2 purposeful ones
- Replaces scale-on-hover with subtle, honest state changes
- Removes animations that exist only to look expensive
- Verifies that layout choices respond to content, not to template muscle memory

**What the refinement pass does NOT do:**

- It does not flatten the design into boring minimalism
- It does not ban all gradients, all shadows, all animation, all color
- It does not impose a single "correct" aesthetic
- It does not override strong, earned creative decisions that serve the brief
- It does not produce the same output regardless of input

### Design Is Iterative, Not One-Shot

A design produced in a single pass and never revised is almost always flawed. The expectation is:

1. **First pass:** Get the structure and content right. Don't worry about perfection.
2. **Second pass:** Apply the refinement filter. Remove the generic. Tighten the spacing.
3. **Third pass:** View in browser. Fix what looks wrong at real sizes. Test interactions.
4. **Fourth pass (if needed):** Respond to feedback. Adjust without regressing.

Each pass makes the output more intentional. The number of passes is not fixed — iterate until the output passes the smell tests in Section XIII.E.

### When This Workflow Triggers

Apply this workflow to any output that involves visual design decisions:

| Output Type | Trigger |
|------------|--------|
| HTML/CSS/JS websites and apps | Always |
| React, Vue, Svelte, or any frontend framework UI | Always |
| Dashboards and data visualizations | Always |
| Documents, reports, and text-heavy layouts | Always (typography and spacing matter) |
| PDFs and printable outputs | Always (different medium, same rigor) |
| Slide decks and presentations | Always (composition and pacing matter) |
| Simulations and interactive animations | Always (visual clarity and performance matter) |
| CLI tools and terminal output | Lighter touch — focus on information hierarchy and readability |
| Pure API or data work | Not applicable — no visual output |

---

## XVI. Anti-Convergence Oath

The most important rule in this document:

> **If your last five outputs look like siblings, something is broken.**

Different projects serve different people, different purposes, different moods. They should *feel* different. Not randomly — but meaningfully.

A medical dashboard and a music app and a legal document and a children's game should not share:
- the same card system
- the same border radius
- the same color temperature
- the same spacing rhythm
- the same typographic voice
- the same interaction personality

Variety is not chaos. It is evidence of actual design thinking.

If you catch yourself reaching for the same patterns out of comfort, stop. Go back to Section I. Start from purpose.

---

*That is how you Uncodixify.*
