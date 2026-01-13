# Developer Template (PARA Method)

Project and repository-focused structure for software developers.

## Folder Structure

```
Target-Directory/
├── 0-Inbox/                    # Unsorted downloads
│   └── _REVIEW/
├── 1-Projects/                 # Active development work
│   ├── Work/
│   ├── Personal/
│   └── Open-Source/
├── 2-Areas/                    # Ongoing dev responsibilities
│   ├── Environment/           # Dev environment configs
│   │   ├── Dotfiles/
│   │   └── Configs/
│   ├── Security/              # Keys, certs (sensitive)
│   └── Backups/
├── 3-Resources/
│   ├── Media/
│   │   ├── Icons/
│   │   ├── Fonts/
│   │   └── Images/
│   ├── Tools/
│   │   ├── Installers/
│   │   ├── Scripts/
│   │   └── CLIs/
│   ├── Learning/
│   │   ├── Documentation/
│   │   ├── APIs/
│   │   ├── Tutorials/
│   │   └── Courses/
│   └── Data/
│       ├── Datasets/
│       └── Exports/
└── 4-Archive/
    ├── Completed-Projects/
    └── Deprecated/
```

## Project Codes

```yaml
project_codes:
  # Work types
  WORK: "Work Project"
  PERSONAL: "Personal Project"
  OSS: "Open Source"
  LEARN: "Learning/Tutorial"

  # Categories
  TOOL: "Tool/Utility"
  DOC: "Documentation"
  DATA: "Data/Export"
```

## Detection Keywords

```yaml
categories:
  1-Projects:
    - src
    - build
    - deploy
    - release
    - sprint
    - feature
    - bugfix

  3-Resources/Tools:
    - installer
    - setup
    - .dmg
    - .exe
    - .pkg
    - .deb
    - .rpm

  3-Resources/Learning:
    - readme
    - docs
    - api
    - spec
    - rfc
    - tutorial
    - guide

  3-Resources/Data:
    - export
    - backup
    - .json
    - .csv
    - .sql
    - dataset
```

## Inbox Review for Developers

### Daily (5 min)
- Sort new downloads by project → 1-Projects/
- File documentation → 3-Resources/Learning/
- Move installers → 3-Resources/Tools/

### Weekly (15 min)
- Archive completed/abandoned projects
- Clean up old data exports
- Update dev environment backups

## Naming Convention

`PROJECT_description.ext`

Examples:
- `WORK_api-documentation-v2.pdf`
- `OSS_react-icons-pack.zip`
- `LEARN_rust-tutorial.pdf`

## Security Note

Files in `2-Areas/Security/` (keys, certificates, credentials) are automatically flagged and require explicit approval before any organization actions.
