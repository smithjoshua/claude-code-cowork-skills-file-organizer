---
name: downloads-organizer
description: Organize a cluttered Downloads folder with intelligent categorization, smart renaming, and full audit trails. Use when user wants to clean up, organize, or sort their Downloads folder. Triggers on phrases like "organize my downloads", "clean up downloads", "sort my downloads folder", "declutter downloads". Creates structured folders (WORK/, PERSONAL/, MEDIA/, REFERENCE/, etc.), renames poorly-named files based on content analysis, identifies duplicates, and maintains complete logs for rollback.
---

# Downloads Organizer

Organizes cluttered Downloads folders with intelligent categorization, content-based renaming, and complete audit trails.

## Workflow Overview

```
Phase 1: Discovery     → Scan, count, assess filename quality
Phase 2: Analysis      → Read file contents for poor names, propose renames
Phase 3: Preparation   → Create folder structure, get user approval
Phase 4: Execution     → Rename and move files (with logging)
Phase 5: Completion    → Generate summary, finalize documentation
```

## Quick Start

1. Create `_ORG/` folder in target directory
2. Initialize tracking files from references/templates.md
3. Customize references/config.md for user's folder structure and naming
4. Execute phases with user approval checkpoints

## Folder Structure (Default)

```
Downloads/
├── WORK/                    # Professional/client work
│   ├── Projects/
│   ├── Proposals/
│   └── _Archive/
├── DOCUMENTS/               # General documents
│   ├── Financial/
│   ├── Legal/
│   └── Credentials/
├── PERSONAL/                # Personal files
│   ├── Family/
│   ├── Health/
│   ├── Travel/
│   └── Receipts/
├── MEDIA/                   # Media files
│   ├── Images/
│   ├── Videos/
│   ├── Audio/
│   └── Screenshots/
├── SOFTWARE/                # Installers and updates
├── REFERENCE/               # Learning materials
│   ├── Articles/
│   ├── Books/
│   └── Courses/
├── _REVIEW/                 # Files needing manual attention
├── _RECENT/                 # Files < 7 days old
└── _ORG/                    # Organization tracking files
    ├── _PLAN.md
    ├── _LOG.md
    ├── _MANIFEST.md
    └── _CONFIG.md
```

## File Naming Convention

Format: `[DATE]_[PROJECT]_[DESCRIPTION].[ext]`

| Component | Format | Example |
|-----------|--------|---------|
| Date | YYYY-MM-DD, YYYY-MM, or YYYY | 2025-01-13 |
| Project | Short code (3-4 chars) | ACME, PERS, GEN |
| Description | lowercase-with-hyphens | quarterly-report |

Example: `2025-01_ACME_quarterly-report_v02.pdf`

## Content Analysis Triggers

Analyze file contents when filename matches:
- Generic: `Document*.pdf`, `Untitled*`, `Copy of *`
- Camera: `IMG_####.*`, `DSC_####.*`, `scan####.*`
- Screenshots: `Screenshot *`, `Screen Shot *`
- Ambiguous: `notes.*`, `report.*`, `data.*`, `export.*`

Do NOT rename: Software installers (.dmg, .exe, .pkg), files with version hashes

## Approval Checkpoints

**Required user approval before:**
1. Executing any renames
2. Moving files to destinations
3. Handling sensitive files (financial, medical, legal)

Never delete files without explicit user confirmation.

## Logging Requirements

Update tracking files in real-time:

**_PLAN.md**: Task checklist with timestamps
- ⬜ Not started → 🔄 In progress → ✅ Complete

**_LOG.md**: Action journal with entries:
```markdown
### [TIMESTAMP] - [ACTION TYPE]
**Task**: [Reference to plan]
**Action**: [What was done]
**Result**: [Outcome]
**Next**: [Next step]
```

**_MANIFEST.md**: File operations audit trail
- Every rename and move logged with timestamps
- Enables rollback if needed

## Reference Files

- **references/config.md**: Customizable folder structure and project codes
- **references/templates.md**: Blank templates for _PLAN.md, _LOG.md, _MANIFEST.md

## Session Resumption

If session is interrupted:
1. Read `_LOG.md` to find last completed action
2. Read `_PLAN.md` to find next incomplete task
3. Log: `### [TIME] - SESSION ... Resuming interrupted session`
4. Continue from that point
