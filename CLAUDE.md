# Kanata Keyboard Configuration

## Overview
This repository contains Kanata keyboard configurations for macOS, originally ported from a Glove80 ZMK configuration.

## Files
- `glove80.kbd` - Main Kanata config (QWERTY with Glove80-style homerow mods)
- `16_macbook_qwerty.kbd` - QWERTY variant for 16" MacBook Pro
- `16_macbook.kbd` - Colemak-DH variant for 16" MacBook Pro
- `glove80.zmk` - Original Glove80 ZMK config (reference)
- `kanata.cron` - Cron job for auto-restart on crash

## Hardware Target
- Configured for **16" MacBook Pro** with physical function keys

## Auto-Restart
A cron job monitors Kanata and restarts it if it crashes:
```bash
# Add to root crontab with: sudo crontab -e
* * * * * pgrep -x kanata > /dev/null || /opt/homebrew/bin/kanata --cfg /path/to/glove80.kbd &
```

## Key Features

### Homerow Mods (QWERTY Row)
Modifiers on the top letter row using tap-hold:
- **Left hand**: Q=LCTRL, W=LSHFT, E=LALT, R=LGUI
- **Right hand**: U=RGUI, I=RALT, O=RSHFT, P=RCTRL
- Timing: tap-time=175ms, hold-time=230ms

### Layer Toggles (Home Row)
Layer access via tap-hold on the home row:
- **Left hand**: S=symbols2, D=symbols1, F=nav, G=numpad
- **Right hand**: J=nav, K=symbols1, L=symbols2

### Layers

**Base Layer**:
- Caps Lock remapped to Escape
- Spacebar = tap-hold for space/Meh (Ctrl+Alt+Shift)

**Nav Layer** (Navigation & Media):
- Arrow keys on right hand (IJKL cluster)
- Copy/Paste tap-dance on U (single tap=copy, double tap=paste)
- Media controls, volume, tab navigation

**Symbols1 Layer**:
- Programming symbols: Hash (#), Dollar ($), Pipe (|), etc.

**Symbols2 Layer**:
- Additional symbols: Parentheses, curly braces, asterisk, colon

**Numpad Layer**:
- Traditional numpad layout on right hand

### Special Features
- **Meh Key**: Space bar tap-hold (tap=space, hold=Ctrl+Alt+Shift)
- **MacBook Keys**: Mission Control (Ctrl+Up), Spotlight (Cmd+Space), Dictation

## Configuration Details

### Timing Values
```
tap-time: 175ms
hold-time: 230ms
```
Based on ZMK config's `tapping-term-ms` and `quick-tap-ms` settings.

### Special Aliases
- `@meh`: Multi-modifier (Ctrl+Alt+Shift)
- `@tmeh`: Tap-hold for space/Meh
- `@mc`: Mission Control
- `@sls`: Spotlight Search

## Common Questions

**Q: Why are mods on QWERTY row instead of home row?**
A: To avoid accidental activation while typing on the home row. Layer toggles use home row instead.

**Q: What's the Meh key used for?**
A: Meh (Ctrl+Alt+Shift) creates a unique modifier combo for custom shortcuts without conflicts.
