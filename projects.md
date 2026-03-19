# Projects
**Last Updated:** 2026-03-17
**Scope:** Active and exploratory software projects. Sumerian naming domain.

---

For source locations, replication topology, and access patterns see [infrastructure.md](https://raw.githubusercontent.com/StopBeingLogical/seshat/main/infrastructure.md).

## Active

### NISABA
- **Purpose:** Unified personal game library and wishlist manager
- **Status:** Active development, in production on Atlas
- **Stack:** Go 1.25, Chi, SQLite, HTMX, Tailwind CSS, Docker
- **Stores:** Steam, GOG, Epic, Amazon (EA/Ubisoft deferred)
- **Live at:** `nisaba.damnaliens.us`
- **Repo:** [Forgejo](http://git.damnaliens.us/bobby/nisaba) · [GitHub](https://github.com/StopBeingLogical/Nisaba)
- **Deep context:** `SESSION_SEED.md` in the Nisaba repo

### NIDABA
- **Purpose:** Corpus migration and knowledge atomization pipeline
- **Status:** Active — initial corpus run complete (~420k atoms embedded)
- **Stack:** Ollama (local LLMs), ChromaDB (vector store), high-concurrency pipeline
- **Primary compute:** Logos (M1 Max, Metal acceleration) — Daemon recommended for future runs >1GB
- **Goal:** Atomize and embed personal corpus; refine into canonical topic seeds
- **Repo:** [Forgejo](ssh://git@192.168.3.174:2222/bobby/Nidaba.git) · [GitHub](https://github.com/StopBeingLogical/Nidaba)
- **Deep context:** `SESSION_SEED.md` in the Nidaba repo

### ENKI
- **Purpose:** Intent Engineering / JIT world generation research
- **Status:** Exploratory
- **Goal:** Generating coherent environments from high-level "vibe" descriptions

---

## Infrastructure

### Concierge
- **Purpose:** Personal AI operating system — distributed across the network
- **Status:** Planning / early architecture
- **Confirmed architectural direction:**
  - Wide not Deep — each GPU is an independent island running its own model; no sharding
  - Pull-based routing — nodes bid on work from a pool; Router posts agnostic chunks, nodes pull what they can handle
  - Quorum diversity — multiple model lineages (different families/architectures) to prevent coherent failure modes
- **Authority model:** Human intent is absolute; system proposes and surfaces risks
- **Note:** Specific layer names, node roles, and terminology from planning sessions should be treated as proposals until explicitly confirmed

### Seshat
- **Purpose:** This repo — AI context seed repository
- **Repo:** [Forgejo](http://git.damnaliens.us/bobby/seshat) · [GitHub](https://github.com/StopBeingLogical/seshat)

---

## Changelog
- **2026-03-17:** Initial version
- **2026-03-18:** Added NIDABA
