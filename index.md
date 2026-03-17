# Seshat — Context Index
**Repo:** [Forgejo](http://git.damnaliens.us/bobby/seshat) · [GitHub](https://github.com/StopBeingLogical/seshat)

---

## Who this is for

You are an AI assistant working with Bobby. He is a systems thinker and builder who designs the architecture, intent, and direction of his projects — and uses AI as the implementation engine. He expects concise, direct responses with no filler. He works across multiple AI systems (Claude, Gemini, local models) and uses this repository to maintain consistent context across sessions. Start by reading `preferences.md` and `naming.md`, then fetch any domain-specific files relevant to the task at hand. If working on a specific project, follow the link in `projects.md` to the project repo for deep technical context.

---

## How to use this

Fetch the raw URL of this file to get the domain map, then fetch only the seeds relevant to your task. Each file is self-contained. Project-specific deep context lives in the project repo, not here.

**This index:** `https://raw.githubusercontent.com/StopBeingLogical/seshat/main/index.md`

---

## Domains

| File | Scope | Raw URL |
|:---|:---|:---|
| [naming.md](naming.md) | Naming conventions and all active asset names | [raw](https://raw.githubusercontent.com/StopBeingLogical/seshat/main/naming.md) |
| [hardware.md](hardware.md) | Physical nodes — specs, roles, status | [raw](https://raw.githubusercontent.com/StopBeingLogical/seshat/main/hardware.md) |
| [projects.md](projects.md) | Active software projects and infrastructure | [raw](https://raw.githubusercontent.com/StopBeingLogical/seshat/main/projects.md) |
| [preferences.md](preferences.md) | Collaboration style and working preferences (living document) | [raw](https://raw.githubusercontent.com/StopBeingLogical/seshat/main/preferences.md) |

---

## Editing this repo

Auth credentials and API instructions are in a local file not tracked by git:
`/Volumes/Shuttle/projects/seshat/.auth`

Read that file to get the GitHub token and API pattern needed to create or update seed files.

---

## Notes for models
- Project deep context (architecture, stack, deployment, known issues) lives in the project repo, not here. `projects.md` links to those seeds.
- `preferences.md` always applies regardless of task domain.
- `naming.md` always applies when creating or referring to any named asset.
