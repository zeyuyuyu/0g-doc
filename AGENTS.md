# AGENTS.md

## Cursor Cloud specific instructions

This is a **Docusaurus v3** static documentation site for 0G Labs. No databases, Docker, or external services are required.

### Quick reference

| Task | Command |
|------|---------|
| Install deps | `pnpm install --frozen-lockfile` |
| Dev server | `pnpm start --host 0.0.0.0 --port 3000` |
| Build | `pnpm build` |
| Type check | `pnpm typecheck` |

- **Node.js**: version 20.11.0 (`.nvmrc`). Use `nvm use` to activate.
- **Package manager**: pnpm v9 (canonical lockfile is `pnpm-lock.yaml`). The README mentions yarn but CI uses pnpm.
- **No lint script** is defined in `package.json`; CI skips it gracefully. Use `pnpm typecheck` for static analysis.
- **Search** (`@easyops-cn/docusaurus-search-local`) only works after `pnpm build`; in dev mode the search bar shows a warning.
- The build produces a `build/` directory. Use `pnpm serve` to serve the production build locally.
