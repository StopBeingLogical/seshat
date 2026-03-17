# Bootstrap Protocol
**Last Updated:** 2026-03-17
**Scope:** Mandatory step-zero for all models starting a new session. Follow this before doing anything else.

---

## Step 0 — Determine your capabilities

**Do you have shell/filesystem access?**
- Yes → use local paths under `/Volumes/Shuttle/` where available. Faster and works offline.
- No (web-only) → use the raw GitHub URLs defined in `index.md` for all file fetches.

---

## Standard Bootstrap Sequence

1. **Fetch `preferences.md`** — always applies, regardless of task
   `https://raw.githubusercontent.com/StopBeingLogical/seshat/main/preferences.md`

2. **Fetch `naming.md`** — always applies when creating or referring to any named asset
   `https://raw.githubusercontent.com/StopBeingLogical/seshat/main/naming.md`

3. **Fetch `current.md`** — read the last known session state before asking the user what to work on
   `https://raw.githubusercontent.com/StopBeingLogical/seshat/main/current.md`

4. **Identify the active project** via `projects.md`, then fetch the project's `SESSION_SEED.md` from its repo for deep technical context

5. **Fetch `infrastructure.md`** if the task involves file paths, deployments, git operations, or SSH access
   `https://raw.githubusercontent.com/StopBeingLogical/seshat/main/infrastructure.md`

---

## Shell Access — Local Path Reference

If you have filesystem access, prefer these local paths over remote URLs:

| Resource | Local Path |
|:---|:---|
| Seshat repo | `/Volumes/Shuttle/projects/seshat/` |
| Nisaba repo (mirror) | `/Volumes/Shuttle/projects/gamerepo/` |
| Nisaba source (canonical) | `truenas_admin@192.168.3.174:/mnt/MemoryAlpha/nisaba/source/` |
| Auth / credentials | `/Volumes/Shuttle/projects/seshat/.auth` |
| Canonical seed archive | `/Volumes/Shuttle/canonical seeds/` |

---

## Changelog
- **2026-03-17:** Initial version
