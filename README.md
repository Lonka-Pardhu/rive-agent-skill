# Rive Agent & Skill for Claude Code

> A specialized AI agent that understands **both** the Rive Editor and iOS/Swift runtime integration.

![Rive](https://img.shields.io/badge/Rive-Animation-ff6b6b?style=flat-square)
![Claude Code](https://img.shields.io/badge/Claude%20Code-Agent-7c3aed?style=flat-square)
![iOS](https://img.shields.io/badge/iOS-Swift-orange?style=flat-square)
![License](https://img.shields.io/badge/License-MIT-green?style=flat-square)

---

## The Problem

Generic AI assistants give you code but don't tell you what needs to be set up in your `.riv` file first. You end up with code that doesn't work because you're missing the editor-side setup.

## The Solution

This Rive agent explains the **full picture**:

1. **What to set up in the Rive Editor** (state machines, inputs, data binding, etc.)
2. **Then the iOS/Swift code** to make it work

No more "why isn't this working?" moments.

---

## Features

- **Dual-sided explanations** — Editor setup + Runtime code
- **iOS/SwiftUI focused** — Primary focus on Apple platform integration
- **Data binding expertise** — Dynamic text, images, colors, lists
- **Version awareness** — Knows which runtime versions support which features
- **Auto-fetches docs** — Searches rive.app/docs when needed
- **Auto-activates** — Triggers when you mention "rive", "state machine", ".riv file", etc.

---

## Installation

### Prerequisites

- [Claude Code](https://claude.ai/code) installed on your machine

### Step 1: Clone this repository

```bash
git clone https://github.com/Lonka-Pardhu/rive-agent-skill.git
```

Or download the ZIP and extract it.

### Step 2: Copy the Agent file

Copy `rive.md` to your Claude agents folder:

```bash
cp rive.md ~/.claude/agents/
```

**Or manually:**
1. Open Finder
2. Press `Cmd + Shift + G`
3. Type `~/.claude/agents/`
4. Drop the `rive.md` file there

### Step 3: Copy the Skill folder

Copy the entire `rive-docs` folder to your Claude skills folder:

```bash
cp -r rive-docs ~/.claude/skills/
```

**Or manually:**
1. Open Finder
2. Press `Cmd + Shift + G`
3. Type `~/.claude/skills/`
4. Drop the `rive-docs` folder there

### Step 4: Restart Claude Code

Quit and reopen Claude Code for the agent to be detected.

### Step 5: Verify Installation

Run `/agents` in Claude Code. You should see `rive` listed under User agents.

---

## File Structure

```
~/.claude/
├── agents/
│   └── rive.md              ← Agent file (copy here)
└── skills/
    └── rive-docs/
        └── SKILL.md         ← Skill file (copy folder here)
```

---

## Usage

Just ask any Rive-related question. The agent activates automatically.

### Example Prompts

```
How do I add Rive to my iOS app?
```

```
How do I create a button with dynamic text that changes at runtime?
```

```
How do I trigger an animation when a user taps?
```

```
How do I use data binding to update images from my Swift code?
```

```
My text isn't updating when I call setValue - what's wrong?
```

---

## What Makes This Agent Different

### Before (Generic AI)

```
Q: How do I play an animation?

A: Use riveView.play()
```

❌ Doesn't work because you don't know what to set up in the editor.

### After (This Agent)

```
Q: How do I play an animation?

A:
## In the Rive Editor:
1. Create a State Machine
2. Add an "idle" and "playing" state
3. Create a Trigger input named "playTrigger"
4. Connect the trigger to a transition
5. Assign your animation to the "playing" state

## In Your iOS Code:
let trigger = stateMachine.input(named: "playTrigger")
trigger?.fire()
```

✅ Complete picture — editor setup + code.

---

## Use Cases

| Use Case | What the Agent Helps With |
|----------|---------------------------|
| **Adding Rive to iOS app** | SPM/CocoaPods setup, basic integration |
| **Dynamic UI components** | Buttons, toggles, progress bars with data binding |
| **Interactive animations** | State machines, triggers, touch handling |
| **Loading remote content** | Dynamic images, user avatars from URLs |
| **Animation events** | Listening for animation completion, callbacks |
| **Troubleshooting** | Why animations don't play, text not updating |
| **Version compatibility** | Which runtime version supports which features |

---

## iOS Version Requirements

| Feature | Minimum iOS Runtime |
|---------|---------------------|
| Basic playback | v1.0.0+ |
| State machines | v2.0.0+ |
| Listeners | v2.0.21+ |
| Events | v5.3.1+ |
| Text | v5.1.5+ |
| Data Binding | v6.8.0+ |
| Image/List Binding | v6.11.0+ |
| Scripting | v6.13.0+ |

---

## Contributing

Found an issue or want to add more documentation? PRs welcome!

1. Fork this repository
2. Add your changes
3. Submit a pull request

---

## Credits

- [Rive](https://rive.app) — The animation platform
- [Claude Code](https://claude.ai/code) — AI coding assistant

---

## License

MIT License — Free to use, modify, and distribute.

---

<p align="center">
  <b>Built for developers learning Rive for iOS</b><br>
  If this helped you, consider giving it a ⭐
</p>
