# 📁 Downloads Organizer for Claude AI

> Transform your chaotic Downloads folder into an organized system with AI-powered categorization, smart renaming, and complete audit trails.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Claude](https://img.shields.io/badge/Claude-Compatible-blueviolet)](https://claude.ai)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](http://makeapullrequest.com)

## 🎬 Demo

![Before and After](docs/demo.gif)

**Before:** 85 files with names like `Document(3).pdf`, `IMG_1234.jpg`, `Screenshot 2024...`
**After:** Organized folders, meaningful names like `2024-01_ACME_quarterly-report.pdf`

## ✨ Features

- **🧠 Smart Categorization** - Analyzes file contents, not just extensions
- **📝 Intelligent Renaming** - `DATE_PROJECT_description.ext` format
- **🔍 Duplicate Detection** - Finds and flags `file (1).pdf` copies
- **✅ Approval Checkpoints** - Nothing happens without your OK
- **📋 Complete Audit Trail** - Every action logged for easy rollback
- **🔒 Sensitive File Detection** - Flags financial, medical, legal docs
- **🔄 Session Recovery** - Resume interrupted organization sessions

## 🚀 Quick Start

### For Claude Desktop (Cowork)
```bash
# Clone the repo
git clone https://github.com/smithjoshua/downloads-organizer.git

# Copy to skills folder
cp -r downloads-organizer/cowork-skill ~/.skills/skills/downloads-organizer

# Start Cowork and say:
# "Organize my downloads"
```

### For Claude Code
```bash
# Clone and copy
git clone https://github.com/smithjoshua/downloads-organizer.git
cp -r downloads-organizer/claude-code-skill ~/.claude/skills/downloads-organizer

# In Claude Code, say:
# "Organize my downloads"
```

## 📖 How It Works

1. **Scan** - Claude analyzes your Downloads folder
2. **Categorize** - Files grouped by type and project
3. **Propose** - You see a plan before anything moves
4. **Execute** - Approve changes, files get organized
5. **Log** - Audit trail saved for rollback

## ⚙️ Customization

Edit `references/config.md` to define:
- Your folder structure
- Project/client codes (e.g., `ACME`, `PROJ1`)
- Detection keywords for auto-categorization
- Behavior settings

See [Customization Guide](docs/CUSTOMIZATION.md) for details.

## 🛡️ Safety First

- **Never deletes files** - only moves them
- **Approval required** - for all renames and sensitive files
- **Complete audit trail** - undo any operation
- **Uncertain files** → `_REVIEW/` folder

## 🤝 Contributing

Contributions welcome! See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

Ideas for contributions:
- Additional folder structure templates (students, developers, creatives)
- Language/locale support
- Integration with cloud storage (Dropbox, Google Drive)
- Desktop notifications

## 📜 License

MIT License - see [LICENSE](LICENSE)

## 🙏 Acknowledgments

Built for the Claude AI ecosystem by [Joshua Smith](https://github.com/smithjoshua)

---

**⭐ If this helped you, please star the repo!**
