# Organization Templates

Initialize these files in the `_ORG/` folder before starting.

---

## _PLAN.md Template

```markdown
# Downloads Organization Plan

**Created**: [TIMESTAMP]
**Last Updated**: [TIMESTAMP]
**Status**: ⬜ Not Started

---

## Overview

**Target Folder**: ~/Downloads
**Total Files Found**: [pending scan]

---

## Phase 1: Discovery & Inventory

| Task | Status | Started | Completed | Notes |
|------|--------|---------|-----------|-------|
| 1.1 List all files | ⬜ | - | - | |
| 1.2 Count by extension | ⬜ | - | - | |
| 1.3 Identify date range | ⬜ | - | - | |
| 1.4 Flag large files (>100MB) | ⬜ | - | - | |
| 1.5 Flag sensitive files | ⬜ | - | - | |
| 1.6 Assess filename quality | ⬜ | - | - | |

---

## Phase 2: Content Analysis

| Task | Status | Started | Completed | Notes |
|------|--------|---------|-----------|-------|
| 2.1 Analyze documents | ⬜ | - | - | |
| 2.2 Analyze images | ⬜ | - | - | |
| 2.3 Analyze spreadsheets | ⬜ | - | - | |
| 2.4 Generate proposed renames | ⬜ | - | - | |
| 2.5 Present for approval | ⬜ | - | - | ⚠️ CHECKPOINT |

---

## Phase 3: Preparation

| Task | Status | Started | Completed | Notes |
|------|--------|---------|-----------|-------|
| 3.1 Create folder structure | ⬜ | - | - | |
| 3.2 User approval checkpoint | ⬜ | - | - | ⚠️ REQUIRED |

---

## Phase 4: Execution

| Task | Status | Started | Completed | Notes |
|------|--------|---------|-----------|-------|
| 4.1 Rename approved files | ⬜ | - | - | |
| 4.2 Move HIGH confidence | ⬜ | - | - | |
| 4.3 Move MEDIUM confidence | ⬜ | - | - | |
| 4.4 Move LOW → _REVIEW | ⬜ | - | - | |
| 4.5 Handle duplicates | ⬜ | - | - | |
| 4.6 Handle large files | ⬜ | - | - | |

---

## Phase 5: Completion

| Task | Status | Started | Completed | Notes |
|------|--------|---------|-----------|-------|
| 5.1 Generate summary | ⬜ | - | - | |
| 5.2 Finalize manifest | ⬜ | - | - | |

---

## Final Summary

| Metric | Count |
|--------|-------|
| Total files processed | - |
| Files renamed | - |
| Files moved | - |
| Files in _REVIEW | - |
| Errors | - |
```

---

## _LOG.md Template

```markdown
# Downloads Organization Log

**Session Started**: [TIMESTAMP]
**Target Folder**: ~/Downloads

---

## Session Log

### [TIMESTAMP] - SESSION
**Action**: Organization session started
**Target**: ~/Downloads
**Next**: Begin Phase 1 discovery

---

<!-- Add entries as you work -->

---

## Error Summary

| Timestamp | File | Error | Resolution |
|-----------|------|-------|------------|
| (none) | - | - | - |

---

## Notes & Observations

- [Patterns noticed]
- [Suggestions for future]
```

---

## _MANIFEST.md Template

```markdown
# Downloads Organization Manifest

**Session**: [TIMESTAMP]
**Plan**: `_PLAN.md`
**Log**: `_LOG.md`

---

## Pre-Organization Inventory

| Extension | Count |
|-----------|-------|
| .pdf | - |
| .docx | - |
| .jpg/.png | - |
| Other | - |

---

## Content Analysis Results

| # | Original Name | Content Found | Proposed Name | Confidence | Approved |
|---|---------------|---------------|---------------|------------|----------|
| 1 | | | | | ⬜ |

---

## File Operations

### Renames

| # | Timestamp | Original | New Name | Status |
|---|-----------|----------|----------|--------|
| 1 | | | | ⬜ |

### Moves

| # | Timestamp | Filename | From | To | Status |
|---|-----------|----------|------|-----|--------|
| 1 | | | | | ⬜ |

---

## Statistics

| Metric | Count |
|--------|-------|
| Files renamed | - |
| Files moved | - |
| Errors | - |

---

## Rollback Information

To undo: Reference the Renames and Moves tables above.
```

---

## _CONFIG.md Template

See references/config.md for full configuration options.
