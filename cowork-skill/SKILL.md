---
name: file-organizer
description: Organize files using the PARA method (Building a Second Brain). Intelligent categorization into Projects, Areas, Resources, and Archive with inbox workflow. Triggers on "organize my files", "organize my downloads", "second brain", "PARA method", "clean up files", "declutter". Creates numbered PARA folders (0-Inbox, 1-Projects, 2-Areas, 3-Resources, 4-Archive), renames poorly-named files, and maintains complete audit trails.
---

# File Organizer (PARA Method)

Organizes files using the PARA methodology from "Building a Second Brain" by Tiago Forte. Intelligent categorization with inbox workflow and complete audit trails.

## What is PARA?

| # | Category | Contains | Lifespan |
|---|----------|----------|----------|
| 0 | Inbox | New files awaiting processing | Temporary |
| 1 | Projects | Active work with deadlines | Short-term |
| 2 | Areas | Ongoing responsibilities | Long-term |
| 3 | Resources | Reference materials by topic | Evergreen |
| 4 | Archive | Inactive/completed items | Preserved |

## Workflow Overview

```
Phase 1: Discovery     → Scan, count, assess filename quality
Phase 2: Analysis      → Read file contents for poor names, propose renames
Phase 3: Preparation   → Create PARA folder structure, get user approval
Phase 4: Execution     → Rename and move files (with logging)
Phase 5: Completion    → Generate summary, prompt inbox review
```

## Quick Start

1. Create `_ORG/` folder in target directory
2. Initialize tracking files from references/templates.md
3. Customize references/config.md for your needs
4. Execute phases with user approval checkpoints

## Folder Structure (PARA Method)

```
Target-Directory/
├── 0-Inbox/                    # New files land here first
│   └── _REVIEW/                # Files needing manual attention
├── 1-Projects/                 # Active work with deadlines
│   ├── Work/
│   └── Personal/
├── 2-Areas/                    # Ongoing responsibilities
│   ├── Finance/
│   ├── Health/
│   ├── Legal/
│   └── Career/
├── 3-Resources/                # Reference materials by topic
│   ├── Media/
│   │   ├── Images/
│   │   ├── Videos/
│   │   ├── Audio/
│   │   └── Screenshots/
│   ├── Tools/
│   │   ├── Installers/
│   │   └── Utilities/
│   └── Learning/
│       ├── Articles/
│       ├── Books/
│       └── Courses/
├── 4-Archive/                  # Inactive/completed items
│   ├── Completed-Projects/
│   └── Past-Years/
└── _ORG/                       # Organization tracking files
    ├── _PLAN.md
    ├── _LOG.md
    └── _MANIFEST.md
```

## Inbox Review Workflow

### Daily Quick Review (5 minutes)

Process files in `0-Inbox/` by asking:

1. **Is this actionable with a deadline?** → Move to `1-Projects/`
2. **Is this an ongoing responsibility?** → Move to `2-Areas/`
3. **Is this useful reference material?** → Move to `3-Resources/`
4. **Is this completed/inactive?** → Move to `4-Archive/`
5. **None of the above?** → Delete or keep in Inbox

### Weekly Deep Review (15 minutes)

1. Clear remaining items in `0-Inbox/`
2. Check `1-Projects/` for completed projects → Archive
3. Review `2-Areas/` for items no longer relevant → Archive
4. Clean up `3-Resources/` duplicates
5. Organize `4-Archive/` by year/category

## File Naming Convention

Format: `[DATE]_[CODE]_[DESCRIPTION].[ext]`

| Component | Format | Example |
|-----------|--------|---------|
| Date | YYYY-MM-DD, YYYY-MM, or YYYY | 2025-01-13 |
| Code | PARA category code | PROJ, FIN, REF |
| Description | lowercase-with-hyphens | quarterly-report |

Example: `2025-01_PROJ_website-mockup.pdf`

### PARA Category Codes

| Code | Category | Use For |
|------|----------|---------|
| PROJ | 1-Projects | Active project files |
| FIN | 2-Areas/Finance | Financial documents |
| HEALTH | 2-Areas/Health | Medical records |
| LEGAL | 2-Areas/Legal | Contracts, agreements |
| REF | 3-Resources | General reference |
| LEARN | 3-Resources/Learning | Educational materials |

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
3. Handling sensitive files (financial, medical, legal in 2-Areas)

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

- **references/config.md**: Customizable PARA structure and detection keywords
- **references/templates.md**: Blank templates for _PLAN.md, _LOG.md, _MANIFEST.md

## Session Resumption

If session is interrupted:
1. Read `_LOG.md` to find last completed action
2. Read `_PLAN.md` to find next incomplete task
3. Log: `### [TIME] - SESSION ... Resuming interrupted session`
4. Continue from that point
