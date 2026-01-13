# File Organizer Skills for Claude Code & Cowork

> AI-powered file organization skills for Claude. Smart categorization, intelligent renaming, and complete audit trails for any directory.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Claude Code](https://img.shields.io/badge/Claude_Code-Compatible-blue)](https://docs.anthropic.com/en/docs/claude-code)
[![Cowork](https://img.shields.io/badge/Cowork-Compatible-blueviolet)](https://claude.ai)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](http://makeapullrequest.com)

## What Is This?

This repository contains **skills** (reusable instruction sets) that teach Claude how to organize files intelligently. Point Claude at any messy directory and it will:

- Analyze and categorize files by content, not just extension
- Propose smart renames for `Document(3).pdf` and `IMG_1234.jpg`
- Create an organized folder structure
- Move files with your approval
- Keep a complete audit trail for rollback

**Works on any directory** - Downloads, Desktop, project folders, or anywhere files accumulate.

## Two Skills, One Goal

| | Claude Code Skill | Cowork Skill |
|---|---|---|
| **Platform** | Terminal / CLI | Claude Desktop app |
| **Best For** | Developers, power users | General users |
| **Interface** | Bash commands | Conversational |
| **Installation** | `~/.claude/skills/` | `.skills/skills/` |
| **Invocation** | "Organize my files" | "Organize my downloads" |

### Claude Code Skill

For users of [Claude Code](https://docs.anthropic.com/en/docs/claude-code) - Anthropic's CLI tool. Uses bash commands (`mv`, `find`, `mkdir`) directly in your terminal.

```bash
# Install
git clone https://github.com/smithjoshua/claude-code-cowork-skills-file-organizer.git
cp -r claude-code-cowork-skills-file-organizer/claude-code-skill ~/.claude/skills/file-organizer

# Use in Claude Code
claude
> Organize my ~/Downloads folder
> Clean up ~/Desktop
> Sort the files in ~/Projects/old-stuff
```

**Key Features:**
- Direct bash command execution
- Works on any directory you specify
- Detailed logging with timestamps
- Content analysis via `pdftotext`, `exiftool`, `strings`

[Full Claude Code skill documentation →](claude-code-skill/README.md)

---

### Cowork Skill

For users of **Cowork** (Claude Desktop). Conversational interface with guided approval checkpoints.

```bash
# Install
git clone https://github.com/smithjoshua/claude-code-cowork-skills-file-organizer.git
cp -r claude-code-cowork-skills-file-organizer/cowork-skill ~/.skills/skills/file-organizer

# Use in Cowork
# Just say: "Organize my downloads" or "Clean up my files"
```

**Key Features:**
- Guided conversational workflow
- Visual approval checkpoints
- Step-by-step progress updates
- Great for first-time users

[Full Cowork skill documentation →](cowork-skill/README.md)

---

## How It Works

```
1. SCAN      → Claude analyzes the target directory
2. CATEGORIZE → Files grouped by type, project, or content
3. PROPOSE   → You see a plan before anything moves
4. APPROVE   → Nothing happens without your OK
5. EXECUTE   → Files renamed and organized
6. LOG       → Complete audit trail for rollback
```

## Folder Structure (Default)

Both skills create this structure (customizable):

```
Target-Directory/
├── WORK/                    # Professional files
│   ├── Projects/
│   ├── Clients/
│   └── _Archive/
├── DOCUMENTS/               # General documents
│   ├── Financial/
│   ├── Legal/
│   └── Credentials/
├── PERSONAL/                # Personal files
├── MEDIA/                   # Images, videos, audio
│   ├── Screenshots/
│   └── Photos/
├── SOFTWARE/                # Installers, apps
├── REFERENCE/               # Articles, books, courses
├── _REVIEW/                 # Files needing manual attention
└── _ORG/                    # Tracking files (log, manifest)
```

## File Naming Convention

**Format:** `YYYY-MM_PROJECT_description.ext`

| Before | After |
|--------|-------|
| `Document (3).pdf` | `2025-01_ACME_quarterly-report.pdf` |
| `IMG_1234.jpg` | `2025-01_PERS_vacation-beach.jpg` |
| `Screenshot 2025-01-13...` | `2025-01-13_WORK_meeting-notes.png` |

## Safety First

- **Never deletes files** - only moves them
- **Approval required** - for all renames and sensitive files
- **Complete audit trail** - undo any operation via `_ORG/_MANIFEST.md`
- **Uncertain files** - go to `_REVIEW/` for manual sorting
- **Sensitive detection** - flags financial, medical, legal docs

## Customization

### Preset Templates

Choose a starting point in [`/templates`](templates/):

| Template | Best For |
|----------|----------|
| [freelancer.md](templates/freelancer.md) | Client-based work |
| [developer.md](templates/developer.md) | Software projects |
| [student.md](templates/student.md) | Course materials |
| [creative.md](templates/creative.md) | Design assets |
| [family.md](templates/family.md) | Shared family files |
| [minimalist.md](templates/minimalist.md) | Simple 5-folder structure |

### Custom Configuration

Edit `references/config.md` in your installed skill to define:
- Your folder structure
- Project/client codes (e.g., `ACME`, `PROJ1`)
- Detection keywords for auto-categorization

[Full customization guide →](docs/CUSTOMIZATION.md)

## Quick Comparison

| Feature | Claude Code | Cowork |
|---------|-------------|--------|
| Direct bash access | Yes | No |
| Works on any path | Yes | Yes |
| Approval checkpoints | Yes | Yes |
| Audit trail | Yes | Yes |
| Content analysis | Via CLI tools | Built-in |
| Best for | Technical users | Everyone |

## Requirements

**Claude Code:**
- [Claude Code CLI](https://docs.anthropic.com/en/docs/claude-code) installed
- Terminal access
- Optional: `pdftotext`, `exiftool` for enhanced content analysis

**Cowork:**
- [Claude Desktop](https://claude.ai/download) with Cowork enabled
- Skills folder configured

## Contributing

Contributions welcome! See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

**Ideas:**
- Additional folder templates
- Language/locale support
- Cloud storage integration
- Enhanced content analysis

## Roadmap

See [ROADMAP.md](ROADMAP.md) for planned features including:
- Undo command
- Cloud storage support (Dropbox, Google Drive, iCloud)
- Scheduled organization
- Custom rules engine

## License

MIT License - see [LICENSE](LICENSE)

---

**Built for the Claude AI ecosystem by [Joshua Smith](https://github.com/smithjoshua)**

**If this helped you, please star the repo!**
