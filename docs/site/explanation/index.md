# Explanation

## Why this crate exists

Typechecking must work before a language has registered a checker — otherwise
`hnl typecheck` on a fresh kit produces nothing at all. The bootstrap is
deliberately shallow (structure and obvious mismatches) and exists to be
*replaced*: dependent types, instance search and handler typing live in the NBE
engine.

## Where it sits

This crate belongs to the `engine-*` family. Plugins, kits and hosts reach it
through the kit's operation slot, so the engine can be swapped without touching a
language definition.

See the [reference](/engine-typecheck/reference/) for the API and the
[how-to guides](/engine-typecheck/how-to/) for tasks.
