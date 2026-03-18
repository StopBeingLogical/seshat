# Glossary
**Last Updated:** 2026-03-17
**Scope:** Unified term → role → location map. Use this for quick orientation on any named asset.

---

## Hardware Nodes

| Name | Role | OS / Platform | Network | Local Access |
|:---|:---|:---|:---|:---|
| **Logos** | Primary Workstation | macOS (MBP M1 Max, 64GB) | LAN + portable | `/Volumes/Shuttle/` (local SSD) |
| **Atlas** | Storage / Services | TrueNAS SCALE (Ryzen 5700G, 64GB, 3×12TB RaidZ1) | `192.168.3.174` | `/mnt/MemoryAlpha/` |
| **Daemon** | Headless CUDA Node | Linux (i7-12700F, 32GB, 2× Tesla P100, 1× 5060 Ti) | LAN | — |
| **Aegis** | Firewall / VPN / Router | — (vacant role, no hardware assigned) | — | — |
| **Ergaster** | Planner / Router | Windows (Acemagic i9-13900HX, 64GB) | LAN | — |
| **Kratos** | High-Perf Compute | Linux (Ryzen 7600X, RX 7800 XT, 32GB DDR5) | LAN | — |
| **Praxis** | Gaming | SteamOS (Steam Deck) | LAN + portable | — |
| **Gramma** | Note-taking | iPadOS (Air M3) | LAN + portable | — |

---

## Software Projects

| Name | Domain | Role | Running At | Canonical Source |
|:---|:---|:---|:---|:---|
| **NISABA** | Sumerian | Game library + wishlist manager | `nisaba.damnaliens.us` | Atlas: `/mnt/MemoryAlpha/nisaba/source/` |
| **NIDABA** | Sumerian | Corpus atomization + knowledge pipeline | Local (Logos) | `/Volumes/Shuttle/projects/nidaba/` |
| **ENKI** | Sumerian | Intent Engineering / JIT world generation | Exploratory | — |
| **Concierge** | — | Personal AI operating system (distributed) | Planning | — |
| **Seshat** | Egyptian | AI context seed repository | `github.com/StopBeingLogical/seshat` | Logos: `/Volumes/Shuttle/projects/seshat/` |

---

## Key Locations

| Path | Node | What lives here |
|:---|:---|:---|
| `/Volumes/Shuttle/` | Logos | Primary working volume — all local project mirrors |
| `/Volumes/Shuttle/projects/seshat/` | Logos | Seshat canonical source |
| `/Volumes/Shuttle/projects/nidaba/` | Logos | NIDABA source + ChromaDB (`tracker/chroma_db/`) |
| `/Volumes/Shuttle/projects/nisaba/` | Logos | Nisaba local mirror (not canonical) |
| `/Volumes/Shuttle/canonical seeds/` | Logos | Canonical seed archive (hardware inventory, software projects list) |
| `/mnt/MemoryAlpha/nisaba/source/` | Atlas | Nisaba canonical source |
| `/mnt/MemoryAlpha/nisaba/data/nisaba.db` | Atlas | Nisaba live database (never committed) |

---

## Naming Domains

| Domain | Cultural Root | Examples |
|:---|:---|:---|
| Hardware | Greek / Latin | Logos, Atlas, Daemon, Ergaster, Kratos, Praxis, Gramma |
| Software | Sumerian | NISABA, ENKI |
| Writing / AI Context | Egyptian | Seshat |

Names persist across hardware changes. Systems are named for the role they inhabit, not their specs.

---

## Changelog
- **2026-03-17:** Initial version
- **2026-03-18:** Added NIDABA, Aegis (vacant role)
