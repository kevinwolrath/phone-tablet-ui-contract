# Phone / Tablet UI Contract

This repository is an experiment, not a framework or a finished answer.

I have been struggling to get coding agents to consistently produce intuitive mobile interfaces. Left to themselves they can drift towards heavy CRUD-style screens: too many visible actions, too much equal-weight information, and a button for every capability.

My first response was to keep adding rules to one large UI contract. That helped for a while, but the contract became part of the problem. A small change could require the agent to read a large rule book containing mostly irrelevant instructions.

The approach being tested here is different:

1. Start with a very small set of global principles.
2. Route the change by what is actually being changed.
3. Load the page contract only when page composition or hierarchy changes.
4. Load a component contract only when that component's behaviour or presentation changes.
5. Do not treat links between contracts as an instruction to read everything.

For example, changing compact button behaviour on an ordinary page might require:

`CHANGE_SCOPE.md` → `GLOBAL.md` + `PAGE.md` + `components/BUTTON.md`

Changing data behaviour without changing the UI may require no UI contract at all.

## What I am trying to find out

I do not know yet whether this is the right level of contract granularity.

Questions I am interested in:

- Has anyone else had coding agents drift towards desktop/CRUD-style mobile UI?
- Is scoped contract loading a sensible way to control context?
- How do you stop small contracts becoming stale or contradictory?
- How do you decide when a rule belongs in a contract versus code or tests?
- Is there a better way to make the agent find the right instructions without making it read everything?

If you have tried something similar, or think this approach is wrong, I would be interested in the feedback.

## Contents

- `contracts/CHANGE_SCOPE.md` — lightweight routing: decide what needs to be read.
- `contracts/GLOBAL.md` — principles that genuinely apply everywhere.
- `contracts/PAGE.md` — ordinary phone/tablet page composition and hierarchy.
- `contracts/components/BUTTON.md` — button rendering and compact behaviour.

The examples have been anonymised from a real mobile project. Product-specific terminology, repository paths and business rules have deliberately been removed.
