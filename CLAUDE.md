# CLAUDE.md

## Project overview
This repository contains a static professional website for a researcher. The site is designed to present a scholarly identity with a strong emphasis on credibility, clarity, and accessibility.

The project is intentionally lightweight: plain HTML/CSS with a few structured data files rather than a framework-heavy setup. This makes it easy to maintain and suitable for academic or research profiles.

## Core goals
- Present the researcher as a serious, polished academic professional.
- Highlight expertise, publications, teaching, and impact clearly.
- Maintain a consistent visual identity across all pages.
- Keep the site easy to update without requiring a build toolchain.
- Support responsive viewing on desktop, tablet, and mobile devices.

## Site structure
- `index.html` — homepage and primary profile overview
- `publications.html` — publication list and filters
- `teaching.html` — courses, mentorship, and instructional work
- `publications.json` — structured publication dataset
- `publications_field_reference.md` — schema and field definitions
- `media/` — images, CVs, videos, and assets
- `README.md` — project notes and usage summary

## Design direction
Use a professional academic aesthetic:
- dark navy / slate background with restrained blue accent colors
- clean sans-serif typography for body text
- bold, editorial headings for strong researcher branding
- generous whitespace and structured cards for readability
- subtle grid textures or minimal visual motifs for sophistication

The current design language should be preserved unless a broader rebrand is requested.

## Content principles
The site should feel like a modern faculty or researcher profile, not a startup landing page.

Prioritize:
- concise biography with research focus
- clear expertise tags
- publication chronology or grouping by type
- teaching responsibilities and mentoring
- CV or downloadable résumé access
- links to scholarly profiles, labs, code, or funding pages when relevant

Avoid:
- excessive marketing language
- novelty copy or gimmicky animations
- generic filler text
- visual clutter or overly saturated color schemes

## Content and data workflow
### Publications
Publications should generally be managed in `publications.json` rather than hard-coded ad hoc into HTML where possible.

The project includes a field reference document to guide valid entries:
- title
- authors
- venue
- year
- type
- abstract or summary
- links or DOI values
- tags or keywords

Keep publication entries accurate, consistent, and scholarly in tone.

### Homepage
The homepage should communicate:
- full name and title
- research area
- short bio
- key expertise tags
- primary calls to action (e.g., publications, CV, contact)
- optional highlight metrics or selected achievements

### Teaching page
The teaching page should focus on:
- current and past courses
- course descriptions
- level and format
- mentoring or advising activities
- student-facing value and instructional approach

### Media and assets
Use `media/` for:
- CV PDFs
- headshots
- academic images
- lecture or talk recordings
- project visuals

Be careful to keep file names consistent and professional.

## Technical standards
- Keep changes lightweight and static-file friendly.
- Prefer semantic HTML sections, headings, and navigation patterns.
- Use accessible labels, alt text, and meaningful structure.
- Maintain consistent class naming and site-wide spacing.
- Preserve responsiveness and avoid introducing layout breakpoints that harm mobile usability.
- If adding assets, ensure they are optimized and referenced correctly.

## Acceptance criteria for updates
A change is complete when:
- content is accurate and professionally written
- styling remains aligned with the academic aesthetic
- the page remains responsive and usable on smaller screens
- navigation and links are functional
- no placeholder or lorem ipsum content remains
- publication data is internally consistent with the JSON schema

## Recommended workflow for future edits
1. Update the relevant content file first.
2. Verify the correct section and page structure.
3. Maintain consistency with the existing visual system.
4. Confirm links, metadata, and page titles are correct.
5. Check the page in a browser for readability and layout integrity.

## Example tasks
### Add a new publication
- edit `publications.json`
- use the schema in `publications_field_reference.md`
- ensure authors, venue, year, and links are correctly formatted
- verify the publication appears correctly on `publications.html`

### Update the research bio
- edit the relevant section in `index.html`
- keep voice concise, credible, and grounded in expertise
- avoid overpromising or inflated language

### Add a teaching course
- update `teaching.html`
- include course title, description, and level
- keep structure consistent with the existing course cards

## Current implementation notes
This site is already a strong base for a researcher profile. Preserve the established design language and quality bar rather than replacing it with a generic template.

The project favors polished, minimal, and credible presentation over flashy interaction. For an academic audience, clarity and trust are the primary design priorities.
