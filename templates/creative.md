# Creative Template (PARA Method)

Asset and project-based structure for designers, artists, and content creators.

## Folder Structure

```
Target-Directory/
├── 0-Inbox/                    # Unsorted downloads
│   └── _REVIEW/
├── 1-Projects/                 # Active creative projects
│   ├── Client-Work/
│   │   ├── [Client-Name]/
│   │   └── [Client-Name]/
│   └── Personal/
│       ├── [Project-Name]/
│       └── [Project-Name]/
├── 2-Areas/                    # Ongoing creative responsibilities
│   ├── Portfolio/
│   │   ├── Web/
│   │   └── Print/
│   ├── Brand-Assets/
│   │   ├── Logos/
│   │   ├── Colors/
│   │   └── Guidelines/
│   └── Client-Management/
│       └── Contracts/
├── 3-Resources/
│   ├── Media/
│   │   ├── Photos/
│   │   ├── Illustrations/
│   │   ├── Icons/
│   │   ├── Fonts/
│   │   ├── Textures/
│   │   ├── Audio/
│   │   └── Video/
│   ├── Inspiration/
│   │   ├── Mood-Boards/
│   │   ├── References/
│   │   └── Screenshots/
│   ├── Templates/
│   │   ├── Social-Media/
│   │   ├── Print/
│   │   └── Web/
│   ├── Stock/
│   │   ├── Licensed/
│   │   └── Free/
│   └── Tools/
│       ├── Plugins/
│       ├── Actions/
│       └── Brushes/
└── 4-Archive/
    ├── Completed-Projects/
    └── Old-Assets/
```

## Project Codes

```yaml
project_codes:
  # Work types
  CLIENT: "Client Work"
  PERSONAL: "Personal Project"
  SPEC: "Spec/Practice Work"

  # Asset types
  STOCK: "Stock Asset"
  INSPO: "Inspiration"
  TEMPLATE: "Template"
```

## Detection Keywords

```yaml
categories:
  1-Projects:
    - project
    - draft
    - wip
    - final
    - revision
    - mockup
    - comp

  3-Resources/Media:
    extensions:
      - .psd
      - .ai
      - .fig
      - .sketch
      - .xd
      - .indd
    keywords:
      - photo
      - illustration
      - icon
      - texture

  3-Resources/Inspiration:
    - mood
    - reference
    - inspo
    - screenshot
    - capture
```

## Inbox Review for Creatives

### Daily (5 min)
- Active project files → 1-Projects/[Project]/
- Stock downloads → 3-Resources/Stock/
- Screenshots/refs → 3-Resources/Inspiration/

### Weekly (15 min)
- Archive completed projects
- Organize new fonts and assets
- Update portfolio with finished work

### Project Completion
Move project folder from `1-Projects/` to `4-Archive/Completed-Projects/`

## Naming Convention

`PROJECT_asset-description.ext`

Examples:
- `CLIENT_acme-logo-final.ai`
- `STOCK_abstract-gradient-blue.jpg`
- `PERSONAL_portfolio-hero-v3.fig`

## Asset Organization Tips

### Fonts
- Keep licensed fonts in `3-Resources/Media/Fonts/`
- Include license files with each font

### Stock Assets
- Separate licensed vs. free in `3-Resources/Stock/`
- Keep receipts/licenses with purchased assets

### Inspiration
- Use `3-Resources/Inspiration/` for reference material
- Organize by mood board or project when relevant
