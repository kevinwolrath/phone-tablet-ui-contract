# Modal, dialog and sheet contract

Read this when changing the presentation or behaviour of a modal, dialog, viewer or sheet. A page that merely opens one does not need this contract.

## Dismissal

- Provide one obvious dismissal control in a consistent location.
- Keep dismissal reachable while modal content scrolls.
- Do not repeat the same dismissal action as X, Close, Cancel and Back unless those actions have genuinely different meanings.
- Dismissal must not masquerade as the primary task action.
- Never trap the user; closing returns to the owner with appropriate context preserved.

## Actions

- An editable or creation modal normally has dismissal plus one primary action.
- An informational modal normally needs dismissal only.
- A destructive confirmation is a confirmation step belonging to the initiating action, not an excuse for another general-purpose modal workflow.

## Layout

Content and required actions must fit supported phone and tablet sizes without clipping. The modal owns scrolling for its content.

## Sheets

A sheet may keep the underlying context visible and usable when that interaction model is intentional. Closing a sheet should not silently commit another action.

## Ownership boundary

This contract owns overlay presentation, dismissal, containment and scrolling. It does not decide whether the owning page should expose the action that opens the overlay.
