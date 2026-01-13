# Organization Configuration

Customize this file for your folder structure and naming conventions.

## Folder Structure

Edit to match your organization needs:

```yaml
folders:
  WORK:
    - Projects
    - Proposals
    - Clients
    - _Archive
  DOCUMENTS:
    - Financial
    - Legal
    - Credentials
    - Reference-Materials
  PERSONAL:
    - Family
    - Health
    - Travel
    - Receipts
  MEDIA:
    - Images
    - Videos
    - Audio
    - Screenshots
  SOFTWARE:
    - Installers
    - Updates
  REFERENCE:
    - Articles
    - Books-PDFs
    - Courses
    - AI-Prompts
  _REVIEW: []      # Files needing manual attention
  _RECENT: []      # Files < 7 days old
```

## Project/Client Codes

Define short codes for your projects and clients:

```yaml
codes:
  # Work projects
  ACME: "Acme Corporation"
  PROJ: "Internal Project"

  # Personal
  PERS: "Personal"
  FAM: "Family"

  # General
  GEN: "General/Uncategorized"
```

## Content Detection Keywords

Keywords to identify file destinations:

```yaml
detection:
  WORK:
    - "invoice"
    - "proposal"
    - "contract"
    - "project"
  PERSONAL:
    - "receipt"
    - "booking"
    - "reservation"
    - "medical"
    - "prescription"
  REFERENCE:
    - "guide"
    - "tutorial"
    - "syllabus"
    - "ebook"
```

## Sensitivity Flags

Flag files containing:

| Type | Indicators | Action |
|------|------------|--------|
| Financial | SSN, account numbers, tax forms | Flag for review |
| Medical | Health records, prescriptions | Flag for review |
| Legal | Contracts, agreements | Flag for review |
| Credentials | Passwords, API keys | DO NOT MOVE, alert immediately |

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
  recent_files_days: 7
```
