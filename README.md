# engine-typecheck

`hnl-engine-typecheck` — the abstraction crate for the typecheck operation.

An `engine-*` crate: the trait/type surface for typechecking that concrete
engines (`engine-typecheck-nbe`) implement.

## Development

```bash
cargo xtask gate        # fmt --check → clippy -D warnings → test → doc
```

`cargo xtask` wraps the repo's `xtask/` crate (`fmt`, `clippy`, `test`, `doc`,
`check`, `gate`); `ci.sh` is the gate entry. Deps resolve from git, so no
sibling checkouts are needed; a plain clone test-runs as-is.

## License

MIT.

## Documentation

<https://handl-lang.github.io/docs/engine-typecheck/>
