# File Organizer Skills for Claude Code & Cowork

> AI-powered file organization using the **PARA method** from "Building a Second Brain." Intelligent categorization into Projects, Areas, Resources, and Archive with inbox workflow.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Claude Code](https://img.shields.io/badge/Claude_Code-Compatible-blue)](https://docs.anthropic.com/en/docs/claude-code)
[![Cowork](https://img.shields.io/badge/Cowork-Compatible-blueviolet)](https://claude.ai)
[![PARA Method](https://img.shields.io/badge/PARA-Second_Brain-orange)](https://fortelabs.com/blog/para/)

## What Is This?

This repository contains **skills** (reusable instruction sets) that teach Claude how to organize files using the PARA methodology. Point Claude at any messy directory and it will:

- Categorize files into Projects, Areas, Resources, and Archive
- Propose smart renames for `Document(3).pdf` and `IMG_1234.jpg`
- Guide you through daily/weekly inbox reviews
- Keep a complete audit trail for rollback

**Works on any directory** - Downloads, Desktop, project folders, or anywhere files accumulate.

---

## Why I Built This

Like most people, my Downloads folder had become a graveyard of forgotten files - `Document (3).pdf`, `IMG_1234.jpg`, `Screenshot 2024-01-15...`. I tried manual cleanup (never finished), traditional organizers (couldn't understand context), and AI assistants (couldn't access my actual files).

**The problem?** Every tool treated organization as one-size-fits-all. But my files aren't generic - client projects, personal receipts, research articles, and family photos all mixed together.

**The solution:** An AI agent that learns *your* structure, reads file contents to understand what they actually are, asks before acting, and keeps complete logs. In my first run, it organized 81 files in 45 minutes - finding forgotten flight receipts, surfacing an investor deck hiding as a screenshot, and flagging duplicates.

[Read the full story →](docs/STORY.md)

---

## What is PARA?

PARA is an organizational system from [Building a Second Brain](https://www.buildingasecondbrain.com/) by Tiago Forte:

| # | Category | Contains | Lifespan |
|---|----------|----------|----------|
| 0 | **Inbox** | New files awaiting processing | Temporary |
| 1 | **Projects** | Active work with deadlines | Short-term |
| 2 | **Areas** | Ongoing responsibilities | Long-term |
| 3 | **Resources** | Reference materials by topic | Evergreen |
| 4 | **Archive** | Inactive/completed items | Preserved |

[Full PARA methodology guide →](docs/PARA-GUIDE.md)

---

## Two Skills, One Goal

| | Claude Code Skill | Cowork Skill |
|---|---|---|
| **Platform** | Terminal / CLI | Claude Desktop app |
| **Best For** | Developers, power users | General users |
| **Interface** | Bash commands | Conversational |
| **Installation** | `~/.claude/skills/` | `.skills/skills/` |

### Claude Code Skill

For users of [Claude Code](https://docs.anthropic.com/en/docs/claude-code) - Anthropic's CLI tool.

```bash
# Install
git clone https://github.com/smithjoshua/claude-code-cowork-skills-file-organizer.git
cp -r claude-code-cowork-skills-file-organizer/claude-code-skill ~/.claude/skills/file-organizer

# Use
claude
> Organize my ~/Downloads folder using PARA
> Help me do a weekly review
```

[Full Claude Code skill documentation →](claude-code-skill/README.md)

---

### Cowork Skill

For users of **Cowork** (Claude Desktop).

```bash
# Install
git clone https://github.com/smithjoshua/claude-code-cowork-skills-file-organizer.git
cp -r claude-code-cowork-skills-file-organizer/cowork-skill ~/.skills/skills/file-organizer

# Use in Cowork
# "Organize my downloads with PARA"
# "Help me process my inbox"
```

[Full Cowork skill documentation →](cowork-skill/README.md)

---

## Folder Structure (PARA Method)

Both skills create this structure:

```
Target-Directory/
├── 0-Inbox/                 # New files awaiting processing
│   └── _REVIEW/             # Files needing manual attention
├── 1-Projects/              # Active work with deadlines
│   ├── Work/
│   └── Personal/
├── 2-Areas/                 # Ongoing responsibilities
│   ├── Finance/
│   ├── Health/
│   └── Legal/
├── 3-Resources/             # Reference materials by topic
│   ├── Media/               # Images, videos, audio
│   ├── Tools/               # Software, installers
│   └── Learning/            # Articles, books, courses
├── 4-Archive/               # Inactive/completed items
└── _ORG/                    # Tracking files (log, manifest)
```

---

## Inbox Workflow

The key to PARA is regular inbox processing. New files land in `0-Inbox/` and get sorted during review sessions.

### Daily Review (5 min)

For each file in `0-Inbox/`, ask:

```
Is this actionable?        → 1-Projects
Ongoing responsibility?    → 2-Areas
Reference material?        → 3-Resources
Completed/inactive?        → 4-Archive
None of the above?         → Delete
```

### Weekly Review (15 min)

1. Clear remaining inbox items
2. Archive completed projects
3. Review areas for relevance
4. Clean up resource duplicates

---

## File Naming Convention

**Format:** `YYYY-MM_CODE_description.ext`

| Before | After |
|--------|-------|
| `Document (3).pdf` | `2025-01_FIN_quarterly-report.pdf` |
| `IMG_1234.jpg` | `2025-01_REF_vacation-beach.jpg` |
| `Screenshot 2025-01-13...` | `2025-01-13_PROJ_meeting-notes.png` |

---

## Safety First

- **Never deletes files** - only moves them
- **Approval required** - for all renames and sensitive files
- **Complete audit trail** - undo any operation via `_ORG/_MANIFEST.md`
- **Uncertain files** - go to `0-Inbox/_REVIEW/` for manual sorting
- **Sensitive detection** - flags financial, medical, legal docs

---

## Customization

### Preset Templates

All templates use the PARA methodology. Choose a starting point in [`/templates`](templates/):

| Template | Best For | PARA Focus |
|----------|----------|------------|
| [minimalist.md](templates/minimalist.md) | Simple organization | Pure 5-folder PARA |
| [freelancer.md](templates/freelancer.md) | Consultants | Projects by client |
| [developer.md](templates/developer.md) | Software engineers | Dev resources |
| [student.md](templates/student.md) | Students | Projects by course |
| [creative.md](templates/creative.md) | Designers | Rich media library |
| [family.md](templates/family.md) | Households | Area responsibilities |

### Custom Configuration

Edit `references/config.md` in your installed skill to define:
- Your PARA folder structure
- Project/client codes
- Detection keywords for auto-categorization
- Inbox workflow prompts

[Full customization guide →](docs/CUSTOMIZATION.md)

---

## Requirements

**Claude Code:**
- [Claude Code CLI](https://docs.anthropic.com/en/docs/claude-code) installed
- Terminal access
- Optional: `pdftotext`, `exiftool` for enhanced content analysis

**Cowork:**
- [Claude Desktop](https://claude.ai/download) with Cowork enabled
- Skills folder configured

---

## Contributing

Contributions welcome! See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

**Ideas:**
- Additional PARA templates
- Language/locale support
- Cloud storage integration
- Enhanced content analysis

---

## Roadmap

See [ROADMAP.md](ROADMAP.md) for planned features including:
- Undo command
- Cloud storage support (Dropbox, Google Drive, iCloud)
- Scheduled organization
- Custom rules engine

---

## About PARA

This project implements the **PARA Method** from [Building a Second Brain](https://www.buildingasecondbrain.com/) by Tiago Forte. PARA (Projects, Areas, Resources, Archive) is a universal organizational system used by thousands for personal knowledge management (PKM).

## License

MIT License - see [LICENSE](LICENSE)

---

**Built for the Claude AI ecosystem by [Joshua Smith](https://github.com/smithjoshua)**

**If this helped you build your second brain, please star the repo!**
