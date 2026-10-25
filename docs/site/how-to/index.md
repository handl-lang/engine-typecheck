# How-to guides

Task recipes. Each assumes sibling checkouts of this repo and of the platform
repos it patches.

## Run the checker from Rust

Call `check_module(&ast, &lang, options)`; the report's diagnostics carry spans, which is how `hnl typecheck` renders `file:line:col`.

```
let report = hnl_engine_typecheck::check_module(&ast, &lang, options);
if !report.is_clean() {
    for d in &report.diagnostics { eprintln!("{d}"); }
}
```

## Register a real engine

Publish the engine under the `typecheck` operation slot in the kit manifest; `hnl typecheck` then prefers it over the bootstrap.
