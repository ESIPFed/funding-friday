# Contributing to FUNding Friday

Thank you for helping keep this record of FUNding Friday award winners up to date. This guide explains how to add or update records.

## What's in this repository

| Path | Purpose |
|---|---|
| `awards.json` | Single source of truth — all award winners from 2010 to present |
| `img/YYYY/` | Poster images (PNG only), one per award winner |
| `artifacts/YYYY/` | Project deliverables and statements of work (PDF) |

## Adding a new year's award winners

### 1. Add poster images

Place each winner's poster image in `img/YYYY/` (replace `YYYY` with the award year):

- **Format:** PNG only
- **Naming:** `FirstName-LastName-YYYY.png`
  - Use the lead person's name (the principal investigator)
  - For team entries without a single lead, use a short team identifier: `Team-Name-YYYY.png`
  - Remove spaces, use hyphens
  - Example: `Jane-Smith-2025.png`

If you have a JPG or JPEG, convert it to PNG before adding it. On macOS:
```bash
sips -s format png photo.jpg --out photo.png
```

### 2. Add records to `awards.json`

Open `awards.json` and add a new object to the array for each winner. All fields are required; use `""` or `[]` if a value is not yet known.

```json
{
  "year": 2025,
  "name": "Jane Smith",
  "title": "Project Title",
  "desc": "One or two sentence description of what the project does or aims to achieve.",
  "co_pi": ["Co-Investigator Name"],
  "image": "img/2025/Jane-Smith-2025.png",
  "docs": ["artifacts/2025/Project-Title-ff-2025.pdf"],
  "funding_amount": 5000,
  "participant_type": "attendee"
}
```

#### Field reference

| Field | Type | Description |
|---|---|---|
| `year` | integer | The year the award was given (e.g., `2025`) |
| `name` | string | Full name of the lead person or team name |
| `title` | string | Project title as presented on the poster |
| `desc` | string | Short description of the project (1–3 sentences). **Please fill this in** — it is the most important field for discoverability. |
| `co_pi` | array of strings | Full names of all co-investigators. Use `[]` if none. |
| `image` | string | Relative path to the poster image: `img/YYYY/Name-YYYY.png`. Use `""` if no image. |
| `docs` | array of strings | Relative paths to any PDFs in `artifacts/`: `["artifacts/YYYY/Project-ff-YYYY.pdf"]`. Use `[]` if none. |
| `funding_amount` | integer or null | Award amount in USD: `5000` for attendees, `3000` for students/educators. Use `null` if unknown. |
| `participant_type` | string | `"attendee"`, `"student"`, or `"educator"`. Use `""` if unknown. |

### 3. Add project artifacts (optional)

If a statement of work, final report, or other project document is available, place the PDF in `artifacts/YYYY/` and add the path to the `docs` array in `awards.json`.

- **Naming:** `Project-Name-ff-YYYY.pdf`
- **Example:** `artifacts/2025/Cool-Project-ff-2025.pdf`

### 4. Submit a pull request

1. Fork this repository
2. Create a branch: `git checkout -b add-2025-winners`
3. Make your changes
4. Open a pull request with a short description of what you added

## Filling in missing descriptions

The `desc` field is empty for many records from 2016–2024. If you have access to the original poster or know what the project was about, please fill it in. Even a single sentence helps. Submit a pull request with the updated `awards.json`.

## Questions?

Open an issue using the [New Award Winner](../../issues/new?template=new-award.yml) template, or file a general issue if something looks wrong.
