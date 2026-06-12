---
Author: Cody Cork
tags:
  - SPAWN/Notes
Type: Document
Date: 2026-03-05
---

# Pulled From Claude Code

## Core Philosophy

![[Full Stack Workflow - 06.png]]

## Dropbox File System

![[Full Stack Workflow - 01.png]]


## Obsidian Vault

![[Full Stack Workflow - 02.png]]


## Git Setup - What Gets Committed

![[Full Stack Workflow - 03.png]]


## Git & Dropbox Integration

![[Full Stack Workflow - 07.png]]


## Daily Workflow

![[Full Stack Workflow - 04.png]]


## Quick Reference

![[Full Stack Workflow - 08.png]]



---


# MD File

# Freelance Audio Engineer — System & Structure

> Obsidian · Git/GitHub · Dropbox · Music & Sound Design


## 00 — Core Philosophy

The entire system is built on one rule: **each tool does one job and never overlaps.**

| Tool | Purpose |
|---|---|
| **Dropbox** | All audio, sessions, renders, assets — anything binary or large |
| **Git / GitHub** | All text — Obsidian vault, notes, templates, project metadata |
| **Obsidian** | The brain — connects both systems via `dropbox_path` in frontmatter |

> **Key Rule:** Git never touches audio binaries. Dropbox never stores your knowledge base. They run in parallel and reference each other — never redundant, never conflicting.

---

## 01 — Dropbox Folder Structure

```
📦 Dropbox/AudioWork/
├── _CLIENTS/
│   └── ClientName/
│       └── YYYY_ProjectTitle_Type/
│           ├── _SESSIONS/        ← DAW project files (.als, .ptx, .logic)
│           ├── _STEMS/           ← exported stems & buses
│           ├── _RENDERS/
│           │   ├── WIP/          ← revision renders
│           │   └── FINAL/        ← approved deliverables
│           ├── _ASSETS/          ← client-provided files, references
│           └── _DELIVERABLES/    ← final files sent to client
│
├── _SOUND_DESIGN/
│   ├── SFX_Library/
│   │   ├── Ambience/
│   │   ├── Foley/
│   │   ├── UI_Game/
│   │   ├── Impacts_Transitions/
│   │   └── Field_Recordings/
│   └── Projects/
│       └── YYYY_ProjectTitle/
│
├── _MUSIC/
│   ├── Original/
│   │   └── YYYY_TrackTitle/
│   └── Sync_Licensing/
│       └── Catalog/              ← finalized, tagged masters
│
├── _TEMPLATES/
│   ├── DAW_Templates/
│   └── Sample_Packs/
│
└── _ARCHIVE/
    └── YYYY/                     ← completed projects by year
```

### Naming Convention

```
# Dropbox project folders
YYYY_ProjectTitle_Type
→ 2025_SongName_Mix
→ 2025_AlbumTitle_Master
→ 2025_GameTitle_SoundDesign
→ 2025_FilmTitle_Score

# Audio render files
ProjectTitle_vN_Description.wav
→ SongName_v3_MixRef.wav
→ SongName_FINAL_Stereo.wav
→ SongName_FINAL_Instrumental.wav
```

> Underscores only — no spaces. Prefix folders with `_` to sort them to the top.

---

## 02 — Obsidian Vault Structure (Git Repo)

```
📓 ~/Documents/AudioVault/   ← Git repo root
│
├── 00_INBOX/                ← quick capture, unsorted
│
├── 01_CLIENTS/
│   └── ClientName/
│       ├── _Index.md        ← MOC for this client
│       ├── Brief_ProjectTitle.md
│       ├── Contract_YYYY-MM-DD.md
│       ├── Invoice_001.md
│       ├── Session_Notes.md
│       └── Feedback_Log.md
│
├── 02_PROJECTS/
│   └── YYYY_ProjectTitle/
│       ├── _Index.md        ← links to Dropbox path in frontmatter
│       ├── Production_Notes.md
│       ├── Mix_Log.md
│       └── Revision_History.md
│
├── 03_KNOWLEDGE/
│   ├── Mixing/
│   ├── Sound_Design/
│   ├── Music_Theory/
│   └── Gear_Software/
│
├── 04_BUSINESS/
│   ├── Finance/
│   │   ├── Income_Tracker.md
│   │   └── Expenses_YYYY.md
│   ├── Rates_Services.md
│   └── Client_CRM.md
│
├── 05_TEMPLATES/
│   ├── New_Client.md
│   ├── Project_Brief.md
│   ├── Session_Notes.md
│   ├── Invoice.md
│   └── Mix_Log.md
│
├── 06_JOURNAL/
│   └── YYYY-MM-DD.md
│
├── 06_ARCHIVE/
│   └── YYYY/
│
└── Dashboard.md             ← Dataview live project dashboard
```

---

## 03 — Project Note Template

Every project in Obsidian uses this frontmatter. The `dropbox_path` is the link that connects your notes to your files.

