# Downloads Organizer Skill

An AI-powered system for organizing cluttered Downloads folders with intelligent categorization, smart renaming, and complete audit trails.

## First-Time Setup

Before using this skill, customize it for your needs:

### 1. Edit `references/config.md`

**Add your folder structure:**
```yaml
folders:
  WORK:
    - Client-A/
    - Client-B/
    - Internal-Projects/
  # Add your own categories...
```

**Add your project/client codes:**
```yaml
codes:
  # Your clients
  ACME: "Acme Corporation"
  BIGCO: "Big Company Inc"

  # Your projects
  PROJ1: "Project Alpha"

  # Personal
  PERS: "Personal"
  FAM: "Family"
```

**Add detection keywords:**
```yaml
detection:
  WORK:
    - "your-company-name"
    - "client-keyword"
  PERSONAL:
    - "family-member-name"
```

### 2. Installation

**For Cowork (Claude Desktop):**
1. Copy the `downloads-organizer-skill` folder to your `.skills/skills/` directory
2. Start a new Cowork session
3. Say "organize my downloads"

**For Claude Code:**
1. Copy to `~/.claude/skills/downloads-organizer/`
2. Or add to your project's `.claude/skills/` folder
3. Say "organize my downloads" or reference the skill

## Usage

Just say:
- "Organize my downloads"
- "Clean up my Downloads folder"
- "Sort my downloads"

The skill will:
1. Scan your Downloads folder
2. Show you what it found
3. Propose renames for poorly-named files
4. Ask for your approval before making changes
5. Create organized folders and move files
6. Keep a complete log for undo capability

## Features

- **Smart categorization** based on file content, not just extensions
- **Intelligent renaming** using `DATE_PROJECT_description.ext` format
- **Duplicate detection** to clean up `file (1).pdf` copies
- **Approval checkpoints** - nothing happens without your OK
- **Complete audit trail** - every action logged for rollback
- **Sensitive file detection** - flags financial/medical/legal docs

## Customization Tips

**For freelancers/consultants:**
- Add client codes: `CLI1`, `CLI2`, etc.
- Create `WORK/Client-Name/` subfolders

**For students:**
- Use course codes: `CS101`, `MATH201`
- Create `SCHOOL/` instead of `WORK/`

**For families:**
- Add family member names to detection keywords
- Create `FAMILY/Kids/`, `FAMILY/Photos/`, etc.

## Safety

- Files are **never deleted** - only moved
- Uncertain files go to `_REVIEW/` for manual sorting
- All operations logged in `_ORG/_MANIFEST.md`
- Can undo any operation using the manifest

## Questions?

The skill includes approval checkpoints. If unsure about a proposed change, just say "skip that one" or "put it in review."
