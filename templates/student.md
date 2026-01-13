# Student Template (PARA Method)

Course and semester-based structure for students using PARA.

## Folder Structure

```
Target-Directory/
├── 0-Inbox/                    # Unsorted downloads
│   └── _REVIEW/
├── 1-Projects/                 # Current semester courses (time-bound!)
│   ├── CS101-Intro-Programming/
│   │   ├── Assignments/
│   │   ├── Labs/
│   │   └── Notes/
│   ├── MATH201-Calculus/
│   ├── ENG102-Writing/
│   └── Research/
│       ├── Thesis/
│       └── Papers/
├── 2-Areas/                    # Ongoing academic responsibilities
│   ├── Applications/          # Jobs, grad school, internships
│   ├── Financial-Aid/
│   ├── Extracurriculars/
│   └── Career/
│       ├── Resume/
│       └── Portfolio/
├── 3-Resources/
│   ├── Media/
│   │   └── Screenshots/
│   ├── Tools/
│   │   └── Software/
│   ├── Learning/
│   │   ├── Textbooks/
│   │   ├── Lecture-Notes/
│   │   └── Study-Guides/
│   └── Templates/
│       ├── Lab-Reports/
│       └── Essays/
└── 4-Archive/
    ├── Past-Semesters/
    │   ├── Fall-2024/
    │   └── Spring-2024/
    └── Completed-Research/
```

## Why Courses are Projects

In PARA, **Projects have deadlines** - and courses end each semester. This makes them Projects, not Areas. At the end of each semester, move course folders to Archive.

## Project Codes

```yaml
project_codes:
  # Courses (update each semester)
  CS101: "Intro to Programming"
  MATH201: "Calculus II"
  ENG102: "Academic Writing"
  PHYS101: "Physics I"

  # Other
  RESEARCH: "Research Project"
  THESIS: "Thesis"
  APPS: "Applications"
```

## Detection Keywords

```yaml
categories:
  1-Projects:
    - assignment
    - homework
    - hw
    - problem set
    - pset
    - lab
    - project
    - draft
    - final

  2-Areas/Applications:
    - resume
    - cv
    - cover letter
    - application
    - interview

  3-Resources/Learning:
    - syllabus
    - lecture
    - slides
    - textbook
    - chapter
    - study guide
    - notes
```

## Semester Workflow

### During Semester
- New downloads → 0-Inbox
- Course materials → 1-Projects/[COURSE]/
- Reference materials → 3-Resources/Learning/

### End of Semester
1. Move all course folders from `1-Projects/` to `4-Archive/Past-Semesters/[Semester]/`
2. Keep only ongoing research in 1-Projects

### New Semester
1. Create new course folders in `1-Projects/`
2. Update project codes in config

## Naming Convention

`COURSE_assignment-name.ext`

Examples:
- `CS101_hw3-sorting-algorithms.py`
- `MATH201_midterm-study-guide.pdf`
- `ENG102_essay-draft-v2.docx`
