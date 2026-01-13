# Developer Template

Project and repository-focused structure for software developers.

## Folder Structure

```
Downloads/
├── _INBOX/              # Unsorted new downloads
├── _REVIEW/             # Files needing manual review
├── Projects/
│   ├── work/
│   └── personal/
├── Documentation/
│   ├── APIs/
│   ├── Specs/
│   └── Tutorials/
├── Assets/
│   ├── Icons/
│   ├── Fonts/
│   └── Images/
├── Tools/
│   ├── Installers/
│   └── Scripts/
├── Data/
│   ├── Exports/
│   ├── Backups/
│   └── Datasets/
└── Archive/
```

## Project Codes

```yaml
project_codes:
  - WORK
  - PERSONAL
  - OSS        # Open source
  - LEARN      # Learning/tutorials
  - TOOL       # Tools and utilities
```

## Detection Keywords

```yaml
categories:
  Documentation:
    - readme
    - docs
    - api
    - spec
    - rfc
  Tools:
    - installer
    - setup
    - .dmg
    - .exe
    - .pkg
  Data:
    - export
    - backup
    - .json
    - .csv
    - .sql
```

## Naming Convention

`PROJECT_description.ext`

Examples:
- `WORK_api-documentation-v2.pdf`
- `OSS_react-icons-pack.zip`
