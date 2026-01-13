# Creative Template

Asset and project-based structure for designers, artists, and content creators.

## Folder Structure

```
Downloads/
├── _INBOX/              # Unsorted new downloads
├── _REVIEW/             # Files needing manual review
├── Projects/
│   ├── Client-Work/
│   └── Personal/
├── Assets/
│   ├── Photos/
│   ├── Illustrations/
│   ├── Icons/
│   ├── Fonts/
│   ├── Textures/
│   ├── Audio/
│   └── Video/
├── Inspiration/
│   ├── Mood-Boards/
│   ├── References/
│   └── Screenshots/
├── Templates/
│   ├── Social-Media/
│   ├── Print/
│   └── Web/
├── Stock/
│   ├── Licensed/
│   └── Free/
└── Archive/
```

## Project Codes

```yaml
project_codes:
  - CLIENT
  - PERSONAL
  - STOCK
  - TEMPLATE
  - INSPO      # Inspiration
```

## Detection Keywords

```yaml
categories:
  Photos:
    - .jpg
    - .jpeg
    - .png
    - .raw
    - .heic
    - photo
    - img
  Illustrations:
    - .ai
    - .svg
    - .eps
    - illustration
    - vector
  Fonts:
    - .ttf
    - .otf
    - .woff
    - font
  Video:
    - .mp4
    - .mov
    - .avi
    - footage
  Audio:
    - .mp3
    - .wav
    - .aiff
    - music
    - sound
```

## Naming Convention

`PROJECT_asset-description.ext`

Examples:
- `CLIENT_acme-logo-final.ai`
- `STOCK_abstract-gradient-blue.jpg`
