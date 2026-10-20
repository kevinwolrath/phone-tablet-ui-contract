# Contract index

Start with `CHANGE_SCOPE.md`. It selects the smallest relevant instruction set for a change. Do not read every contract first, and do not treat references between contracts as a recursive reading list.

## Owners

| Contract | Responsibility |
| --- | --- |
| `GLOBAL.md` | Principles that apply across the interface |
| `PAGE.md` | Ordinary page composition, action hierarchy and information hierarchy |
| `components/BUTTON.md` | Shared button rendering and compact behaviour |
| `components/ACTION_ROW.md` | Responsive layout of legitimate actions |
| `components/MODAL.md` | Overlay presentation, dismissal and scrolling |
| `components/STATES.md` | Empty, loading, error and notice presentation |
| `components/DRAG_DROP.md` | Shared direct-manipulation and drag-container behaviour |

Each rule should have one owner. A reference to another contract identifies neighbouring ownership; it does not copy that ownership.

## Placement test

Before adding prose, ask whether shared code or an automated check can reliably enforce the rule. If not, place ordinary screen composition in `PAGE.md`, reusable interaction behaviour in its component contract, and only genuinely universal principles in `GLOBAL.md`.

Keep intentional exceptions explicit and local instead of weakening a shared rule for every screen.

The goal is not to grow a contract library. The goal is to give an agent enough instruction for the current change without loading unrelated rules.
