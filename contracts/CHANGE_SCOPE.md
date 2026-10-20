# Contract selection by change scope

Route a UI change here first. Read only the contracts relevant to the thing being changed.

## Page composition

When changing what an ordinary page shows, its action hierarchy, information hierarchy or responsive composition, read:

- `GLOBAL.md`
- `PAGE.md`

A behaviour or data-only change that does not alter what the user sees or does needs no UI contract.

## Shared components

Load a component contract only when changing that component's behaviour or presentation. Simply using an existing component does not require reading its contract.

| Change | Contract |
| --- | --- |
| Button rendering, variants or compact behaviour | `components/BUTTON.md` |
| Layout of an action row | `components/ACTION_ROW.md` |
| Modal, dialog, viewer or sheet presentation | `components/MODAL.md` |
| Empty, loading, error or notice presentation | `components/STATES.md` |
| Drag/drop or reordering | `components/DRAG_DROP.md` |
| Ordinary page composition or hierarchy | `PAGE.md` |

## Ownership and precedence

Each rule should have one owner. A component contract owns that component's shared behaviour; the page contract owns ordinary page composition and action hierarchy; global rules are reserved for principles that genuinely apply everywhere.

If a specialised interface deliberately needs an exception, make the exception explicit rather than silently duplicating or contradicting the shared rule.

Links between contracts identify neighbouring ownership. They are not an instruction to recursively load every linked document.

## Stop condition

If a small change appears to require several unrelated contract families, stop and check whether the change is actually several changes, ownership is wrong, or a repeated rule belongs in shared code or tests. Do not solve ambiguity by loading everything.

## Examples

Changing compact button behaviour on an ordinary page:

`CHANGE_SCOPE.md` → `GLOBAL.md` + `PAGE.md` + `components/BUTTON.md`

Changing only data loading on that page:

No UI contract required.

Changing an empty section inside an otherwise populated ordinary page:

`CHANGE_SCOPE.md` → `GLOBAL.md` + `PAGE.md` + `components/STATES.md`

Changing shared drag behaviour without changing page composition:

`CHANGE_SCOPE.md` → `components/DRAG_DROP.md`
