# engine-typecheck

The typecheck contract (`TypecheckEngine`) plus the bootstrap checker.

## What it is

The **abstraction crate** for the typecheck operation (ADR-0054 §3):
`Typecheck`, `TypecheckRequest`, `TypecheckResult`/`TypecheckReport`,
`TypecheckEngine`, and the `check_module` entry point `hnl typecheck` calls.

Unlike the other abstraction crates this one *does* ship a checker — a small
**bootstrap** implementation used when no engine is registered. The production
engine is `engine-typecheck-nbe`, registered by the canonical kit as `"nbe"`.

## Modules
- `bootstrap` — the bootstrap checker: structure + obvious type errors only


## Start here

- **Reference** — [public API](/engine-typecheck/reference/)
- **How-to** — [task recipes](/engine-typecheck/how-to/)
- **Explanation** — [design and rationale](/engine-typecheck/explanation/)

No tutorials: this repo is a building block used from Rust. End-to-end
walkthroughs live with the product that composes it — see the
[Handl platform](/handl/).
