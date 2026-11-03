# knip: plugin-supplied entry drops a production entry

```sh
bunx knip@6.44.0 --production   # clean
bunx knip@6.44.1 --production   # Unused files (1): dep.ts
```

`main.ts!` is a production entry and imports `dep.ts`. The vite-plus task
`bun --watch main.ts` also yields `main.ts` as a (non-production) plugin
entry, which removes it from the `--production` graph.
