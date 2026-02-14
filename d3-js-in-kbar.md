# First some facts

- OSM iD uses D3.js heavily
- not only for charts but also as DOM manipulation layer, an event system and a data -> UI binding mechanism
- D3 in iD is not "charting library" , its more like low-level UI engine

# Where D3 is in iD already?

- SVG rendering
- selection and data joins
- event handeling(.on('click'), .on('keyydown'))
- Incremental DOM updates
- State-Driven UI updates

# Does KBar need D3?

- KBar dosent need D3 for correctness - but MAY benifit from it for consistency

- KBar is DOM-heavy, state-driven and not data-viz-heavy
- From pure engineering POV: Vanilla DOM / minimal helpe utils should be totally fine and D3 is optional

# Where D3 could make sense in KBar

1. Action List Rendering

KBar is basically:
actions[] → <li> elements

D3 excels at:

- enter / update / exit
- diffing lists efficiently '- keeping in DOM in sync with state

Example conceptual mapping:

- actions = data
- list items = selection
- active index = class binding

2. Keyboard-driven State Updates

when we do things like:

- arrow up/down
- search filter updates
- active index changes

D3 makes it easy to:

- rebind classes
- avoid manual DOM bookkeping
- keep logic declarative

3. Consistency with iD Codebase
