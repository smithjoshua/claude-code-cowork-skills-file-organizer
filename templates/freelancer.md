# Freelancer Template

Client-based folder structure for freelancers and consultants.

## Folder Structure

```
Downloads/
├── _INBOX/              # Unsorted new downloads
├── _REVIEW/             # Files needing manual review
├── Clients/
│   ├── ACME/
│   ├── BigCorp/
│   └── StartupXYZ/
├── Contracts/
├── Invoices/
├── Resources/
│   ├── Templates/
│   ├── Stock-Assets/
│   └── References/
└── Archive/
    └── 2024/
```

## Project Codes

```yaml
project_codes:
  - ACME
  - BIGCORP
  - STARTUP
  - INTERNAL
```

## Detection Keywords

```yaml
categories:
  Contracts:
    - contract
    - agreement
    - nda
    - sow
    - proposal
  Invoices:
    - invoice
    - receipt
    - payment
    - billing
```

## Naming Convention

`YYYY-MM_CLIENT_description.ext`

Examples:
- `2024-01_ACME_website-mockups.fig`
- `2024-02_BIGCORP_quarterly-report.pdf`
