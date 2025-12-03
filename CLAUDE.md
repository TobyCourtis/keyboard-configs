# Kanata Keyboard Configuration

## Overview
This directory contains a Kanata keyboard configuration that has been ported from a Glove80 ZMK configuration.

- **Source**: `src/kanata/glove80.zmk` - Original Glove80 ZMK config
- **Target**: `/Users/tobyc/Documents/repos/scripts/src/kanata/glove80.kbd` - Current Kanata configuration

## Hardware Target
- Configured for **16" MacBook Pro** with physical function keys
- Excludes Bluetooth devices (MX Master 2S, MX Vertical) to prevent conflicts

## Key Features

### 1. Homerow Mods (QWERTY Row)
Modifiers are implemented on the top letter row using tap-hold behavior:
- **Left hand**: Q=LCTRL, W=LSHFT, E=LALT, R=LGUI
- **Right hand**: U=RGUI, I=RALT, O=RSHFT, P=RCTRL
- Timing: tap-time=175ms, hold-time=230ms (based on ZMK config)

### 2. Layer Toggles (Home Row)
Layer access via tap-hold on the home row:
- **Left hand**: S=layer3, D=layer2, F=layer1, G=numpad
- **Right hand**: J=layer1, K=layer2, L=layer3

### 3. Layers

**Base Layer**:
- Caps Lock remapped to Escape
- Spacebar = tap-hold for space/Meh (Ctrl+Alt+Shift)
- Function row includes media controls (brightness, etc.)

**Layer 1** (Navigation & Media):
- Arrow keys on right hand (IJKL cluster)
- Copy/Paste tap-dance on U (single tap=copy, double tap=paste)
- Media controls (prev/next/play-pause)
- Volume controls
- Tab navigation (Cmd+Tab, Cmd+Shift+Tab)
- Bracket navigation (Opt+[ / Opt+])

**Layer 2** (Symbols):
- Programming symbols and operators
- Common brackets and operators in accessible positions
- Hash (#), Dollar ($), Pipe (|), etc.

**Layer 3** (More Symbols):
- Additional symbols and special characters
- Parentheses, curly braces, asterisk
- Colon, semicolon variations

**Numpad Layer**:
- Traditional numpad layout on right hand
- Numbers 0-9 in standard numpad arrangement

### 4. Special Features
- **Meh Key**: Space bar tap-hold (tap=space, hold=Ctrl+Alt+Shift)
- **Copy/Paste Tap-Dance**: Single tap copies, double tap pastes (200ms window)
- **Media Keys**: Mapped to F1-F2 for brightness, with emoji indicators
- **Device Exclusions**: Configured to ignore specific Bluetooth mice

## Configuration Details

### Timing Values
```
tap-time: 175ms
hold-time: 230ms
```
These values are ported from the ZMK config's `tapping-term-ms` and `quick-tap-ms` settings.

### Special Aliases
- `@meh`: Multi-modifier (Ctrl+Alt+Shift)
- `@tmeh`: Tap-hold for space/Meh
- `@cpypst`: Copy/Paste tap-dance
- Media controls with emoji indicators (🔅🔆◀◀▶⏸▶▶🔇🔉🔊)

## When Helping with Improvements

Consider:
1. **Timing adjustments**: The tap/hold times may need tuning based on typing speed
2. **Layer accessibility**: Current layer toggles use home row - consider ergonomics
3. **Symbol placement**: Layer 2 & 3 have programming symbols - verify common workflows
4. **Conflicts**: Watch for unintended activations with homerow mods
5. **macOS specific**: Some shortcuts use Cmd (lmet/rmet) - ensure macOS compatibility
6. **Device exclusions**: Check if Bluetooth device exclusions are still needed

## Common Questions

**Q: Why are mods on QWERTY row instead of home row?**
A: To avoid accidental activation while typing on the home row. Layer toggles use home row instead.

**Q: What's the Meh key used for?**
A: Meh (Ctrl+Alt+Shift) creates a unique modifier combo for custom shortcuts without conflicts.

**Q: Why exclude Bluetooth mice?**
A: These devices can send basic keyboard commands that interfere with Kanata's processing.