```yaml
---
title:          Nike Ad — Sound Design
client:         Nike
type:           sound-design   # mixing | mastering | original | sound-design | score
status:         active         # active | review | delivered | archived
start_date:     2025-01-15
deadline:       2025-02-01
rate:           flat $2000      # or $X/hr
invoice_status: unpaid          # unpaid | sent | paid
dropbox_path:   ~/Dropbox/AudioWork/_CLIENTS/Nike/2025_NikeAd_SoundDesign/
daw:            Ableton 12
tags:           [client, sound-design, active]
---

## Brief
...

## Production Notes
...

## Revision Log

| Rev | Date       | Notes          |
|-----|------------|----------------|
| v1  | 2025-01-20 | First delivery |

## Deliverables
- [ ] Stem export
- [ ] Final stereo mix
- [ ] Invoice sent
```

---

## 04 — Git Setup

### .gitignore (vault root)

```gitignore
# Audio & DAW files — use Dropbox instead
*.wav
*.aiff
*.aif
*.mp3
*.flac
*.ogg
*.als
*.ptx
*.logic
*.rpp
*.mid
*.sf2
*.vst3

# Large exports & media
*.pdf
*.zip
*.rar
*.ai
*.psd

# OS junk
.DS_Store
Thumbs.db
*.tmp
*.log

# Obsidian cache (keep .obsidian/plugins and .obsidian/snippets)
.obsidian/workspace.json
.obsidian/workspace-mobile.json
.obsidian/cache
```

### Branch Strategy

```
main        → clean, reviewed vault — push here weekly
wip         → daily edits, drafts, auto-commits go here

# Optional per-client branches
client/nike-2025
client/jane-album-mix
```

Merge `wip → main` once a week:

```bash
git checkout main
git merge wip
git push origin main
```

### Obsidian Git Plugin Settings

```
Auto backup interval:   30 minutes
Commit message:         vault: {{date}} auto-backup
Push on backup:         true
Pull on startup:        true
Backup on file save:    false  (too noisy)
```

For meaningful manual commits:

```bash
git add -A && git commit -m "client: added Nike brief + contract"
git push origin wip
```

---

## 05 — Dataview Dashboard

Create `Dashboard.md` at the vault root. These queries auto-build from your frontmatter.

````md
## Active Projects
```dataview
TABLE client, type, deadline, invoice_status
FROM "02_PROJECTS"
WHERE status = "active"
SORT deadline ASC
```

## Unpaid Invoices
```dataview
TABLE client, rate, invoice_status
FROM "01_CLIENTS"
WHERE invoice_status = "unpaid" OR invoice_status = "sent"
SORT file.mtime DESC
```

## Recent Projects
```dataview
TABLE client, status, dropbox_path
FROM "02_PROJECTS"
SORT file.mtime DESC
LIMIT 10
```
````

---

## 06 — New Project Workflow

### Starting a Project

1. **Create Dropbox folder** — `_CLIENTS/ClientName/YYYY_Title_Type/` with all subfolders
2. **Create Obsidian project note** — use Project template, fill frontmatter including `dropbox_path`
3. **Work in Dropbox** — all sessions, renders, assets stay there. Audio never touches the vault
4. **Log in Obsidian** — revision notes, feedback, decisions, deliverable checklists go in the project note
5. **Vault auto-commits** — Obsidian Git backs up to GitHub every 30 min silently

### Closing a Project

1. Move approved finals to `_RENDERS/FINAL/` in Dropbox
2. Set frontmatter `status: delivered` and `invoice_status: sent`
3. Once paid, update `invoice_status: paid` and log in `Income_Tracker.md`
4. Move Obsidian note to `06_ARCHIVE/YYYY/`
5. Move Dropbox folder to `_ARCHIVE/YYYY/`

---

## 07 — Recommended Obsidian Plugins

| Plugin | Use |
|---|---|
| **Obsidian Git** | Auto-commit & push to GitHub on a schedule — hands-free backup |
| **Dataview** | Query project notes like a database; build live dashboards from frontmatter |
| **Templater** | Dynamic templates that auto-fill dates and prompt for client name on creation |
| **Tasks** | Turn checklist items in notes into a tracked task system with due dates |
| **Calendar** | Daily note navigation; view session logs by date |
| **QuickAdd** | One-key capture macros for new client, new project, new session note |

---

## 08 — Quick Reference

### What Lives Where

```
DROPBOX  ~/Dropbox/AudioWork/
  + DAW session files (.als, .ptx, .logic)
  + Audio files (.wav, .aif, .mp3, stems)
  + Renders, deliverables, WIP exports
  + Sample packs & licensed content
  + Plugin preset banks
  + Contract & invoice PDFs
  + DAW session templates

GIT / GITHUB  ~/Documents/AudioVault/
  + All Obsidian .md notes
  + Project notes & templates
  + Client profiles & history
  + Business docs, income tracker
  + Technique & knowledge notes
  + Obsidian config files
```

### Obsidian Note Naming

```
02_PROJECTS/  →  YYYY_ProjectTitle.md
01_CLIENTS/   →  ClientName_Overview.md
06_JOURNAL/   →  YYYY-MM-DD.md
```

---

> **System Summary:** Dropbox syncs your project files. Git backs up your brain. Obsidian connects them with a simple path field. Each system does one job — no overlap, no conflicts, no LFS needed.
