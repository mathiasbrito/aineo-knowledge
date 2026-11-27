# aineo Knowledge Vault

The project's shared knowledge base. It is a repository of its own, [aineo-knowledge](https://github.com/mathiasbrito/aineo-knowledge), apart from the plugin's [aineo](https://github.com/mathiasbrito/aineo) since 2026-11-27 so that plugin installs do not carry it, and is read and written by everyone working on aineo — people and agents alike. Clone it into the git-ignored `knowledge-vault/` at the root of your aineo checkout: `git clone https://github.com/mathiasbrito/aineo-knowledge.git knowledge-vault`.

**It is an [Obsidian](https://obsidian.md) vault.** Open the `knowledge-vault/` folder as a vault and the `[[wikilinks]]` resolve. It is also plain Markdown, so it reads fine in any editor or on a code host.

## Start here

| If you are… | Read |
|---|---|
| New to the project | `Projects/aineo.md` — architecture, decisions, gotchas |
| About to build a feature | `Planning/` for an active plan · the specs for what it must do |
| Running or joining an orchestration wave | `Implementation/Waves/` — the plans and their status · `Skills/Orchestrate.md` |
| Wondering *why* something is the way it is | `Planning/` and the `Sessions/` they link |
| Touching something that changes upstream | `Tracking/Tracking.md` — and check the verification dates |
| Finishing a piece of work | Write a note in `Sessions/`, update `Projects/aineo.md` |

## The one rule that matters most

Some contributors keep a personal Obsidian vault and have global instructions to record work there. **Inside this repository, that does not apply.** aineo knowledge goes here and only here — a fact kept in two vaults diverges, and then neither can be trusted. The full statement is in `CLAUDE.md` alongside this file.

## What is binding and what is not

The constitution and the specs, once the project has them, are **binding** — they govern the code. This vault is **context**: why we chose what we chose, what we rejected, and what bit us. If the vault contradicts a spec, the spec wins and the vault needs fixing. One exception, until specs exist: the plan the root `CLAUDE.md` names as the spec is binding too — its decision and component rows change only with the user's agreement.
