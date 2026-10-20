# Action row contract

Read this when changing shared action-row layout or responsive behaviour.

The row lays out actions its owner has already decided belong there. It does not decide which actions belong on a screen.

- Wrap before labels clip or truncate.
- Put the primary action last and align the row consistently.
- Preserve touch targets.
- Buttons explicitly marked as compactable may become icon-only under constrained width; other actions keep their labels.
- Do not hide arbitrary actions merely to make an overcrowded row fit. Overcrowding is an action-hierarchy problem for the owning page.
- Avoid per-screen breakpoint logic where the shared row can own the responsive behaviour.
