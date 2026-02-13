so my idea is that it will focus on:

Can future contributors understand this system?
Can maintainers evolve it without you?
Is this documented where it belongs (not random markdown)?

Docs will cover 3 audiences:
1 Users
2 Contributors
3 Maintainers

KBar Documentation

1. KBar Overview & Architecture Doc

- It will be for contributors/revievers
- It will explain what is Kbar and why it exists in iD
- Whats its relationship with: *modes *presets *actions *systems(like i10n)
- it will contain high-level flow diagram
- data flow: action -> selection -> mode -> execution

2. Action Registration Guide

- It will be for contributors
- It is huge and will explain a lot of things
- Action object structure
- Required vs optional fields
- Lifecycle (onSelect, availability, cleanup)
- How localization is applied to titles/descriptions
- Common mistakes (like undefined context systems 👀)

Includes Examples

- Simple static action
- Context-aware action
- Preset-backed action

It will basically “Provide a contributor guide detailing how to register new KBar actions, including localization and context awareness.”

3. Localization & i18n Documentation (Dedicated Section)

- It will explain a lot of things like
- How KBar uses iD’s l10n system
- When to use l10n.t() vs fallbacks
- Naming conventions for translation keys
- How translators will see these strings
- Runtime language switching behavior

4. Preset Integration Documentation

- this will be for contributors/ maintainers
- It covers topics like
- What presets are in iD
- How KBar maps presets → actions
- How to add a new preset-based command
- Performance considerations (don’t load everything eagerly)

This sections will bridge knowledge between Kbar <-> core editor

5. Context Awareness and Filtering Doc

- This will be for maintaines
- It will explain the following things:
- How actions decide when they are visible/enabled
- Selection-based filtering
- Mode-based filtering
- Geometry constraints
- Include examples like: node vs way vs relation or drawing mode vs browse mode

- This doc prevents future regressions.

6. Accessibility & Keyboard Interaction Doc

- This will be for maintainers/UX contributors
- It will contain
- Keyboard navigation model
- Focus handling
- ARIA roles used
- Screen reader expectations

(The implementation here will be partial)

7. User-Facing Documentation (Short & Sweet)

- This will be for mappers
