# Android Design Plugin for Claude Code

A Claude Code plugin that guides Claude to craft production-grade, visually distinctive Android application interfaces. Eliminates generic "AI slop" Android UIs and produces bold, intentional, memorable designs grounded in Material Design 3.

## Capabilities

- **Complete Theme Systems** — Full `Color.kt`, `Typography.kt`, `Shape.kt`, and `Theme.kt` generation with distinctive, non-default choices
- **Compose Screen Generation** — Production-grade Jetpack Compose screens with state hoisting, Modifier parameters, and `@Preview` annotations
- **XML Layout Support** — Legacy View-based layouts with the same aesthetic quality when explicitly requested
- **Animations** — `AnimatedVisibility`, staggered reveals, spring/tween motion specs, and meaningful transitions
- **Adaptive Layouts** — `WindowSizeClass`-aware designs for phones, tablets, and foldables
- **Accessibility** — 4.5:1 contrast ratios, 48dp touch targets, `contentDescription`, semantics, and TalkBack support

## How It Works

The plugin enforces a mandatory three-phase workflow that prevents jumping straight to code:

### Phase 1 — Design Declaration

Before any code is written, Claude produces a design declaration covering app purpose, emotional tone, aesthetic lineage (concrete visual influences), and explicit anti-goals (what the design intentionally avoids).

### Phase 2 — Design Constraints & Commitments

Claude locks in binding decisions for light/dark strategy, corner philosophy, typography pairing, motion philosophy, and density level. These cannot be contradicted later.

### Phase 3 — Self-Critique

After generating the UI, Claude performs a non-skippable self-critique: a snapshot evaluation, a comparison against best-in-class Android apps, and an anti-slop checklist. If any check fails, revision is required.

## Design Philosophy

- Default Material purple and default tonal palettes are **forbidden**
- Default card lists are **forbidden** — repeated content must vary in size, rhythm, or treatment
- Every non-trivial screen must use at least two compositional techniques: asymmetric padding, scale contrast, overlap/layering, full-bleed elements, or negative space
- Motion must express intent — spring for organic/playful, tween for editorial/precise, snap for brutalist/technical
- Light and dark themes are designed separately, not auto-inverted
- Typography must be chosen intentionally — default Roboto without customization is not allowed

## Installation

### Quick start (single session)

Load the plugin for the current session:

```bash
claude --plugin-dir /path/to/android-design
```

### Persistent installation (recommended)

To auto-load the plugin on every Claude Code session:

1. Clone this repo somewhere on your machine:
   ```bash
   git clone https://github.com/moictab/android-design.git
   ```

2. Inside Claude Code, add the marketplace and install the plugin:
   ```
   /plugin marketplace add /path/to/android-design
   /plugin install android-design@moictab-plugins
   ```

3. Restart Claude Code. The plugin loads automatically on every future session, across all repositories.

## Invocation

The plugin auto-activates when Claude detects Android UI work — mentions of Compose, XML layouts, themes, screens, components, Material Design 3, and more.

You can also invoke it explicitly with `/android-design`.

For best results, provide at least one of:
- A comparable app you like (and why)
- A vibe reference ("feels like X, but for Y")
- A strong constraint ("must feel severe", "must feel luxurious", etc.)

## Example Prompts

- "Create a dashboard screen for a fitness tracking app"
- "Generate a theme for a luxury banking app"
- "Build an onboarding flow with bold animations"
- "Design a music player screen with a brutalist aesthetic"
- "Create an XML layout for a settings screen"
- "Build an adaptive layout that works on phones and tablets"

## Structure

```
.claude-plugin/
  plugin.json            # Plugin manifest
  marketplace.json       # Marketplace manifest for persistent install
skills/
  android-design/
    SKILL.md             # Core skill instructions
```

## Author

[moictab](https://github.com/moictab)
