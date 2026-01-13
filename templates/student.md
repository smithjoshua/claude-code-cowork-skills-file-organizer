# Student Template

Course and semester-based structure for students.

## Folder Structure

```
Downloads/
├── _INBOX/              # Unsorted new downloads
├── _REVIEW/             # Files needing manual review
├── Current-Semester/
│   ├── CS101-Intro-Programming/
│   ├── MATH201-Calculus/
│   ├── ENG102-Writing/
│   └── PHYS101-Physics/
├── Research/
│   ├── Papers/
│   ├── Sources/
│   └── Notes/
├── Assignments/
│   ├── Drafts/
│   └── Submitted/
├── Resources/
│   ├── Textbooks/
│   ├── Lecture-Slides/
│   └── Study-Guides/
└── Archive/
    ├── Fall-2024/
    └── Spring-2024/
```

## Project Codes

```yaml
project_codes:
  - CS101
  - MATH201
  - ENG102
  - PHYS101
  - RESEARCH
  - PERSONAL
```

## Detection Keywords

```yaml
categories:
  Assignments:
    - assignment
    - homework
    - hw
    - problem set
    - pset
    - lab
  Research:
    - paper
    - journal
    - study
    - research
    - thesis
  Resources:
    - syllabus
    - lecture
    - slides
    - textbook
    - chapter
```

## Naming Convention

`COURSE_assignment-name.ext`

Examples:
- `CS101_hw3-sorting-algorithms.py`
- `MATH201_midterm-study-guide.pdf`
