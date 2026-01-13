# Family Template (PARA Method)

Shared folder structure for family organization using PARA.

## Folder Structure

```
Target-Directory/
├── 0-Inbox/                    # Unsorted downloads
│   └── _REVIEW/
├── 1-Projects/                 # Active family projects
│   ├── Vacations/             # Trip planning
│   │   └── [Trip-Name]/
│   ├── Home-Improvement/
│   │   └── [Project-Name]/
│   ├── Events/                # Birthdays, holidays
│   │   └── [Event-Name]/
│   └── Kids-Projects/
│       └── [Project-Name]/
├── 2-Areas/                    # Ongoing family responsibilities
│   ├── Finance/
│   │   ├── Banking/
│   │   ├── Taxes/
│   │   ├── Budget/
│   │   └── Insurance/
│   ├── Medical/
│   │   ├── Records/
│   │   ├── Insurance/
│   │   └── Prescriptions/
│   ├── Legal/
│   │   ├── Wills/
│   │   ├── Deeds/
│   │   └── Contracts/
│   ├── School/
│   │   ├── Report-Cards/
│   │   ├── Permissions/
│   │   └── Schedules/
│   ├── Home/
│   │   ├── Warranties/
│   │   ├── Maintenance/
│   │   └── Manuals/
│   └── Vehicles/
│       ├── Registration/
│       └── Maintenance/
├── 3-Resources/
│   ├── Media/
│   │   ├── Family-Photos/
│   │   │   ├── Events/
│   │   │   ├── Vacations/
│   │   │   └── Everyday/
│   │   └── Videos/
│   ├── Recipes/
│   ├── Kids-Artwork/
│   ├── Shopping/
│   │   ├── Receipts/
│   │   └── Wishlists/
│   └── Templates/
│       └── Forms/
└── 4-Archive/
    ├── Past-Years/
    │   └── [YYYY]/
    ├── Completed-Projects/
    └── Old-School/
```

## Project Codes

```yaml
project_codes:
  # Projects
  VACATION: "Vacation Planning"
  HOME: "Home Improvement"
  EVENT: "Family Event"
  KIDS: "Kids Project"

  # Areas
  FIN: "Finance"
  MEDICAL: "Medical"
  LEGAL: "Legal"
  SCHOOL: "School"
```

## Detection Keywords

```yaml
categories:
  2-Areas/Finance:
    - bank
    - tax
    - statement
    - 401k
    - investment
    - budget
    - insurance
    - bill

  2-Areas/Medical:
    - medical
    - health
    - prescription
    - doctor
    - dental
    - vision
    - insurance

  2-Areas/Legal:
    - legal
    - court
    - will
    - deed
    - title
    - contract

  2-Areas/School:
    - report card
    - permission
    - school
    - teacher
    - grade
```

## Inbox Review for Families

### Daily (5 min)
- Sort new downloads by category
- File bills and statements → 2-Areas/Finance
- Move photos → 3-Resources/Media/Family-Photos

### Weekly (15 min)
- Process school papers → 2-Areas/School
- File receipts → 3-Resources/Shopping/Receipts
- Archive completed event/vacation projects

### Yearly
- Move tax documents to 4-Archive/Past-Years/[YYYY]
- Archive old school records
- Review and purge old receipts

## Naming Convention

`YYYY-MM_CATEGORY_description.ext`

Examples:
- `2025-03_MEDICAL_annual-checkup.pdf`
- `2025-06_VACATION_italy-itinerary.pdf`
- `2025-01_FIN_tax-return.pdf`

## Sensitive File Handling

Files in these locations require review approval:
- `2-Areas/Medical/` - Health records, prescriptions
- `2-Areas/Finance/` - Bank statements, tax documents
- `2-Areas/Legal/` - Wills, deeds, contracts

**Never auto-move files containing:**
- Social Security Numbers
- Account numbers
- Medical diagnosis information
