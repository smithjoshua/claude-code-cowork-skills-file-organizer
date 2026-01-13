# Family Template

Shared folder structure for family organization.

## Folder Structure

```
Downloads/
├── _INBOX/              # Unsorted new downloads
├── _REVIEW/             # Files needing manual review
├── Family-Photos/
│   ├── Events/
│   ├── Vacations/
│   └── Everyday/
├── Documents/
│   ├── Medical/
│   ├── Financial/
│   ├── Legal/
│   ├── School/
│   └── Home/
├── Recipes/
├── Kids/
│   ├── Artwork/
│   ├── School-Projects/
│   └── Activities/
├── Shopping/
│   ├── Receipts/
│   └── Wishlists/
└── Archive/
    └── 2024/
```

## Project Codes

```yaml
project_codes:
  - FAMILY
  - MEDICAL
  - FINANCIAL
  - SCHOOL
  - HOME
  - VACATION
```

## Detection Keywords

```yaml
categories:
  Medical:
    - medical
    - health
    - prescription
    - doctor
    - insurance
    - dental
  Financial:
    - bank
    - tax
    - statement
    - 401k
    - investment
    - budget
  Legal:
    - legal
    - court
    - will
    - deed
    - title
  School:
    - report card
    - permission
    - school
    - teacher
```

## Naming Convention

`YYYY-MM_CATEGORY_description.ext`

Examples:
- `2024-03_MEDICAL_annual-checkup.pdf`
- `2024-06_VACATION_italy-itinerary.pdf`

## Sensitive File Handling

Files in Medical, Financial, and Legal categories are automatically flagged for review before organizing.
