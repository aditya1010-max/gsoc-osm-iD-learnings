# Pull Requests for KBAR Integration in OSM-iD

## Overview

This document discusses the anticipated pull requests (PRs) and related considerations for integrating KBAR (Keyboard Bars) functionality into the iD editor used by OpenStreetMap.

## Expected PRs

### 1. Core KBAR Implementation

- Main UI component for keyboard bar rendering
- Event listeners and key binding handlers
- Configuration schema for keyboard layouts

### 2. Integration with iD Editor

- Connection points with existing iD modes and tools
- Toolbar integration
- Context-aware key binding management

### 3. Testing and Documentation

- Unit tests for key event handling
- Integration tests with iD workflows
- User-facing documentation updates

## Challenges and Considerations

### Code Review Points

- Backward compatibility with existing keyboard shortcuts
- Performance impact on startup and runtime
- Accessibility compliance (WCAG standards)
- Browser compatibility across supported versions

### Merge Conflicts

- Modifications to shared utility files
- Changes to iD's main initialization flow
- Updates to existing keybinding maps

### Dependencies

- Version compatibility with iD core
- External library dependencies
- Build system modifications

## Review Checklist

- [ ] No breaking changes to public APIs
- [ ] Tests provide adequate coverage
- [ ] Documentation is updated
- [ ] Performance benchmarks pass

🧩 PR 1 — Command registry abstraction

Theme: groundwork, not UI

What it introduces:

a lightweight command registry

mapping between:

command id

label

existing action callback

What it does NOT do:

no UI

no keyboard shortcuts

no new features

How it’s justified:

“This creates a single place to describe user-invokable actions, improving internal consistency.”

Why it gets accepted:

no behavior change

no user-facing impact

very low risk

This PR sets the chessboard.

🧩 PR 2 — Keyboard-triggered empty shell

Theme: interaction without behavior

What it adds:

Ctrl + K listener

opens a minimal, non-functional overlay (or logs)

What it does NOT do:

no commands executed

no shortcut conflicts

no mode changes

Justification:

“Establishes a non-conflicting entry point for future command discovery.”

Why maintainers accept it:

doesn’t touch existing shortcuts

easy to disable or revert

isolated code path

This PR proves non-invasiveness.

🧩 PR 3 — Minimal command execution (3 + 3)

Theme: proof of concept

What it wires:

add point / line / area

undo / redo / save

Why these?

they already exist

they’re well-understood

no tagging ambiguity

Justification:

“Demonstrates reuse of existing actions without duplicating logic.”

This PR answers the question:

“Does this respect iD’s architecture?”

🧩 PR 4 — Context awareness (small, surgical)

Adds:

filtering based on selection / mode

Example:

no “add line” when already drawing

Justification:

“Improves usability without altering behavior.”

This is where KBar stops feeling like a toy.

🧩 PR 5 — Discoverability & learning

Adds:

shortcut hints in command list

grouping by category

This PR is framed as:

“Improving onboarding and action discoverability.”

That’s a very strong justification.
