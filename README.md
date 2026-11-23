# tool-typecheck

`hnl-tool-typecheck` — the abstraction crate for the typecheck operation.

A `tool-*` crate: the trait/type surface for typechecking that concrete
engines (`tool-typecheck-nbe`) implement.

## Development

```bash
cargo run --manifest-path xtask/Cargo.toml -- gate   # fmt → clippy → test → doc
```

The repo's `xtask/` crate provides the gate tasks (`fmt`, `clippy`, `test`, `doc`,
`check`, `gate`); `ci.sh` is the gate entry. Deps resolve from git, so no
sibling checkouts are needed; a plain clone test-runs as-is.

## License

MIT.

## Documentation

<https://handl-lang.github.io/docs/tool-typecheck/>
