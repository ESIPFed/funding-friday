# Copilot Instructions for FUNding Friday Repository

## About This Repository

This repository contains information about FUNding Friday (FF), an annual mini-grant competition held during ESIP's July Meeting. The repository includes:

- Documentation about the program rules, eligibility, and procedures
- Historical records of award winners from 2010 to present
- Artifacts (PDFs) from funded projects organized by year
- Images of project posters organized by year

## Repository Structure

```
funding-friday/
├── awards.json          ← Single source of truth for all award winners
├── README.md            ← Program documentation
├── CONTRIBUTING.md      ← How to add or update records
├── img/YYYY/            ← Poster images (PNG only), named FirstName-LastName-YYYY.png
└── artifacts/YYYY/      ← Project PDFs, named Project-Name-ff-YYYY.pdf
```

The `award-winners/` directory contains the legacy per-year JSON files. `awards.json` is the current source of truth.

## Data Format Standards

### awards.json schema

Each record in `awards.json` is an object in a top-level array:

```json
{
  "year": 2025,
  "name": "Jane Smith",
  "title": "Project Title",
  "desc": "One to three sentence description of the project.",
  "co_pi": ["Co-PI Name"],
  "image": "img/2025/Jane-Smith-2025.png",
  "docs": ["artifacts/2025/Project-Title-ff-2025.pdf"],
  "funding_amount": 5000,
  "participant_type": "attendee"
}
```

Field rules:
- `year`: integer — the award year
- `name`: string — lead person's full name or team name
- `title`: string — project title as on the poster
- `desc`: string — project description; empty string `""` if unknown
- `co_pi`: array of strings — co-PI names; `[]` if none
- `image`: string — **relative path** from repo root (e.g., `img/2025/Name-2025.png`); `""` if no image
- `docs`: array of strings — relative paths to PDFs; `[]` if none
- `funding_amount`: integer or null — `5000` or `3000`; `null` if unknown
- `participant_type`: string — `"attendee"`, `"student"`, or `"educator"`; `""` if unknown

### Image standards
- Format: **PNG only**
- Location: `img/YYYY/FirstName-LastName-YYYY.png`
- `image` field in awards.json uses a relative path, not a full GitHub URL

### Artifact standards
- Format: PDF
- Location: `artifacts/YYYY/Project-Name-ff-YYYY.pdf`

## Documentation Style Guide

When editing the README:
- Use clear, professional language appropriate for a grant program
- Maintain the existing section structure
- Keep formatting consistent with existing markdown conventions
- Preserve bullet point formatting for lists
- Use proper heading hierarchy (##, ###, etc.)
- Maintain line breaks between sections
- Keep award amounts, dates, and rules accurate and up-to-date

## Key Program Details to Remember

- **Award Amounts**: $5,000 for meeting attendees, $3,000 for students/educators
- **Timing**: Annual competition at ESIP's July Meeting
- **Duration**: Projects completed within one year
- **Eligibility**: Previous year's awardees and ESIP leadership are ineligible
- **Tax Status**: Awards are taxable income to individuals
- **Payment Schedule**: Two installments (half at start, half at completion)
- **Requirements**: Hand-drawn poster, 2-minute pitch, project presentation

## When Making Changes

- Verify data accuracy for award amounts, dates, and eligibility rules
- Ensure image paths in awards.json are relative (not full GitHub URLs)
- Use PNG format for all images — convert if necessary with `sips -s format png input.jpg --out output.png`
- Preserve historical accuracy — don't modify past award data without good reason
- The `desc` field for 2016–2024 records is mostly empty and should be filled in when information is available
