# Infrastructure
**Last Updated:** 2026-03-17
**Scope:** Source of truth locations, replication topology, and access patterns for all projects and services. Reference this before making changes to any file or repo.

---

## Replication Model

All projects follow the same pattern:

```
Atlas (source of truth)
  └─ git push → Forgejo (git.damnaliens.us, primary remote)
                    └─ push mirror → GitHub (automatic, cloud backup)
Logos (local clone, mirrors on pull)
```

- **Edits happen on Atlas.** The working copy on Atlas is canonical.
- **Logos is a passive mirror.** Pull from Forgejo at milestones. Do not treat Logos as the source of truth.
- **GitHub is a cloud backup.** Forgejo mirrors to GitHub automatically on every push. Never push directly to GitHub.
- **Commits happen on Atlas** and flow outward. At milestone points, sync Atlas → Logos and commit from there if needed.

---

## Projects

### NISABA
| Location | Path | Purpose |
|:---|:---|:---|
| **Atlas (source)** | `/mnt/MemoryAlpha/nisaba/source/` | Canonical working copy |
| **Atlas (data)** | `/mnt/MemoryAlpha/nisaba/data/nisaba.db` | Live database (never committed) |
| **Logos (mirror)** | `/Volumes/Shuttle/projects/gamerepo/` | Local clone, synced at milestones |
| **Forgejo (primary)** | `http://git.damnaliens.us/bobby/nisaba` | Primary remote (`origin`) |
| **GitHub (backup)** | `https://github.com/StopBeingLogical/Nisaba` | Auto-mirror via Forgejo push mirror |

**SSH access to Atlas:** `ssh truenas_admin@192.168.3.174` (key with passphrase — run `ssh-add` first)

**Milestone sync (Atlas → Logos → commit):**
```bash
rsync -av --exclude='*.db' --exclude='imgcache' --exclude='._*' \
  truenas_admin@192.168.3.174:/mnt/MemoryAlpha/nisaba/source/ \
  /Volumes/Shuttle/projects/gamerepo/
cd /Volumes/Shuttle/projects/gamerepo
git add -A && git commit -m "..." && git push
```

**Deploy on Atlas:**
```bash
ssh -t truenas_admin@192.168.3.174 "cd /mnt/MemoryAlpha/nisaba/source && bash deploy.sh"
```

---

### SESHAT
| Location | Path | Purpose |
|:---|:---|:---|
| **Logos (source)** | `/Volumes/Shuttle/projects/seshat/` | Canonical working copy |
| **Forgejo (primary)** | `http://git.damnaliens.us/bobby/seshat` | Primary remote (`origin`) |
| **GitHub (backup)** | `https://github.com/StopBeingLogical/seshat` | Auto-mirror via Forgejo push mirror |

Seshat is the exception — it lives on Logos, not Atlas, since it's edited during active sessions on the primary workstation. Atlas has no clone of Seshat.

**Commit workflow:**
```bash
cd /Volumes/Shuttle/projects/seshat
git add -A && git commit -m "..." && git push
```

---

## Access

### Forgejo (git.damnaliens.us)
- Protected by Cloudflare Access — login required for external access
- Git clients use HTTP extraHeader for the service token (configured globally on Logos and Atlas)
- LAN access via `192.168.3.174:3000` bypasses Cloudflare — no token needed on-network
- **Service token:** stored in `/Volumes/Shuttle/projects/seshat/.auth` (local only, git-ignored)

### GitHub
- **Token:** stored in `/Volumes/Shuttle/projects/seshat/.auth`
- Used for API operations and as Forgejo push mirror credential

---

## Changelog
- **2026-03-17:** Initial version
