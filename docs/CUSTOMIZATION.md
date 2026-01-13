# Customization Guide

This guide explains how to customize File Organizer for your workflow using the PARA methodology.

## Understanding PARA

This organizer uses the PARA method from "Building a Second Brain":

| # | Category | Purpose | Lifespan |
|---|----------|---------|----------|
| 0 | Inbox | New files awaiting processing | Temporary |
| 1 | Projects | Active work with deadlines | Short-term |
| 2 | Areas | Ongoing responsibilities | Long-term |
| 3 | Resources | Reference materials | Evergreen |
| 4 | Archive | Inactive items | Preserved |

For the complete methodology, see [PARA-GUIDE.md](PARA-GUIDE.md).

---

## Configuration File

Edit `references/config.md` in your installed skill to customize behavior.

## Folder Structure

The default PARA structure:

```yaml
folders:
  0-Inbox:
    - _REVIEW
  1-Projects:
    - Work
    - Personal
  2-Areas:
    - Finance
    - Health
    - Legal
    - Career
  3-Resources:
    Media:
      - Images
      - Videos
      - Audio
    Tools:
      - Installers
    Learning:
      - Articles
      - Books
      - Courses
  4-Archive:
    - Completed-Projects
    - Past-Areas
```

Add or modify subfolders based on your needs.

---

## Preset Templates

All templates use the PARA methodology. Choose a starting point:

| Template | Best For | PARA Focus |
|----------|----------|------------|
| [freelancer.md](../templates/freelancer.md) | Consultants, contractors | Projects by client |
| [developer.md](../templates/developer.md) | Software engineers | Resources for dev tools |
| [student.md](../templates/student.md) | Students, academics | Projects by course |
| [creative.md](../templates/creative.md) | Designers, artists | Rich media resources |
| [family.md](../templates/family.md) | Households | Areas for responsibilities |
| [minimalist.md](../templates/minimalist.md) | Simple organization | Pure 5-folder PARA |

---

## Project Codes

Define short codes for file naming:

```yaml
codes:
  # Projects (active work)
  PROJ: "Active Project"
  CLIENT: "Client Work"

  # Areas (responsibilities)
  FIN: "Finance"
  HEALTH: "Health"
  LEGAL: "Legal"

  # Resources (reference)
  REF: "Reference Material"
  LEARN: "Learning"
```

---

## Detection Keywords

Keywords trigger auto-categorization into PARA folders:

```yaml
detection:
  1-Projects:
    - project
    - deadline
    - deliverable
    - draft
    - final

  2-Areas/Finance:
    - invoice
    - receipt
    - tax
    - statement

  2-Areas/Health:
    - medical
    - prescription
    - insurance

  3-Resources/Media:
    extensions:
      - .jpg
      - .png
      - .mp4
    patterns:
      - IMG_*
      - Screenshot*

  3-Resources/Tools:
    - .dmg
    - .exe
    - installer
```

---

## Inbox Workflow Settings

Configure daily/weekly review prompts:

```yaml
inbox_workflow:
  auto_prompt_daily_review: true
  auto_prompt_weekly_review: true

  daily_review_prompt: |
    Time for your daily inbox review!
    For each file in 0-Inbox:
    - Actionable? → 1-Projects
    - Responsibility? → 2-Areas
    - Reference? → 3-Resources
    - Done? → 4-Archive

  weekly_review_prompt: |
    Weekly review time!
    1. Clear remaining inbox
    2. Archive completed projects
    3. Review areas for relevance
```

---

## Naming Convention

Default format: `YYYY-MM_CODE_description.ext`

Customize in config:

```yaml
naming:
  include_date: true
  date_format: "YYYY-MM"
  include_code: true
  separator: "_"
```

Examples:
- `2025-01_PROJ_website-mockup.fig`
- `2025-01_FIN_tax-statement.pdf`

---

## Sensitive File Detection

Files matching these patterns require explicit approval:

```yaml
sensitive_keywords:
  - tax
  - medical
  - legal
  - password
  - financial
  - ssn
  - account

sensitive_locations:
  - 2-Areas/Finance
  - 2-Areas/Health
  - 2-Areas/Legal
```

---

## Behavior Settings

```yaml
settings:
  require_approval_for_renames: true
  require_approval_for_moves: false
  require_approval_for_sensitive: true
  never_delete_files: true
  preserve_original_dates: true
  skip_files_larger_than_mb: 500
  inbox_processing_enabled: true
```

---

## Migrating from Old Structure

If you're upgrading from a non-PARA structure:

| Old | New (PARA) |
|-----|------------|
| WORK/ | 1-Projects/ or 2-Areas/ |
| DOCUMENTS/ | 2-Areas/ |
| MEDIA/ | 3-Resources/Media/ |
| SOFTWARE/ | 3-Resources/Tools/ |
| REFERENCE/ | 3-Resources/Learning/ |
| _REVIEW/ | 0-Inbox/_REVIEW/ |

The organizer can help migrate files - just say "migrate my files to PARA."
