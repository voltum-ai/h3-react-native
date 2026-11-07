# AGENTS.md

Third-party fork of Uber's h3-js (`upstream` remote), a pure-JavaScript build of the H3 hexagonal geo-grid library, published as `h3-react-native`. Local to this fork: a committed `dist/` (commit ddea71e) and two fork-only commits on top of upstream; everything else is upstream code, so keep changes minimal and upstream-shaped.

## Map
- `lib/` source (`lib/h3core.js` is the API); `test/` tape specs; `benchmark/` benchmarks
- `build/`, `scripts/` bindings, emscripten and doc/type generation; `out/` emscripten output
- `dist/` built bundles and types (committed here, `main` points into it); `doc-files/` README templates
- `H3_VERSION` pins the bundled H3 C core; `README.md` is generated (`build-docs`), edit `doc-files/`

## Verify
Package manager is yarn. Scripts are in `package.json`:
- `yarn lint` (tsc + eslint), `yarn test-fast`, `yarn test-legacy`; `yarn test` runs lint and both
- `yarn dist` rebuilds `dist/` and needs docker (emscripten); run it after any `lib/` change, then commit `dist/`
- CI: `.github/workflows/test.yml` (GitHub, not GitLab)

## Where to look
`CONTRIBUTING.md` (100% coverage, changelog entry), `RELEASE.md`, `CHANGELOG.md`. The repo has no docs folder, no Voltum knowledge folder and no vault page.

This AGENTS.md may be improved by any session that has evidence.
