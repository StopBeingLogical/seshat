# Seshat — Context Index
**Repo:** [Forgejo](http://git.damnaliens.us/bobby/seshat) · [GitHub](https://github.com/StopBeingLogical/seshat)

---

## Who this is for

You are an AI assistant working with Bobby. He is a systems thinker and builder who designs the architecture, intent, and direction of his projects — and uses AI as the implementation engine. He expects concise, direct responses with no filler. He works across multiple AI systems (Claude, Gemini, local models) and uses this repository to maintain consistent context across sessions.

**Start here:** Read `bootstrap.md` for the mandatory session startup sequence.

---

## Capability Check

**Do you have shell / filesystem access to `/Volumes/Shuttle/`?**
- **Yes** → use local paths defined in `bootstrap.md`. Faster, works offline.
- **No (read-only session)** → use raw GitHub URLs only. Do NOT attempt to modify local files. Provide code or instructions for the user to apply manually.

---

## How to use this

Fetch the raw URL of this file to get the domain map, then follow `bootstrap.md`. Each seed file is self-contained. Project-specific deep context lives in the project repo, not here.

**This index:** `https://raw.githubusercontent.com/StopBeingLogical/seshat/main/index.md`

---

## Domains

| File | Scope | Raw URL |
|:---|:---|:---|
| [bootstrap.md](bootstrap.md) | Mandatory session startup sequence + local path reference | [raw](https://raw.githubusercontent.com/StopBeingLogical/seshat/main/bootstrap.md) |
| [current.md](current.md) | Last known session state — read before asking what to work on | [raw](https://raw.githubusercontent.com/StopBeingLogical/seshat/main/current.md) |
| [preferences.md](preferences.md) | Collaboration style, working preferences, security guardrails (living document) | [raw](https://raw.githubusercontent.com/StopBeingLogical/seshat/main/preferences.md) |
| [glossary.md](glossary.md) | Term → role → physical location map for all named assets | [raw](https://raw.githubusercontent.com/StopBeingLogical/seshat/main/glossary.md) |
| [naming.md](naming.md) | Naming conventions and all active asset names | [raw](https://raw.githubusercontent.com/StopBeingLogical/seshat/main/naming.md) |
| [hardware.md](hardware.md) | Physical nodes — specs, roles, status | [raw](https://raw.githubusercontent.com/StopBeingLogical/seshat/main/hardware.md) |
| [projects.md](projects.md) | Active software projects and infrastructure | [raw](https://raw.githubusercontent.com/StopBeingLogical/seshat/main/projects.md) |
| [infrastructure.md](infrastructure.md) | Source of truth locations, replication topology, access patterns | [raw](https://raw.githubusercontent.com/StopBeingLogical/seshat/main/infrastructure.md) |
| [templates/SESSION_SEED.md](templates/SESSION_SEED.md) | Template for per-project SESSION_SEED files | [raw](https://raw.githubusercontent.com/StopBeingLogical/seshat/main/templates/SESSION_SEED.md) |

---

## Editing this repo

Auth credentials and API instructions are in a local file not tracked by git:
`/Volumes/Shuttle/projects/seshat/.auth`

Read that file to get the GitHub token and API pattern needed to create or update seed files.

---

## Notes for models
- `bootstrap.md` defines the mandatory startup sequence — always follow it
- `current.md` tells you what was last worked on — read it before asking the user for a status update
- `preferences.md` and `naming.md` always apply regardless of task domain
- Project deep context lives in the project repo. `projects.md` links to those seeds.
