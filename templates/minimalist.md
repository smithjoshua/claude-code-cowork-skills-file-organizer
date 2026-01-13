# Minimalist Template

Simple 5-folder structure for those who prefer simplicity.

## Folder Structure

```
Downloads/
├── _INBOX/       # New downloads land here
├── Documents/    # PDFs, docs, spreadsheets
├── Media/        # Images, videos, audio
├── Software/     # Apps, installers, archives
└── Archive/      # Old files, organized by year
```

## How It Works

1. **_INBOX** - Everything new goes here first
2. **Documents** - Anything readable (PDF, DOC, TXT, etc.)
3. **Media** - Anything viewable/playable (images, videos, music)
4. **Software** - Anything installable (DMG, EXE, ZIP, etc.)
5. **Archive** - Manually move old files here

## Detection Keywords

```yaml
categories:
  Documents:
    - .pdf
    - .doc
    - .docx
    - .txt
    - .xls
    - .xlsx
    - .ppt
    - .pptx
  Media:
    - .jpg
    - .jpeg
    - .png
    - .gif
    - .mp4
    - .mov
    - .mp3
    - .wav
  Software:
    - .dmg
    - .exe
    - .pkg
    - .zip
    - .tar
    - .gz
    - .app
```

## Naming Convention

Keep it simple: `description.ext`

No dates or project codes required. Just clean, readable names.

Examples:
- `tax-return-2024.pdf`
- `vacation-photo.jpg`
- `chrome-installer.dmg`

## Best For

- People who don't want to think about organization
- Shared computers
- Quick cleanup sessions
- Those new to file organization
