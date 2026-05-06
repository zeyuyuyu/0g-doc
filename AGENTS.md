# AGENTS.md

## Cursor Cloud specific instructions

This is a Docusaurus 3.x static documentation site (0G Labs docs). There is no backend, database, or Docker infrastructure.

### Quick reference

| Action | Command |
|--------|---------|
| Install deps | `pnpm install` |
| Dev server | `pnpm start` (port 3000) |
| Build | `pnpm build` |
| Type check | `pnpm typecheck` |

### Environment notes

- **Node.js 20.11.0** is required (see `.nvmrc`). Load via: `export NVM_DIR="$HOME/.nvm" && source "$NVM_DIR/nvm.sh" && nvm use 20.11.0`
- **pnpm** is the package manager (lockfile: `pnpm-lock.yaml`). The README mentions `yarn` but the actual lockfile is pnpm.
- The `pnpm install` step emits a warning about ignored build scripts for `core-js`; this is harmless and can be ignored.
- `pnpm build` produces a warning about a broken anchor (`inference#sdk`); this is a pre-existing content issue, not a build failure.
- No lint command is configured in `package.json`. Use `pnpm typecheck` (runs `tsc`) as the primary static analysis check.
- The dev server supports hot-reload for content and component changes.
