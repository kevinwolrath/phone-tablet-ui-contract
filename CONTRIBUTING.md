# Contributing

This repository is an experiment. Feedback does not need to accept the premise.

Useful contributions include:

- examples where scoped contract loading works poorly;
- simpler routing approaches;
- cases where ownership between page and component rules is unclear;
- techniques for detecting stale or contradictory instructions;
- examples of rules better enforced by code, linting or tests;
- mobile UI rules that are missing or too prescriptive;
- evidence that fewer, larger contracts work better.

When proposing a new rule, please identify the smallest owner that should contain it. Avoid copying the same rule into several contracts for emphasis.

When proposing a new contract, explain why an existing owner cannot reasonably contain the rule. The goal is not to grow a contract library; the goal is to give a coding agent the smallest relevant context for a change.
