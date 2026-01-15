---
name: file-organizer
description: Organize files using the PARA method (Building a Second Brain). Intelligent categorization into Projects, Areas, Resources, and Archive with inbox workflow. Triggers on "organize my files", "organize my downloads", "second brain", "PARA method", "clean up files". Creates numbered PARA folders, renames poorly-named files, and maintains rollback logs. Works via bash commands in Claude Code terminal.
---

# File Organizer (Claude Code - PARA Method)

Organizes files using the PARA methodology with bash commands. Intelligent categorization and audit trails.

## What is PARA?

| # | Category | Contains | Lifespan |
|---|----------|----------|----------|
| 0 | Inbox | New files awaiting processing | Temporary |
| 1 | Projects | Active work with deadlines | Short-term |
| 2 | Areas | Ongoing responsibilities | Long-term |
| 3 | Resources | Reference materials by topic | Evergreen |
| 4 | Archive | Inactive/completed items | Preserved |

## Workflow

```
Phase 1: Discovery     → ls, find, file commands to scan and assess
Phase 2: Analysis      → Read file contents for poor names (use Read tool for PDFs)
Phase 3: Triage        → Create categorization table, flag sensitive/scam files
Phase 4: Preparation   → mkdir -p to create PARA structure, get approval
Phase 5: Execution     → mv commands with logging
Phase 6: Cleanup       → Remove empty folders, delete temp files
Phase 7: Completion    → Generate summary, verify PARA folder roots are clean
```

### 0-Review Staging Workflow

For large batches of poorly-named files, use a staging folder:

```bash
# Create staging folder for files needing content analysis
mkdir -p ~/Downloads/0-Review

# Move cryptic/poorly-named files to review
mv ~/Downloads/U0BPA6*.pdf ~/Downloads/0-Review/
mv ~/Downloads/[0-9][0-9][0-9][0-9][0-9].pdf ~/Downloads/0-Review/

# Analyze each file, then move to proper PARA location
# Remove staging folder when empty
rmdir ~/Downloads/0-Review
```

## Quick Start

```bash
# 1. Create PARA folder structure
mkdir -p ~/Downloads/{0-Inbox/_REVIEW,1-Projects/{Work,Personal},2-Areas/{Finance,Health,Legal,Career},3-Resources/{Media/{Images,Videos,Audio,Screenshots},Tools/{Installers,Utilities},Learning/{Articles,Books,Courses}},4-Archive/{Completed-Projects,Past-Years},_ORG}

# 2. Scan target directory
find ~/Downloads -maxdepth 1 -type f | wc -l
ls -la ~/Downloads | head -50

# 3. Move files (log each operation)
mv "~/Downloads/file.pdf" "~/Downloads/2-Areas/Finance/"
```

## PARA Folder Structure

```bash
# One-liner to create full PARA structure
mkdir -p ~/Downloads/{0-Inbox/_REVIEW,1-Projects/{Work,Personal},2-Areas/{Finance,Health,Legal,Career,Home},3-Resources/{Media/{Images,Videos,Audio,Screenshots},Tools/{Installers,Utilities},Learning/{Articles,Books,Courses},Templates},4-Archive/{Completed-Projects,Past-Areas,Old-Resources},_ORG}
```

Visual structure:
```
Target-Directory/
├── 0-Inbox/                    # New files land here first
│   └── _REVIEW/
├── 1-Projects/                 # Active work with deadlines
│   ├── Work/
│   └── Personal/
├── 2-Areas/                    # Ongoing responsibilities
│   ├── Finance/
│   ├── Health/
│   ├── Legal/
│   └── Career/
├── 3-Resources/                # Reference materials
│   ├── Media/
│   ├── Tools/
│   └── Learning/
├── 4-Archive/                  # Inactive items
│   └── Completed-Projects/
└── _ORG/                       # Tracking files
```

## Inbox Review Workflow

### Daily Review (5 min)

```bash
# List inbox contents
ls -la ~/Downloads/0-Inbox/

# For each file, determine PARA destination:
# Actionable with deadline? → 1-Projects
# Ongoing responsibility?   → 2-Areas
# Reference material?       → 3-Resources
# Completed/inactive?       → 4-Archive
```

### Weekly Review (15 min)

