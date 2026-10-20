# Drag and drop contract

Read this when changing drag/drop or reordering behaviour. The owning page decides what the source and target collections mean; this contract owns the interaction pattern.

## Direct manipulation

Use one shared drag implementation rather than creating page-specific gesture systems. Keep movement responsive and avoid driving every movement frame through application state when the UI framework provides a dedicated gesture/animation path.

Drag and ordinary scrolling must have a deliberate recognition strategy so they do not randomly compete for the same gesture.

Tap and accessibility actions must remain available beside drag behaviour, and completing a drag must not accidentally trigger a tap.

## Reordering

Drag/drop or a drag handle can be the normal visible reorder mechanism for directly manipulable content. Provide an accessible alternative for people who cannot perform the gesture, without turning duplicate Move Up / Move Down controls into the dominant interface.

## Core layout rule

A drag source or drop target should not become its own nested scroll region merely because it contains more items.

- Let sources and targets grow with their content.
- Wrap items into additional rows where appropriate.
- Avoid arbitrary fixed heights that clip draggable content.
- Avoid putting the active drag field inside its own mini scrolling list.
- Let the owning page, workspace or sheet handle overflow.
- Keep an empty drop target large enough to understand and use without reserving a large blank area.

The same principle applies across phone, portrait tablet and landscape tablet layouts; larger layouts may place source and target side by side.

For datasets too large for direct manipulation, browse or filter outside the active drag field rather than turning the drag field into a scrollable mini-list.
