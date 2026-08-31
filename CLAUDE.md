# CLAUDE.md — FOMO System

Guidance for Claude Code (and any agent) working in this repository.

## What this project is

**FOMO** — File Organisation, Management & Optimisation. A practical file-naming and
directory-structure framework balancing human readability with machine processing.

Read first, in order:

1. `docs/fomo-project-onboarding.md` — one-page brief
2. `docs/fomo-project-charter.md` — vision, scope, principles
3. `docs/fomo-project-setup-plan.md` — implementation detail
4. `docs/fomo-project-checklist.md` — current state and change log

Always reference the **highest `v##`** of any versioned document.

## Source of truth and sync workflow

Three copies of this project exist. They are not equal.

| Copy | Path / location | Role |
|---|---|---|
| **Local folder** | `~/Projects/dev/00-fomo-system/` | **Source of truth.** All work happens here. |
| **GitHub repo** | `github.com/exlennis/fomof` (`origin/main`) | Backup mirror and relay. Never edited directly. |
| **claude.ai project knowledge** | "FOMO System" project | Synced snapshot, read-only downstream. |

**Conflict rule: the local folder always wins.** If GitHub or the claude.ai project
knowledge disagrees with local, local is correct and the others are stale — re-sync
them from local, never the other way.

**Normal flow:**

1. Edit files locally in this folder.
2. `git add` + `git commit` locally (see Git conventions below).
3. `git push` to `origin/main` — **only when the user explicitly asks.**
4. After a push, the user clicks **Sync now** on the GitHub connector in the
   claude.ai "FOMO System" project to refresh the snapshot.

Claude Code does not have API access to the claude.ai project knowledge or a way to
push on its own initiative — steps 3 and 4 are user-triggered.

## Git conventions

- Branch: `main`. Do not create branches unless asked.
- **Never `git push` unless the user explicitly requests it in that session.**
  Committing locally is fine when asked; pushing is a separate, explicit step.
- Commit messages: conventional-ish prefix, imperative, lower case —
  `docs: formalise local-as-source-of-truth workflow`, `feat: add rename script`,
  `fix: correct vocabulary term`.
- Do not commit `.DS_Store` or anything already in `.gitignore`.

## Documentation conventions

- Filename pattern: `topic-DOCUMENT-TYPE-v##.md` (e.g. `fomo-project-charter-v04.md`).
- Primary naming convention across the system: **kebab-case**
  (e.g. `project-brief-20250410-v01.pdf`).
- Significant changes create a new `v##` and a version-history bump; minor changes
  go in the document's own change log or the maintenance log.
- Controlled vocabulary lives in `docs/02-standards/fomo-controlled-VOCABULARY-v##.md` —
  use its terms.
- Australian English, AGSM style (`-ise`, `organisation`, `optimise`).

## Repository layout

```
docs/
  01-planning/       research and analysis inputs
  02-standards/      naming + directory + vocabulary standards
  03-analysis/       DAM / taxonomy analysis
  04-implementation/ scripts, automation, rollout
  05-maintenance/    logs, checks
  archive/           superseded material
  fomo-project-*.md  charter, checklist, setup plan, onboarding, directory map
tests/               (gitignored)
```

## Known loose ends

- Four unfiled `.md` notes sit at the repo root (TorBox/Jellyfin, Hermes workspace,
  system-instructions draft, ChatGPT settings). Leave them in place — the user will
  file or remove them. Do not commit or move them without being asked.
- The `v04` charter / `v05` checklist / `v03` setup-plan revisions produced in a
  separate claude.ai session may not be imported yet. If asked to work with them,
  confirm which version is current on disk first.
