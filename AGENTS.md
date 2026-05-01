# AGENTS.md

## Cursor Cloud specific instructions

This is a **Docusaurus 3.8** static documentation site (0G Labs docs). There are no backend services, databases, or APIs.

### Quick reference

| Action | Command |
|--------|---------|
| Install deps | `pnpm install --frozen-lockfile` |
| Dev server | `pnpm start` (default port 3000) |
| Production build | `pnpm build` |
| Type check | `npx tsc --noEmit` |
| Serve build | `pnpm serve` |

### Gotchas

- **Package manager**: CI uses **pnpm v9**. The README mentions `yarn`, but the lockfile is `pnpm-lock.yaml` — always use pnpm.
- **Node version**: `.nvmrc` specifies **20.11.0**. After sourcing nvm (`source ~/.bashrc` or `source $HOME/.nvm/nvm.sh`), run `nvm use` in the workspace to pick up `.nvmrc`.
- **No lint script**: `package.json` has no `lint` script; CI skips it. Type checking (`npx tsc --noEmit`) is the primary static analysis step.
- **Search index**: The local search plugin (`@easyops-cn/docusaurus-search-local`) only works after `pnpm build`; in dev mode (`pnpm start`) search shows "index not available".
- **Broken anchor warning**: The build emits a non-fatal warning about a broken anchor (`#sdk` on the compute-network overview page). This is a known content issue, not a build failure.
