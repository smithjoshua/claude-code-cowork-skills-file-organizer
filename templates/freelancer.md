# Freelancer Template (PARA Method)

Client-based organization using the PARA methodology for freelancers and consultants.

## Folder Structure

```
Target-Directory/
├── 0-Inbox/                    # Unsorted downloads
│   └── _REVIEW/
├── 1-Projects/                 # Active client projects
│   ├── Clients/
│   │   ├── ACME/
│   │   ├── BigCorp/
│   │   └── StartupXYZ/
│   └── Internal/               # Your own business projects
├── 2-Areas/                    # Ongoing business operations
│   ├── Finance/
│   │   ├── Invoices/
│   │   ├── Expenses/
│   │   └── Taxes/
│   ├── Legal/
│   │   ├── Contracts/
│   │   └── NDAs/
│   ├── Marketing/
│   └── Admin/
├── 3-Resources/                # Business resources
│   ├── Media/
│   │   └── Stock-Assets/
│   ├── Tools/
│   ├── Templates/
│   │   ├── Proposals/
│   │   ├── Contracts/
│   │   └── Invoices/
│   └── Learning/
└── 4-Archive/
    ├── Completed-Projects/
    └── Past-Clients/
```

## Project Codes

```yaml
project_codes:
  # Clients (add your own)
  ACME: "Acme Corporation"
  BIGCO: "Big Company Inc"
  STARTUP: "StartupXYZ"

  # Internal
  BIZ: "Business Operations"
  MKTG: "Marketing"

  # Areas
  FIN: "Finance"
  LEGAL: "Legal"
```

## Detection Keywords

```yaml
categories:
  1-Projects:
    - project
    - deliverable
    - milestone
    - draft
    - revision
    - mockup
    - wireframe

  2-Areas/Finance:
    - invoice
    - payment
    - receipt
    - expense
    - tax
    - 1099
    - w9

  2-Areas/Legal:
    - contract
    - agreement
    - nda
    - sow
    - proposal
    - terms
```

## Inbox Review for Freelancers

### Daily (5 min)
- Process client deliverables → 1-Projects/Clients/[name]
- File invoices and receipts → 2-Areas/Finance
- Move reference materials → 3-Resources

### Weekly (15 min)
- Archive completed client projects
- Update contract/invoice tracking
- Review proposals and follow-ups

### End of Project
Move entire client folder from `1-Projects/Clients/` to `4-Archive/Completed-Projects/`

## Naming Convention

`YYYY-MM_CLIENT_description.ext`

Examples:
- `2025-01_ACME_website-mockups.fig`
- `2025-01_BIGCO_quarterly-report.pdf`
- `2025-01_BIZ_invoice-0042.pdf`

## Sensitive Files

Files in these locations require review approval:
- `2-Areas/Finance/` (financial data)
- `2-Areas/Legal/` (contracts, agreements)
