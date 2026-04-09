# CLAUDE.md — FUNding Friday Repository

## What this repository is

This is the historical record of **FUNding Friday (FF)**, an annual mini-grant competition held at ESIP's July Meeting since 2008. Award winners receive $5,000 (attendees) or $3,000 (students/educators) to complete a project within one year.

## Repository structure

```
funding-friday/
├── awards.json          ← Single source of truth for all award winners (2010–present)
├── README.md            ← Program rules and procedures (audience: applicants/participants)
├── CONTRIBUTING.md      ← How to add or update records (audience: contributors)
├── img/YYYY/            ← Poster images, PNG only, named FirstName-LastName-YYYY.png
├── artifacts/YYYY/      ← Project PDFs, named Project-Name-ff-YYYY.pdf
└── award-winners/       ← Legacy per-year JSON files (2010–2024); do not edit these
```

## Primary data file: awards.json

`awards.json` is a JSON array of award records. Each record:

```json
{
  "year": 2025,
  "name": "Jane Smith",
  "title": "Project Title",
  "desc": "1–3 sentence description of the project.",
  "co_pi": ["Co-PI Name"],
  "image": "img/2025/Jane-Smith-2025.png",
  "docs": ["artifacts/2025/Project-Title-ff-2025.pdf"],
  "funding_amount": 5000,
  "participant_type": "attendee"
}
```

- `image` and `docs` use **relative paths from the repo root**, not full GitHub URLs
- `funding_amount`: `5000`, `3000`, or `null` if unknown
- `participant_type`: `"attendee"`, `"student"`, `"educator"`, or `""` if unknown
- `co_pi`: empty array `[]` if none
- `desc`: empty string `""` for ~57 records from 2016–2024 — these need to be filled in

## Known data gaps

- **Descriptions missing:** `desc` is `""` for most records from 2016–2024. These should be filled in when source materials (posters, reports) are available.
- **Images missing:** No poster images for 2012–2013.
- **Artifacts sparse:** PDFs exist only for 2008–2011. Artifacts for 2020 include one PDF originally misplaced in `img/`.
- **funding_amount / participant_type:** `null`/`""` for all historical records — not captured in original data.

## Conventions

- Images must be PNG. Convert with: `sips -s format png input.jpg --out output.png`
- Image naming: `FirstName-LastName-YYYY.png` (lead PI's name, hyphens, no spaces)
- Artifact naming: `Project-Name-ff-YYYY.pdf`
- Do not edit files in `award-winners/` — that directory contains legacy data only
- Do not use full GitHub URLs in `image` or `docs` fields

## When adding a new year

1. Add poster PNGs to `img/YYYY/`
2. Add a record per winner to `awards.json`
3. Add any PDFs to `artifacts/YYYY/`
4. Fill in `desc`, `funding_amount`, and `participant_type` — do not leave them blank for new records

## GitHub Issue template

`.github/ISSUE_TEMPLATE/new-award.yml` provides a form for contributors to submit new award data without editing JSON directly.
