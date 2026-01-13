---
name: downloads-organizer
description: Organize a cluttered Downloads folder with intelligent categorization, smart renaming, and full audit trails. Use when user wants to clean up, organize, or sort their Downloads folder. Triggers on "organize my downloads", "clean up downloads", "sort downloads", "declutter downloads". Creates structured folders, renames poorly-named files based on content analysis, identifies duplicates, and maintains rollback logs. Works via bash commands in Claude Code terminal.
---

# Downloads Organizer (Claude Code)

Organizes cluttered Downloads folders using bash commands with intelligent categorization and audit trails.

## Workflow

```
Phase 1: Discovery     → ls, find, file commands to scan and assess
Phase 2: Analysis      → Read file contents for poor names (pdftotext, etc.)
Phase 3: Preparation   → mkdir -p to create structure, get approval
Phase 4: Execution     → mv commands with logging
Phase 5: Completion    → Generate summary report
```

## Quick Start

```bash
# 1. Create tracking folder
mkdir -p ~/Downloads/_ORG

# 2. Scan Downloads
find ~/Downloads -maxdepth 1 -type f | wc -l
ls -la ~/Downloads | head -50

# 3. Create folder structure
mkdir -p ~/Downloads/{WORK/{Projects,Proposals},DOCUMENTS/{Financial,Legal},PERSONAL/{Receipts,Travel},MEDIA/{Images,Screenshots},REFERENCE/{Articles,Books},SOFTWARE,_REVIEW,_RECENT}

# 4. Move files (log each operation)
mv "~/Downloads/file.pdf" "~/Downloads/WORK/Projects/"
```

## Default Folder Structure

```bash
mkdir -p ~/Downloads/{WORK/{Projects,Proposals,Clients,_Archive},DOCUMENTS/{Financial,Legal,Credentials},PERSONAL/{Family,Health,Travel,Receipts},MEDIA/{Images,Videos,Audio,Screenshots},SOFTWARE/{Installers,Updates},REFERENCE/{Articles,Books-PDFs,Courses},_REVIEW,_RECENT,_ORG}
```

## File Naming Convention

Format: `[DATE]_[CODE]_[description].[ext]`

```bash
# Examples
mv "Document.pdf" "2025-01_ACME_quarterly-report.pdf"
mv "IMG_1234.jpg" "2025-01_PERS_vacation-photo.jpg"
mv "Screenshot 2025-01-13.png" "2025-01-13_GEN_meeting-notes.png"
```

## Content Analysis (Bash)

For poorly-named files, extract content to determine proper naming:

```bash
# PDFs - extract text
pdftotext "Document.pdf" - | head -50

# If pdftotext unavailable, try:
strings "Document.pdf" | head -100

# Images - check EXIF data
file "IMG_1234.jpg"
exiftool "IMG_1234.jpg" 2>/dev/null | grep -E "Date|Title|Description"

# Office docs - unzip and read
unzip -p "document.docx" word/document.xml | head -100
```

## Files to Analyze

Trigger content analysis for:
```bash
# Generic names
ls ~/Downloads | grep -iE "^(document|untitled|copy of|new )"

# Camera defaults
ls ~/Downloads | grep -iE "^(IMG_|DSC_|DCIM|scan[0-9])"

# Screenshots
ls ~/Downloads | grep -iE "^(screenshot|screen shot|capture)"

# Numbered duplicates
ls ~/Downloads | grep -E "\([0-9]+\)\."
```

## Logging Template

Create `_ORG/_LOG.md`:

```bash
cat > ~/Downloads/_ORG/_LOG.md << 'EOF'
# Organization Log
**Started**: $(date '+%Y-%m-%d %H:%M')

## Operations
| Time | Action | File | From | To |
|------|--------|------|------|-----|
EOF

# Log each move
echo "| $(date '+%H:%M') | MOVE | file.pdf | Downloads | WORK/Projects/ |" >> ~/Downloads/_ORG/_LOG.md
```

## Safety Rules

1. **Never delete** - only move to _REVIEW if uncertain
2. **Log everything** - append to _LOG.md before each mv
3. **Approval checkpoints** - pause and confirm before bulk moves
4. **Preserve dates** - use `mv` (not cp+rm) to keep timestamps

## Duplicate Detection

```bash
# Find duplicates by name pattern
ls ~/Downloads | grep -E "\([0-9]+\)\." | while read f; do
  original="${f/ ([0-9])/}"
  echo "Duplicate: $f -> Original: $original"
done

# Find duplicates by content (md5)
find ~/Downloads -maxdepth 1 -type f -exec md5sum {} \; | sort | uniq -d -w32
```

## Large File Handling

```bash
# Find files > 100MB
find ~/Downloads -maxdepth 1 -type f -size +100M -exec ls -lh {} \;

# Move installers to SOFTWARE
find ~/Downloads -maxdepth 1 -name "*.dmg" -o -name "*.exe" -o -name "*.pkg" | while read f; do
  mv "$f" ~/Downloads/SOFTWARE/Installers/
done
```

## Session Resume

If interrupted, check last operation:
```bash
tail -5 ~/Downloads/_ORG/_LOG.md
```

## Reference Files

- **references/config.md**: Customize folder structure and project codes
- **references/templates.md**: Tracking file templates
