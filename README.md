# Phone / Tablet UI Contract

This repository is an experiment, not a framework, standard, or finished answer.

Coding agents can drift towards heavy CRUD-style mobile screens: too many visible actions, equal visual weight for everything, and a button for every capability. My first response was to keep adding rules to one large UI contract. That eventually created another problem: small changes required reading a large rule book containing mostly irrelevant instructions.

The approach being tested here is scoped loading:

1. Keep global principles small.
2. Route a change by what is actually changing.
3. Read page rules only when page composition or hierarchy changes.
4. Read a component contract only when that component's behaviour or presentation changes.
5. Do not follow links between contracts as a reading list.
6. Prefer shared code or tests for stable mechanical rules.

Example:

`CHANGE_SCOPE.md` → `GLOBAL.md` + `PAGE.md` + `components/BUTTON.md`

A data-only change that leaves the interface unchanged may require no UI contract.

## Questions

I do not know whether this is the right level of granularity. I am interested in feedback on:

- whether scoped contract loading is a sensible way to control agent context;
- how granular contracts should become before routing itself becomes overhead;
- how to prevent stale or contradictory contracts;
- how precedence and intentional exceptions should work;
- how to detect documentation that no longer matches implementation;
- when a rule belongs in prose versus shared code, static checks or tests;
- better ways for an agent to discover the right instructions without reading everything;
- the point at which instruction context becomes part of the problem it was intended to solve.

Criticism and alternative approaches are welcome. Issues and pull requests are useful even when they argue that this structure is wrong. See `CONTRIBUTING.md` for the kinds of feedback this experiment is looking for.

## Current structure

- `contracts/INDEX.md` — ownership map and rule-placement test.
- `contracts/CHANGE_SCOPE.md` — lightweight routing.
- `contracts/GLOBAL.md` — genuinely global principles.
- `contracts/PAGE.md` — ordinary phone/tablet page composition and hierarchy.
- `contracts/components/BUTTON.md` — button rendering and compact behaviour.
- `contracts/components/ACTION_ROW.md` — responsive layout of legitimate actions.
- `contracts/components/MODAL.md` — modal/dialog/sheet presentation.
- `contracts/components/STATES.md` — empty, loading and error presentation.
- `contracts/components/DRAG_DROP.md` — direct manipulation and drag-container behaviour.

## Ownership boundary

The contracts are split by ownership rather than by screen. A page contract decides whether an action belongs on a page. A button contract decides how that action renders. An action-row contract decides how several legitimate actions lay out responsively. They should not copy each other's rules merely for emphasis.

## Routing examples

**Compact Back/Forward buttons:** route to page and button rules. Do not load modal, state or drag/drop rules simply because they exist.

**API mapping fix with no UI change:** no UI contract.

**Empty section inside a populated page:** route to page and state rules. Read button rules only if button behaviour also changes.

## Scope

The examples were anonymised from a real phone/tablet project. Product terminology, business logic, private links, tickets, credentials, assets and unrelated repository structure have been removed.

The repository is intentionally small. It exposes the idea and its rough edges rather than presenting a large production rule set.
