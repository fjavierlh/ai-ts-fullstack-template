# AGENTS.md

Bootstrap template for a TypeScript fullstack app. There is **no application code, test runner, linter, formatter, CI, or source tree yet** — only tooling is initialized. Do not assume scripts or commands that aren't listed here.

## Toolchain

- **Node 24** (`.nvmrc`, and enforced by `devEngines` in `package.json`: `>=24 <25`, `onFail: error`).
- **pnpm 12.8.1** is the package manager (`packageManager` + `devEngines`). It is not assumed to be on `PATH`: `onFail: download` means pnpm auto-downloads the pinned version.
- **ESM only** — `"type": "module"`; use `import`/`export`, not `require`.

## Commands

- Install: `pnpm install`
- `package.json` `test` is a placeholder that exits 1. There is no real test/lint/typecheck/build setup. When adding one, add the scripts at the same time.
- Run a single package/filtered command only after a workspace is introduced; there are no workspace globs yet.

## Workflow: OpenSpec (spec-driven)

For any non-trivial change, use the repo's OpenSpec flow instead of ad-hoc edits:

- `/opsx-propose` → `/opsx-apply` → `/opsx-sync` → `/opsx-archive`
- Active changes live in `openspec/changes/`; archived changes move to `openspec/changes/archive/`; baseline capabilities live in `openspec/specs/`.
- Record team conventions (proposal limits, task sizing, output language, platform constraints) in `openspec/config.yaml`, not in this file.

## OpenCode config

- Repo-local commands: `.opencode/commands/opsx-*.md`
- Repo-local skills: `.opencode/skills/openspec-*` — invoke via the skill tool rather than reading them by hand.

## Intended direction

TypeScript fullstack. When scaffolding, prefer pnpm workspaces with clear boundaries (e.g. `apps/web`, `apps/api`, `packages/shared`). Do not commit to specific frameworks ahead of an OpenSpec proposal that chooses them.
