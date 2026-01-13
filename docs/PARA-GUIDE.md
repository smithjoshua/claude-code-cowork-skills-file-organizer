# PARA Method Guide

This guide explains the PARA methodology used by File Organizer Skills.

## What is PARA?

PARA is a universal organizational system created by Tiago Forte, author of "Building a Second Brain." It organizes all information into four categories:

- **P**rojects - Active tasks with deadlines
- **A**reas - Ongoing responsibilities
- **R**esources - Topics of interest
- **A**rchive - Inactive items

## Why Numbered Prefixes?

We use numbered prefixes (0-4) to ensure folders sort in the correct order:

```
0-Inbox/      ← Process first
1-Projects/   ← Most actionable
2-Areas/      ← Regular maintenance
3-Resources/  ← Reference as needed
4-Archive/    ← Rarely accessed
```

This creates a natural workflow from top to bottom.

---

## Category Definitions

### 0-Inbox

**Purpose**: Landing zone for new files before processing.

**What goes here**:
- New downloads
- Email attachments
- Files you haven't categorized yet

**Processing frequency**: Daily (5 min)

**Subfolder**:
- `_REVIEW/` - Files that need manual attention

---

### 1-Projects

**Purpose**: Active work with a specific goal and deadline.

**Definition**: A project has:
- A clear outcome
- A deadline (even if self-imposed)
- Multiple steps to complete

**Examples**:
- Client website redesign
- Tax preparation 2025
- Home renovation
- Wedding planning
- Course assignment

**When to archive**: When the project is complete or abandoned.

**Key insight**: If it has an end date, it's a Project. If it doesn't, it's probably an Area.

---

### 2-Areas

**Purpose**: Ongoing responsibilities you maintain over time.

**Definition**: An area:
- Has no end date
- Requires regular maintenance
- Represents a role or commitment

**Common areas**:

| Area | Contains |
|------|----------|
| Finance | Bank statements, invoices, taxes, budgets |
| Health | Medical records, insurance, prescriptions |
| Legal | Contracts, agreements, important documents |
| Career | Resume, certifications, performance reviews |
| Home | Warranties, maintenance records, manuals |

**When to archive**: When you're no longer responsible for that area.

---

### 3-Resources

**Purpose**: Reference materials organized by topic.

**Definition**: Resources are:
- Not actionable
- Potentially useful someday
- Organized by topic, not by project

**Standard subfolders**:

| Subfolder | Contains |
|-----------|----------|
| Media/ | Images, videos, audio, screenshots |
| Tools/ | Software installers, utilities, scripts |
| Learning/ | Articles, books, courses, tutorials |
| Templates/ | Reusable templates |

**Why Media and Software are Resources**: They are reference materials, not active work or responsibilities. You don't "complete" your photo collection or "maintain" your installers - you reference them when needed.

---

### 4-Archive

**Purpose**: Inactive items you want to keep but don't need regularly.

**What goes here**:
- Completed projects (from 1-Projects)
- Past areas you no longer maintain (from 2-Areas)
- Old resources that aren't relevant anymore (from 3-Resources)

**Structure**:
```
4-Archive/
├── Completed-Projects/
│   ├── 2024-Website-Redesign/
│   └── 2023-Tax-Return/
├── Past-Areas/
│   └── Old-Job/
└── Old-Resources/
```

---

## The Inbox Workflow

### Daily Quick Review (5 minutes)

Process each file in `0-Inbox/` by asking:

```
┌─────────────────────────────────────┐
│         Is this actionable?         │
│     (has deadline or outcome?)      │
└─────────────────────────────────────┘
              │
    ┌─────────┴─────────┐
   YES                  NO
    │                   │
    ▼                   ▼
1-Projects      Is it an ongoing
                responsibility?
                    │
          ┌─────────┴─────────┐
         YES                  NO
          │                   │
          ▼                   ▼
      2-Areas        Is it useful
                     reference?
                        │
              ┌─────────┴─────────┐
             YES                  NO
              │                   │
              ▼                   ▼
         3-Resources         DELETE or
                           keep in Inbox
```

### Weekly Deep Review (15 minutes)

1. **Clear Inbox**: Process any remaining items in `0-Inbox/`
2. **Review Projects**:
   - Are any projects complete? → Move to `4-Archive/`
   - Any stalled projects? → Decide: continue or archive
3. **Check Areas**:
   - Any areas no longer relevant? → Move to `4-Archive/`
   - Any new responsibilities? → Create new area folder
4. **Tidy Resources**:
   - Any duplicates?
   - Any resources better organized elsewhere?

---

## File Naming with PARA

**Format**: `YYYY-MM_CODE_description.ext`

The CODE maps to PARA categories:

| Code | Meaning | Example |
|------|---------|---------|
| PROJ | Active project | `2025-01_PROJ_website-mockup.fig` |
| FIN | Finance area | `2025-01_FIN_tax-statement.pdf` |
| HEALTH | Health area | `2025-01_HEALTH_lab-results.pdf` |
| REF | Reference material | `2025-01_REF_react-tutorial.pdf` |

Or use specific codes like client names, course numbers, or project names.

---

## Migration from Old Structure

If upgrading from a previous folder structure:

| Old Location | New Location |
|--------------|--------------|
| WORK/ | 1-Projects/ or 2-Areas/ |
| DOCUMENTS/Financial/ | 2-Areas/Finance/ |
| DOCUMENTS/Legal/ | 2-Areas/Legal/ |
| PERSONAL/Health/ | 2-Areas/Health/ |
| MEDIA/ | 3-Resources/Media/ |
| SOFTWARE/ | 3-Resources/Tools/ |
| REFERENCE/ | 3-Resources/Learning/ |
| _REVIEW/ | 0-Inbox/_REVIEW/ |
| _RECENT/ | 0-Inbox/ |

---

## Common Questions

### Should I use subfolders?

Start simple. Add subfolders only when a folder grows too large to scan quickly (roughly 20+ items).

### Where do photos go?

`3-Resources/Media/` - They're reference materials. If photos are part of an active project, keep them in the project folder until completion.

### What about software installers?

`3-Resources/Tools/` - You reference them when needed, but they're not active work.

### Can I have both a Project and an Area for the same thing?

Yes! Example: "Taxes" could be:
- `1-Projects/2025-Tax-Return/` - This year's active filing
- `2-Areas/Finance/Taxes/` - Ongoing tax-related responsibilities

---

## Further Reading

- [Building a Second Brain](https://www.buildingasecondbrain.com/) by Tiago Forte
- [The PARA Method](https://fortelabs.com/blog/para/) - Original blog post
- [Forte Labs](https://fortelabs.com/) - More productivity resources
