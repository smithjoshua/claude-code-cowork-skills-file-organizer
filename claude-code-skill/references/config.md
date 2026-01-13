# Organization Configuration (PARA Method)

Customize this file for your folder structure using the PARA methodology from "Building a Second Brain."

## PARA Folder Structure

```yaml
folders:
  0-Inbox:
    - _REVIEW           # Files needing manual attention
  1-Projects:           # Active work with deadlines
    - Work
    - Personal
  2-Areas:              # Ongoing responsibilities
    - Finance
    - Health
    - Legal
    - Career
    - Home
  3-Resources:          # Reference materials by topic
    Media:
      - Images
      - Videos
      - Audio
      - Screenshots
    Tools:
      - Installers
      - Utilities
    Learning:
      - Articles
      - Books
      - Courses
    Templates: []
  4-Archive:            # Inactive/completed items
    - Completed-Projects
    - Past-Areas
    - Old-Resources
```

## Project/Client Codes

Define short codes for PARA categories:

```yaml
codes:
  # Projects (active work)
  PROJ: "Active Project"
  CLIENT: "Client Work"

  # Areas (responsibilities)
  FIN: "Finance"
  HEALTH: "Health"
  LEGAL: "Legal"
  CAREER: "Career"

  # Resources (reference)
  REF: "Reference Material"
  LEARN: "Learning"

  # General
  GEN: "General/Uncategorized"
```

## Content Detection Keywords

Keywords to auto-categorize into PARA folders:

```yaml
detection:
  1-Projects:
    - "project"
    - "deadline"
    - "deliverable"
    - "milestone"
    - "sprint"
    - "draft"
    - "revision"
    - "wip"
    - "final"

  2-Areas/Finance:
    - "invoice"
    - "receipt"
    - "statement"
    - "tax"
    - "w2"
    - "1099"
    - "bank"
    - "payment"
    - "expense"
    - "budget"

  2-Areas/Health:
    - "medical"
    - "health"
    - "prescription"
    - "insurance"
    - "doctor"
    - "dental"
    - "lab"
    - "test-results"

  2-Areas/Legal:
    - "contract"
    - "agreement"
    - "nda"
    - "lease"
    - "deed"
    - "will"
    - "court"
    - "legal"

  3-Resources/Media:
    extensions:
      - ".jpg"
      - ".jpeg"
      - ".png"
      - ".gif"
      - ".mp4"
      - ".mov"
      - ".mp3"
      - ".wav"
    patterns:
      - "IMG_*"
      - "DSC_*"
      - "Screenshot*"

  3-Resources/Tools:
    extensions:
      - ".dmg"
      - ".exe"
      - ".pkg"
      - ".msi"
      - ".app"
    keywords:
      - "installer"
      - "setup"
      - "update"

  3-Resources/Learning:
    - "guide"
    - "tutorial"
    - "course"
    - "ebook"
    - "syllabus"
    - "lecture"
    - "reference"
    - "documentation"
```

## Inbox Workflow

Prompts for processing files in 0-Inbox:

```yaml
inbox_workflow:
  daily_review_prompt: |
    Time for your daily inbox review! Process files in 0-Inbox:

    For each file, ask:
    - Is this actionable with a deadline? → 1-Projects
    - Is this an ongoing responsibility? → 2-Areas
    - Is this useful reference material? → 3-Resources
    - Is this completed/inactive? → 4-Archive
    - None of the above? → Delete or keep in Inbox

  weekly_review_prompt: |
    Weekly review time! Let's:
    1. Clear remaining 0-Inbox items
    2. Archive completed projects from 1-Projects
    3. Review 2-Areas for items no longer relevant
    4. Clean up 3-Resources duplicates
    5. Organize 4-Archive by year/category
```

## Sensitivity Flags

Flag files containing:

| Type | Indicators | PARA Location | Action |
|------|------------|---------------|--------|
| Financial | SSN, account numbers, tax forms | 2-Areas/Finance | Flag for review |
| Medical | Health records, prescriptions | 2-Areas/Health | Flag for review |
| Legal | Contracts, agreements | 2-Areas/Legal | Flag for review |
| Credentials | Passwords, API keys | DO NOT MOVE | Alert immediately |

## Behavior Settings

```yaml
settings:
  require_approval_for_renames: true
  require_approval_for_moves: false  # Only for HIGH confidence
  require_approval_for_sensitive: true
  never_delete_files: true
  preserve_original_dates: true
  create_review_folder_for_uncertain: true
  skip_files_larger_than_mb: 500
  inbox_processing_enabled: true
  auto_prompt_daily_review: true
  auto_prompt_weekly_review: true
```
