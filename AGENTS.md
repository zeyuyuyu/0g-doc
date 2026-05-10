# AGENTS.md

## Cursor Cloud specific instructions

This is a **Docusaurus v3** static documentation site for 0G Labs (docs.0g.ai). There is only one service — the Docusaurus dev server.

### Quick reference

| Task | Command |
|------|---------|
| Install deps | `pnpm install --frozen-lockfile` |
| Dev server | `pnpm start` (port 3000) |
| Build | `pnpm build` |
| Typecheck | `pnpm typecheck` |
| Serve prod build | `pnpm serve` |

### Non-obvious notes

- **Node version**: Must use Node.js 20.11.0 (specified in `.nvmrc`). Run `nvm use` to activate.
- **Package manager**: pnpm v9 (lockfile is `pnpm-lock.yaml`). CI uses `--frozen-lockfile`.
- **No lint script**: The `package.json` does not define a `lint` script. CI checks for it and skips if absent.
- **No automated tests**: There are no unit/integration test suites. Validation is done via `pnpm typecheck` and `pnpm build`.
- **Broken anchor warning**: Build produces a warning about a broken anchor (`inference#sdk`). This is a pre-existing issue and not a build failure.
- **`onBrokenLinks: 'throw'`**: The Docusaurus config throws on broken links during build, so any new broken links will fail the build.
- **No external services required**: No databases, Docker, or APIs needed for local development.
