---
name: rive-docs
description: Rive animation platform documentation. Use for editor workflows, Luau scripting, state machines, data binding, app runtimes (iOS, Android, Flutter, React Native, Web), game runtimes (Unity, Unreal, Defold). Triggers on "rive", ".riv files", "state machine", "artboard", "rive runtime", "rive animation".
---

# Rive Documentation

## Quick Reference

### File Format
- `.riv` - Compiled Rive animation file

### State Machine Inputs
- **Trigger** - Fire once, auto-resets
- **Boolean** - true/false state
- **Number** - Numeric value for conditions

### Data Binding Types
- Text, Color, Number, Boolean, Image, List, Enum

## Core Areas

### Editor
Design, animate, create state machines, set up data binding.
- Interface: toolbar, hierarchy, inspector, stage
- Animate mode: timeline, keyframes
- State machines: states, transitions, inputs, listeners

### Scripting (Luau)
Add interactivity with Luau scripts.
- Protocols: `onLoad`, `onStateChange`, `onMouseEnter`, `onMouseLeave`, `onPointerDown`, `onPointerUp`, `onPointerMove`
- Debug panel for troubleshooting
- AI Agent for script generation

### App Runtimes
iOS, Android, Flutter, React Native, Web, React.
- Load `.riv` files
- Control state machines via inputs
- Bind dynamic data (text, images, colors)
- Listen for Rive events

### Game Runtimes
Unity, Unreal, Defold.
- Custom engine integration via C++ runtime

## When to Fetch Docs

Use WebFetch for implementation details:

**Platform Setup:**
- iOS: `https://rive.app/docs/runtimes/overview/apple`
- Android: `https://rive.app/docs/runtimes/overview/android`
- Flutter: `https://rive.app/docs/runtimes/overview/flutter`
- React Native: `https://rive.app/docs/runtimes/overview/react-native`
- Web: `https://rive.app/docs/runtimes/overview/web-js`
- React: `https://rive.app/docs/runtimes/overview/react`

**Features:**
- Data Binding: `https://rive.app/docs/runtimes/data-binding`
- State Machines: `https://rive.app/docs/runtimes/state-machines`
- Events: `https://rive.app/docs/runtimes/rive-events`
- Text: `https://rive.app/docs/runtimes/text`

**Editor:**
- State Machines: `https://rive.app/docs/editor/state-machine/state-machine`
- Data Binding Setup: `https://rive.app/docs/editor/data-binding/overview`

**Scripting:**
- Getting Started: `https://rive.app/docs/scripting/getting-started`
- Protocols: `https://rive.app/docs/scripting/protocols`

**Game Runtimes:**
- Unity: `https://rive.app/docs/game-runtimes/unity/unity`
- Unreal: `https://rive.app/docs/game-runtimes/unreal/unreal`
- Defold: `https://rive.app/docs/game-runtimes/defold`

## Reference Files

Load these when specific details needed:

- **Version requirements**: See `references/feature-support.md`
- **Runtime packages & installation**: See `references/runtime-packages.md`
- **Full documentation links**: See `references/doc-links.md`

## Common Patterns

### State Machine Control (All Platforms)
1. Get state machine controller from artboard
2. Find input by name (trigger/boolean/number)
3. Set value or fire trigger
4. Runtime handles transitions automatically

### Data Binding (All Platforms)
1. Create View Model in editor with properties
2. Bind properties to artboard elements
3. At runtime, get view model instance
4. Update property values dynamically

### Rive Events
1. Add event in editor (on state/transition)
2. Set event name and optional properties
3. Register event listener at runtime
4. Handle event with callback

## Resources

- Community: https://community.rive.app
- Tutorials: https://rive.app/docs/tutorials/learn-rive
- Feature Support: https://rive.app/docs/feature-support
