# Contributing

**Creative Quality Of Life** (`qolminecraft`, store slug `creative-qol`) is a **closed-source** project.

## Public vs private

- **Public docs** (README, changelog, license, icon): [QoL-minecraft-public](https://github.com/alanjmrt94/QoL-minecraft-public)
- **Development source** lives in a **private** GitHub repo. It is not open for unsolicited public pull requests.
- Invited collaborators work on the **private** repo (branches / internal PRs as agreed with the owner).
- In the private clone, public-facing docs are edited at the repo root and synced into the `public-docs/` submodule. Do not `git push` the private tree to the public remote.

## For invited collaborators

1. Read the Spanish guides under [`docs/`](docs/README.md) before changing features, items, models, or menus.
2. Prefer small, focused commits (English Conventional Commits: `feat`, `fix`, `docs`, …).
3. Do not commit secrets: `scripts/.release.local`, keystores, `.env`, tokens, or real Discord webhooks.
4. Store / Discord publishing is discretionary for the team. Scripts may be visible, but uploads are gated (`QOL_ALLOW_STORE_PUBLISH`, etc.). Prefer not to publish without agreement unless the owner has given you that latitude.
5. **Pre-commit (Husky):** run `npm install` once after clone. Each commit runs mixin signature checks then Spotless (`scripts/pre-commit.sh`). Bypass only if needed: `QOL_SKIP_HOOKS=1`. See [`.cursor/TESTING.md`](.cursor/TESTING.md).

## Community

- Chat: [discord.gg/CcUNTJjPD](https://discord.gg/CcUNTJjPD)
- Issues on the **public** docs repo are welcome for README / changelog / license feedback.
