# Customization Guide

This guide explains how to customize Downloads Organizer for your workflow.

## Configuration File

Edit `references/config.md` in your skill folder to customize behavior.

## Folder Structure

Define your preferred folder hierarchy:

```yaml
folders:
  - Documents
  - Images
  - Videos
  - Software
  - Projects
  - Archive
```

## Project Codes

Add codes for automatic categorization:

```yaml
project_codes:
  - ACME       # Client name
  - PROJ1      # Project identifier
  - PERSONAL   # Personal files
```

## Detection Keywords

Define keywords that trigger categorization:

```yaml
categories:
  Documents:
    - invoice
    - contract
    - report
  Images:
    - screenshot
    - photo
    - scan
```

## Preset Templates

Choose from ready-made configurations in `/templates`:

| Template | Best For |
|----------|----------|
| [freelancer.md](../templates/freelancer.md) | Client-based work |
| [developer.md](../templates/developer.md) | Software projects |
| [student.md](../templates/student.md) | Course materials |
| [creative.md](../templates/creative.md) | Design assets |
| [family.md](../templates/family.md) | Shared family files |
| [minimalist.md](../templates/minimalist.md) | Simple organization |

## Naming Convention

Default format: `YYYY-MM_PROJECT_description.ext`

Customize in config:

```yaml
naming:
  include_date: true
  date_format: "YYYY-MM"
  include_project: true
  separator: "_"
```

## Sensitive File Detection

Files matching these patterns require explicit approval:

```yaml
sensitive_keywords:
  - tax
  - medical
  - legal
  - password
  - financial
```

## Behavior Settings

```yaml
settings:
  require_approval: true      # Always ask before moving
  create_audit_log: true      # Log all operations
  handle_duplicates: "ask"    # ask, skip, or rename
  uncertain_folder: "_REVIEW" # Where to put uncertain files
```
