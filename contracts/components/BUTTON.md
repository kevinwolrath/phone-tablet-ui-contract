# Button contract

Read this when changing how a shared button renders or behaves. Whether an action belongs on a screen is the page contract's decision, not this contract's.

## Shared controls and vocabulary

- Use the application's shared button controls rather than inventing local button styles.
- Equivalent operations should use consistent short labels and icons.
- Labelled actions normally show icon and label.
- Labels should not clip or truncate merely to fit more actions onto one row.

## Action importance

Use the shared variants consistently so that the action progressing the primary task is distinguishable from secondary, cancel/back and destructive actions.

Do not use local colours to invent new action meanings.

## Compact icon-only behaviour

A button may become icon-only on compact layouts when the icon is unambiguous.

- Keep an accessible name when the visible label is hidden.
- Do not shrink the touch target simply to fit more actions.
- Wider layouts retain the useful text label.
- Compact behaviour is a presentation change, not permission to add more actions to the page.

## Ownership boundary

The button contract owns how a button renders and behaves. It does not decide whether an action should be visible, how many actions a page should contain, or the workflow behind an action.