```bash
# 1. Check for remaining inbox items
ls ~/Downloads/0-Inbox/

# 2. Find completed projects (no recent modifications)
find ~/Downloads/1-Projects -maxdepth 2 -type d -mtime +30

# 3. Archive completed projects
mv ~/Downloads/1-Projects/old-project ~/Downloads/4-Archive/Completed-Projects/
```

## File Naming Convention

Format: `[DATE]_[CODE]_[description].[ext]`

```bash
# Examples
mv "Document.pdf" "2025-01_FIN_tax-statement.pdf"
mv "IMG_1234.jpg" "2025-01_REF_vacation-photo.jpg"
mv "Screenshot 2025-01-13.png" "2025-01-13_PROJ_meeting-notes.png"
```

### PARA Category Codes

| Code | Category | Destination |
|------|----------|-------------|
| PROJ | Projects | 1-Projects/ |
| FIN | Finance | 2-Areas/Finance/ |
| HEALTH | Health | 2-Areas/Health/ |
| LEGAL | Legal | 2-Areas/Legal/ |
| REF | Reference | 3-Resources/ |
| LEARN | Learning | 3-Resources/Learning/ |

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

# Random alphanumeric strings (auto-generated filenames)
ls ~/Downloads | grep -iE "^[A-Z0-9]{16,}\.[a-z]+$"

# Numeric-only filenames (e.g., 65440.pdf)
ls ~/Downloads | grep -E "^[0-9]+\.[a-z]+$"

# Scan prefixes with timestamps
ls ~/Downloads | grep -iE "^scan_.*[0-9]{4}-[0-9]{2}-[0-9]{2}"

# Gmail exports
ls ~/Downloads | grep -iE "^Gmail.*\.pdf$"
```

## Auto-Categorization by Type

```bash
# Move images to Resources/Media
find ~/Downloads/0-Inbox -maxdepth 1 \( -name "*.jpg" -o -name "*.png" -o -name "*.gif" \) -exec mv {} ~/Downloads/3-Resources/Media/Images/ \;

# Move installers to Resources/Tools
find ~/Downloads/0-Inbox -maxdepth 1 \( -name "*.dmg" -o -name "*.exe" -o -name "*.pkg" \) -exec mv {} ~/Downloads/3-Resources/Tools/Installers/ \;

