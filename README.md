# Rive Agent & Skill for Claude Code

> A specialized AI agent that understands **both** the Rive Editor and runtime integration — works great with iOS/Swift especially.

![Rive](https://img.shields.io/badge/Rive-Animation-ff6b6b?style=flat-square)
![Claude Code](https://img.shields.io/badge/Claude%20Code-Agent-7c3aed?style=flat-square)
![Platform](https://img.shields.io/badge/Platform-All-blue?style=flat-square)
![License](https://img.shields.io/badge/License-MIT-green?style=flat-square)

---

## The Problem

Generic AI assistants give you code but don't tell you what needs to be set up in your `.riv` file first. You end up with code that doesn't work because you're missing the editor-side setup.

## The Solution

This Rive agent explains the **full picture**:

1. **What to set up in the Rive Editor** (state machines, inputs, data binding, etc.)
2. **Then the runtime code** to make it work

No more "why isn't this working?" moments.

---

## Features

- **Dual-sided explanations** — Editor setup + Runtime code
- **Works with all platforms** — iOS, Android, Flutter, React Native, Web, Unity, Unreal
- **Optimized per Anthropic guidelines** — Focused agent (79 lines) + progressive disclosure skill
- **Preloads skill automatically** — rive-docs skill injected at startup
- **Persistent memory** — Learns patterns across conversations
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
│   └── rive.md                      ← Agent (79 lines, optimized)
├── skills/
│   └── rive-docs/                   ← Skill folder
│       ├── SKILL.md                 ← Core skill (109 lines)
│       └── references/
│           ├── feature-support.md   ← Version tables
│           ├── runtime-packages.md  ← Installation info
│           └── doc-links.md         ← Documentation URLs
└── agent-memory/
    └── rive/                        ← Persistent memory (auto-created)
```

**Optimized per Anthropic best practices:**
- Agent preloads `rive-docs` skill automatically
- Progressive disclosure — reference files load only when needed
- Persistent memory — learns patterns across conversations

---

## Updating & Customizing

You can update or customize the agent anytime:

- **Add version info** — Edit `~/.claude/skills/rive-docs/references/feature-support.md`
- **Add doc links** — Edit `~/.claude/skills/rive-docs/references/doc-links.md`
- **Modify core skill** — Edit `~/.claude/skills/rive-docs/SKILL.md`
- **Modify agent behavior** — Edit `~/.claude/agents/rive.md`
- **Pull updates** — Run `git pull` in the cloned repo and copy the updated files

---

## Usage

Just ask any Rive-related question. The agent activates automatically.

### Example Prompts

```
How do I add Rive to my app?
```

```
How do I create a button with dynamic text that changes at runtime?
```

```
How do I trigger an animation when a user taps?
```

```
How do I use data binding to update images?
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

## In Your Code:
// Get the trigger input and fire it
let trigger = stateMachine.input(named: "playTrigger")
trigger?.fire()
```

✅ Complete picture — editor setup + code.

---

## Use Cases

| Use Case | What the Agent Helps With |
|----------|---------------------------|
| **Adding Rive to your app** | Setup for iOS, Android, Flutter, React Native, Web |
| **Dynamic UI components** | Buttons, toggles, progress bars with data binding |
| **Interactive animations** | State machines, triggers, touch handling |
| **Loading remote content** | Dynamic images, user avatars from URLs |
| **Animation events** | Listening for animation completion, callbacks |
| **Troubleshooting** | Why animations don't play, text not updating |
| **Version compatibility** | Which runtime version supports which features |

---

## Runtime Version Requirements

| Feature | iOS | Android | Flutter | Web |
|---------|-----|---------|---------|-----|
| Basic playback | v1.0.0+ | v2.0.0+ | v0.8.0+ | v1.0.0+ |
| State machines | v2.0.0+ | v3.0.0+ | v0.9.0+ | v1.0.0+ |
| Listeners | v2.0.21+ | v3.0.8+ | v0.9.0+ | v1.0.65+ |
| Events | v5.3.1+ | v8.4.0+ | v0.11.17+ | v2.4.3+ |
| Data Binding | v6.8.0+ | v10.1.0+ | v0.14.0+ | v2.26.6+ |
| Scripting | v6.13.0+ | v11.1.0+ | v0.14.1+ | v2.34.0+ |

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
  <b>Built for developers learning Rive</b><br>
  If this helped you, consider giving it a ⭐
</p>
