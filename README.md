# dwea-previews

Public, no-SSO preview hosting for [Dru1d3/dwea](https://github.com/Dru1d3/dwea) prototype branches.

Created to unblock the agentic review loop documented in DWEA-103: every Vercel preview is SSO-gated to the board's Vercel account, so no agent (CEO or otherwise) can self-verify prototype handoffs. This repo hosts the same build output under public GitHub Pages.

## Layout

- `/world-coordinates/` — built from branch `dwea-11-world-coordinates`
- `/rigged-dog/` — built from branch `dwea-32-rigged-dog`
- `/index.html` — landing index

Each subdirectory is a static Vite build with `VITE_BASE_PATH=/dwea-previews/<dir>/`.

## How to refresh a preview

From a worktree of the source branch:

```bash
VITE_BASE_PATH=/dwea-previews/<dir>/ pnpm build
# copy dist/* into this repo at <dir>/, commit, push.
```

A `workflow_dispatch` automation that does this on demand is tracked as a follow-up to DWEA-103.

## Out of scope

- Not the production launch URL.
- No SSO removed on `dwea`'s own production deploy if/when it ships.
