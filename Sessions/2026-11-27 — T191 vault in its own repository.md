# 2026-11-27 — T191: the vault moves to aineo-knowledge

**Author:** the user, with Claude (orchestrator and implementer agent)
**Branch:** `ai/t191-vault-in-its-own-repository` (aineo); `knowledge/t191-vault-in-its-own-repository` (this repository)

## Links
Decision: the user, 2026-11-27: "we need to move the vault out of the repo, why, when someone installs the plugin, most of the size is comming from the knowledge-valt", then "ok move on..." accepting the design below. Code repository: https://github.com/mathiasbrito/aineo

## What was done and why
The vault was 8.7 MB of aineo's 19 MB tree (46%), and every plugin install carried it.
- **Seeding:** this repository was seeded with the vault's whole history by `git subtree split --prefix=knowledge-vault` of aineo's dev at 761b1fe6. That gave 665 commits, and the split's tree equals `knowledge-vault/` there.
- **`--no-verify`:** the first push to `main` used `git push --no-verify`, run by the user. A pull request needs a base, and an empty repository has none. That was the only push to `main` outside a pull request.
- **Protection:** `main` is now protected as aineo's is: pull requests only, linear history, admins enforced, no force pushes or deletions.
- **aineo's side** (`ai/t191-vault-in-its-own-repository`):
  - `knowledge-vault/` is removed and git-ignored. Contributors clone this repository into it, so every `knowledge-vault/...` path in the rules still reads the same.
  - CLAUDE.md, README, the agent charters and the orchestrate skill now say:
    - the vault is its own repository, under the same never-commit-to-main rule;
    - a dispatched agent hands its session note back and marks no task line;
    - the orchestrator commits notes in batches here, on a `knowledge/` branch, through a PR into `main`;
    - agents in worktrees read the vault at the main checkout.
- **Ignore rules:** this repository's `.gitignore` takes over the Obsidian rules aineo's held for `knowledge-vault/`.

## Decisions
- **Rejected options:**
  - an orphan branch in aineo, which full clones still fetch;
  - a submodule, which lazy.nvim fetches by default;
  - `export-ignore`, which only affects archives;
  - a rewrite of aineo's history, which would break every v0.2.x tag. lazy.nvim's partial clone and the other managers' shallow clones fetch only the current tree, so taking the vault out of it is the whole saving.
- **Notes:** session notes come back in hand-backs and are committed in batches, not as a second PR per task.

## Open threads
The orchestrate skill still words its plan, claim and knowledge-pass steps as `knowledge/` PRs merged to aineo's `dev`. One paragraph says they live here now, but not every sentence is reworded.

## Commits
Recorded after the merge.
