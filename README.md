# Expedition Tracker

`Expedition Tracker` is a system-agnostic Foundry VTT module for GM-facing expedition timekeeping, wandering checks, timed effects, and expedition logging.

It is designed to stay compact and fast at the table while still supporting richer exploration options like timed light sources, journal logging, and effect countdowns.

## Current Status

- Module id: `expedition-tracker`
- Current version: `2026.04.10`
- Foundry compatibility:
  - minimum: `13`
  - verified: `14.359`

## Core Features

### Expedition Tracking HUD

- Compact GM-only expedition tracker HUD
- Draggable header
- Per-client saved HUD position
- Module-options `Reset Position` action
- Start/end expedition workflow
- Supports dungeon, overland, and custom time procedures

### Turn and Wandering Procedure Tracking

- Advance expedition turns directly from the HUD
- Built-in turn actions:
  - advance
  - rest
  - search
  - listen
  - custom other turn
- Wandering check support with:
  - configurable encounter chance
  - configurable cadence
  - optional auto-checking

### Expedition Logging

- Tracker log stored as typed log entries
- Current tracked entry types include:
  - turn actions
  - notes
  - wandering checks
  - timed effect activation
  - timed effect expiration
  - timed effect pause
  - timed effect resume
- Optional expedition journal logging

### Timed Effects

- Enable/disable the timed effect turn track from module settings
- Add timed effects from reusable templates
- Add fully custom timed effects
- Supports both:
  - predefined effect templates
  - one-off effects created in the dialog
- Track remaining duration on the HUD
- Manage active timed effects after creation

### Timed Effect Management

- Edit active timed effects
- Pause/resume timed effects
- Custom Foundry-styled hover tooltip
- Template-based effect names stay read-only
- Custom effects can be renamed

### Timed Effect Announcements

- Optional `Announce Effect` checkbox when adding a new effect
- Public chat announcement when enabled
- Current wording:
  - non-light effects: `<Character Name> gains <Effect Name>. (Duration: <X IncrementName>)`
  - light-source effects: `<Character Name> lights a <Effect Name>! (Duration: <X IncrementName>)`
- Effect icons are included in begin/end chat messages when available

### Light-Source Timed Effects

- Timed effect templates and custom effects can be marked as `Light Source`
- Supports:
  - bright light radius
  - dim light radius
  - emission angle
- Light-source effects bind to a real token on the current scene
- Token light updates immediately when the effect is applied
- Overlap policy:
  - newest active light-source effect wins
  - expiration/removal recalculates from remaining active light-source effects on that token
  - if none remain, token light resets to `0 / 0 / 360`
- Public extinguish chat message on natural expiration

### Theme Awareness

- The module now follows Foundry light mode vs dark mode automatically
- The tracker HUD, expedition dialogs, and timed-effect dialogs use module-scoped theme variables instead of a hard-forced dark palette

## Module Settings

Current settings include:

- `Enable Expedition Tracker`
- `Enable Timed Effects Turn Track`
- `Timed Effect Templates`
- `Reset Tracker Position`

## Current Next Priorities

The current highest-priority remaining work is:

1. Log filtering/toggles in the HUD
2. Improved journal formatting for typed log entries
3. UI refinement for crowded timed-effect slots and narrow-width layouts
4. Optional expiring-soon timed-effect visuals
5. Saved custom time procedure presets
