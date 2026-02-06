# Android Design Plugin for Claude Code

A Claude Code plugin that guides Claude to craft production-grade, visually distinctive Android application interfaces. Eliminates generic "AI slop" Android UIs and produces bold, intentional, memorable designs grounded in Material Design 3.

## Capabilities

- **Complete Theme Systems** — Full Color.kt, Typography.kt, Shape.kt, and Theme.kt generation with distinctive, non-default choices
- **Compose Screen Generation** — Production-grade Jetpack Compose screens with state hoisting, Modifier parameters, and @Preview annotations
- **XML Layout Support** — Legacy View-based layouts with the same aesthetic quality when explicitly requested
- **Animations** — AnimatedVisibility, staggered reveals, spring/tween motion specs, and meaningful transitions
- **Adaptive Layouts** — WindowSizeClass-aware designs for phones, tablets, and foldables
- **Accessibility** — 4.5:1 contrast ratios, 48dp touch targets, contentDescription, semantics, and TalkBack support

## Example Prompts

- "Create a dashboard screen for a fitness tracking app"
- "Generate a theme for a luxury banking app"
- "Build an onboarding flow with bold animations"
- "Design a music player screen with a brutalist aesthetic"
- "Create an XML layout for a settings screen"
- "Build an adaptive layout that works on phones and tablets"

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

## How It Works

The plugin auto-activates when Claude detects Android UI work — mentions of Compose, XML layouts, themes, screens, components, or Material Design 3. It forces a design-thinking step before code generation, ensuring every interface has a clear aesthetic direction rather than falling back to generic defaults.

You can also invoke it explicitly with `/android-design`.

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
