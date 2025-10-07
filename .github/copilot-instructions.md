# Copilot Instructions for FUNding Friday Repository

## About This Repository

This repository contains information about FUNding Friday (FF), an annual mini-grant competition held during ESIP's July Meeting. The repository includes:

- Documentation about the program rules, eligibility, and procedures
- Historical records of award winners from 2010-2024
- Artifacts (PDFs) from funded projects organized by year
- Images of project posters organized by year

## Repository Structure

- `README.md` - Main documentation for the FUNding Friday program
- `award-winners/` - JSON files containing award winner data by year (2010-2024)
- `artifacts/` - Project deliverables and documentation organized by year (2008-2011)
- `img/` - Project poster images organized by year

## Data Format Standards

### Award Winners JSON Structure
Award winner files follow this format:
```json
{
    "Name or Team Name": {
        "funding-cycle": 2024,
        "title": "Project Title",
        "desc": "Project description",
        "image": "https://github.com/ESIPFed/funding-friday/blob/main/img/YEAR/filename.jpg",
        "co-pi": ["Name 1", "Name 2"],
        "docs": []
    }
}
```

Key fields:
- `funding-cycle`: Year the award was given (integer)
- `title`: Full project title
- `desc`: Project description (can be empty string)
- `image`: Full GitHub URL to poster image
- `co-pi`: Array of co-principal investigator names (can be empty array)
- `docs`: Array of document links (can be empty array)

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

## File Organization Guidelines

- Award winner JSON files are named by year: `YYYY.json`
- Images are organized in `img/YYYY/` directories
- Artifacts are organized in `artifacts/YYYY/` directories
- Use consistent naming conventions: `Name-Title-Year.jpg` or `Project-Title-ff-year.pdf`

## When Making Changes

- Verify data accuracy for award amounts, dates, and eligibility rules
- Maintain consistency across all JSON files when updating the schema
- Ensure image URLs use the correct GitHub path format
- Test that all links and references are valid
- Preserve historical accuracy - don't modify past award data without good reason
