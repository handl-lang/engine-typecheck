# Agent guide — tool-typecheck

`hnl-tool-typecheck` — the abstraction crate for the typecheck
operation: the trait/type surface for typechecking that concrete
engines (`tool-typecheck-nbe`, `tool-typecheck-handl`) implement.
`publish = false` (git-install only). Rust 2024.

## Layout

| path | role |
| --- | --- |
| `src/lib.rs` | crate docs + `TypecheckEngine` trait surface |
| `src/bootstrap.rs` | bootstrap/self-host typecheck plumbing |
| `tests/bootstrap.rs` | bootstrap tests |
| `docs/` | operation doc |
| `xtask/`, `workflows/gate.yaml`, `bupha.toml`, `.cargo/` | vendored repo gate + CI wiring |

## Contract

- Deps resolve from git — `handl-language` → `handl-lang/kernel`,
  `handl-platform`/`handl-plugin-ext-diag` (`lang-span` feature) →
  `handl-lang/host`, `hnl-tool-lex`/`hnl-tool-parse` → sibling
  `tool-*` repos, all `branch = "main"`.
- Abstraction only: type rules live in `lang.types` data and the
  concrete engines — this repo owns the `TypecheckEngine` contract.

## Verification

```bash
cargo xtask gate   # fmt --check → clippy -D warnings → test → doc
```


<!-- myco:agent-awareness -->

## Agent awareness

- Session start / any work discussion: run `myco status --prompt`
  before proposing next steps — know the board first.
- User describes new work → offer to capture it (`myco todo add`,
  `issue new`, `proposal new`). Don't wait to be asked.
- Picking up a task: `myco resume <ID>` is the briefing.
- Wrapping up: `myco handoff <ID>` anything resumable; keep statuses
  honest (claimed → in-progress → blocked/done).

<!-- /myco:agent-awareness -->