# Move PDFs with financial keywords to Areas/Finance
for f in ~/Downloads/0-Inbox/*.pdf; do
  if pdftotext "$f" - 2>/dev/null | grep -qiE "invoice|receipt|statement|tax"; then
    mv "$f" ~/Downloads/2-Areas/Finance/
  fi
done
```

## Logging Template

Create `_ORG/_LOG.md`:

```bash
cat > ~/Downloads/_ORG/_LOG.md << 'EOF'
# Organization Log (PARA Method)
**Started**: $(date '+%Y-%m-%d %H:%M')

## Operations
| Time | Action | File | From | To (PARA) |
|------|--------|------|------|-----------|
EOF

# Log each move
echo "| $(date '+%H:%M') | MOVE | file.pdf | 0-Inbox | 2-Areas/Finance/ |" >> ~/Downloads/_ORG/_LOG.md
```

## Safety Rules

1. **Never delete** - only move to 0-Inbox/_REVIEW if uncertain
2. **Log everything** - append to _LOG.md before each mv
3. **Approval checkpoints** - pause and confirm before bulk moves
4. **Preserve dates** - use `mv` (not cp+rm) to keep timestamps
5. **Sensitive files** - flag anything in 2-Areas/{Finance,Health,Legal}

## Security & Scam Detection

Flag and quarantine potential scam/phishing files:

```bash
# Common scam patterns in PDFs (fake invoices, tech support scams)
# Keywords to search: "Norton", "McAfee", "Microsoft Support",
# "Your account", "Payment required", "Call immediately"

# Check PDF content for scam indicators
for f in ~/Downloads/*.pdf; do
  if pdftotext "$f" - 2>/dev/null | grep -qiE "norton|mcafee|geek squad|call.*1-[0-9]{3}"; then
    echo "⚠️  POTENTIAL SCAM: $f"
    mv "$f" ~/Downloads/0-Inbox/_REVIEW/
  fi
done
```

**Scam indicators:**
- Random alphanumeric filename (e.g., `U0BPA6IUWL6FUQRUHYCZ.pdf`)
- Fake invoice from security software companies
- "Call this number" with toll-free numbers
- Urgent payment demands

**Action:** Move to `_REVIEW` folder, flag for user, recommend DELETE

## Sensitive Document Handling

Flag and secure sensitive documents:

```bash
# Tax documents (W-2, 1099, tax returns)
ls ~/Downloads | grep -iE "(w-2|w2|1099|tax.*(return|form))"

# Documents with SSN patterns
grep -l "[0-9]\{3\}-[0-9]\{2\}-[0-9]\{4\}" ~/Downloads/*.pdf 2>/dev/null

# Financial statements
ls ~/Downloads | grep -iE "(statement|account.*summary|routing.*number)"
```

**Sensitive file types:**
| Type | Flag | Destination |
|------|------|-------------|
| W-2, 1099, Tax forms | ⚠️ SENSITIVE | 2-Areas/Finance/Tax/ |
| Contracts with signatures | ⚠️ LEGAL | 2-Areas/Legal/ |
| Medical records | ⚠️ HEALTH | 2-Areas/Health/ |
| Password/credential files | ⚠️ SECURE | Encrypted storage |

**Action:** Flag in categorization table, confirm with user before moving

## Duplicate Detection

```bash
# Find duplicates by name pattern
ls ~/Downloads/0-Inbox | grep -E "\([0-9]+\)\." | while read f; do
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

# Large media files typically go to Resources
find ~/Downloads/0-Inbox -maxdepth 1 -size +100M \( -name "*.mp4" -o -name "*.mov" \) -exec mv {} ~/Downloads/3-Resources/Media/Videos/ \;
```

## Session Resume

If interrupted, check last operation:

```bash
tail -5 ~/Downloads/_ORG/_LOG.md
```

## Temp File Cleanup

Remove common junk files before organizing:

```bash
# Office temp files (~$...)
find ~/Downloads -name "~\$*" -delete

# macOS metadata
find ~/Downloads -name ".DS_Store" -delete
find ~/Downloads -name "._*" -delete

# Empty files
find ~/Downloads -maxdepth 1 -type f -empty -delete
```

## PARA Root-Level Audit

After initial organization, check for loose files at PARA folder roots:

```bash
# Files should be in subfolders, not at PARA root level
echo "=== 2-Areas root files (should be in subfolders) ==="
find ~/Downloads/2-Areas -maxdepth 1 -type f ! -name ".DS_Store"

echo "=== 3-Resources root files ==="
find ~/Downloads/3-Resources -maxdepth 1 -type f ! -name ".DS_Store"

echo "=== 4-Archive root files ==="
find ~/Downloads/4-Archive -maxdepth 1 -type f ! -name ".DS_Store"
```

## Empty Folder Cleanup

After processing, remove empty staging folders:

```bash
# Remove empty review/staging folders
rmdir ~/Downloads/0-Review 2>/dev/null
rmdir ~/Downloads/0-Inbox/_REVIEW 2>/dev/null

# Find and remove empty subdirectories
find ~/Downloads -type d -empty -delete
```

## Categorization Table Format

Present recommendations in a clear table before executing:

```markdown
### 🚫 DELETE (scam/junk)
| File | Reason |
|------|--------|
| `U0BPA6...pdf` | SCAM - Fake Norton invoice |

### ⚠️ SENSITIVE → 2-Areas/Finance
| File | Content |
|------|---------|
| `65440.pdf` | W-2 Tax Form 2024 |

### 📁 4-Archive
| File | Suggested Rename |
|------|------------------|
| `old-project.pdf` | `2023-01_PROJ_project-name.pdf` |

### 📚 3-Resources
| File | Destination |
|------|-------------|
| `manual.pdf` | 3-Resources/Tools/ |
```

**Emoji flags:**
- 🚫 DELETE - Scam, junk, or duplicate
- ⚠️ SENSITIVE - Tax, legal, medical, credentials
- 📁 ARCHIVE - Old/completed items
- 📚 RESOURCES - Reference materials
- 📂 AREAS - Ongoing responsibilities
- 📝 PROJECTS - Active work

## Reference Files

- **references/config.md**: Customize PARA structure and detection keywords
- **references/templates.md**: Tracking file templates
