# publications.json — Field Reference

Since JSON doesn't support comments natively, keep this file alongside
publications.json as your reference when adding new entries.

---

## TEMPLATE — copy this block for each new publication

```json
{
  "id": "",
  "type": "",
  "title": "",
  "authors": [],
  "year": 0,
  "venue": "",
  "volume": "",
  "issue": "",
  "pages": "",
  "month": "",
  "location": "",
  "pdf": "",
  "doi": "",
  "arxiv": "",
  "citation_count": null,
  "abstract": "",
  "keywords": [],
  "bibtex": ""
}
```

---

## FIELD DEFINITIONS

### id
- **Type:** string
- **Required:** yes
- **Usage:** Internal unique identifier. Used by JavaScript to reference entries.
- **Rules:** Lowercase, no spaces, use hyphens. Must be unique across all entries.
- **Example:** `"conf-cdc-2024-formation"`

---

### type
- **Type:** string (enum)
- **Required:** yes
- **Usage:** Controls badge color and filter tabs on the publications page.
- **Allowed values:**
  - `"journal"` — blue badge
  - `"conference"` — green badge
  - `"book_chapter"` — purple badge
  - `"thesis"` — gray badge
- **Example:** `"conference"`

---

### title
- **Type:** string
- **Required:** yes
- **Usage:** Displayed as the publication heading.
- **Example:** `"Robust Formation Control of Satellite Systems"`

---

### authors
- **Type:** array of strings
- **Required:** yes
- **Usage:** Displayed below the title. Your name (S. Phillips) is automatically bolded by the renderer.
- **Example:** `["S. Phillips", "R. G. Sanfelice"]`

---

### year
- **Type:** integer
- **Required:** yes
- **Usage:** Shown in the left column. Used for sorting (newest first) and year filter buttons.
- **Example:** `2024`

---

### venue
- **Type:** string
- **Required:** yes
- **Usage:** Shown in italics below authors. Use full journal or conference name.
- **Example:** `"IEEE Transactions on Automatic Control"` or `"AIAA SciTech Forum"`

---

### volume
- **Type:** string
- **Required:** no (journal only)
- **Usage:** Shown as part of journal citation metadata. Leave `""` for conferences.
- **Example:** `"63"`

---

### issue
- **Type:** string
- **Required:** no (journal only)
- **Usage:** Journal issue number. Leave `""` if not applicable.
- **Example:** `"4"`

---

### pages
- **Type:** string
- **Required:** no
- **Usage:** Page range, shown in citation metadata.
- **Example:** `"973–988"` (use an en dash –, not a hyphen -)

---

### month
- **Type:** string
- **Required:** no
- **Usage:** Month of publication, shown in citation metadata.
- **Example:** `"July"`

---

### location
- **Type:** string
- **Required:** no (conference only)
- **Usage:** City and country/state of the conference. Leave `""` for journals.
- **Example:** `"Cancun, Mexico"`

---

### pdf
- **Type:** string (URL)
- **Required:** no
- **Usage:** Renders a "PDF ↗" link. Can be a preprint, author copy, or direct link.
- **Leave blank:** `""` if no PDF is available.
- **Example:** `"https://seanaphillipscom.wordpress.com/wp-content/uploads/2019/10/phillips.auto_.16.pdf"`

---

### doi
- **Type:** string (DOI only, not full URL)
- **Required:** no
- **Usage:** Renders as a "DOI ↗" link pointing to `https://doi.org/{doi}`.
- **Leave blank:** `""` if unknown.
- **Example:** `"10.1109/TAC.2017.2748519"`

---

### arxiv
- **Type:** string (full URL)
- **Required:** no
- **Usage:** Renders an "arXiv ↗" link.
- **Leave blank:** `""` if no arXiv preprint exists.
- **Example:** `"https://arxiv.org/abs/2302.14188"`

---

### citation_count
- **Type:** integer or null
- **Required:** no
- **Usage:** Shown as a small badge, e.g. "cited 42×". Update periodically from Google Scholar.
- **Leave blank:** `null` (not `""`) if unknown.
- **Example:** `42`

---

### abstract
- **Type:** string
- **Required:** no
- **Usage:** Shown in an expandable dropdown when the user clicks the entry.
- **Leave blank:** `""` if not added yet.
- **Example:** `"We present a hybrid observer design for..."`

---

### keywords
- **Type:** array of strings
- **Required:** no
- **Usage:** Rendered as tags. Used by the keyword filter on the publications page.
- **Tips:** Use lowercase, keep consistent across papers (e.g. always "hybrid systems" not sometimes "hybrid" or "Hybrid Systems").
- **Example:** `["hybrid systems", "robust control", "multi-agent systems"]`

---

### bibtex
- **Type:** string
- **Required:** no (but strongly recommended)
- **Usage:** Shown in a copy-to-clipboard modal when the user clicks "Cite ↗".
- **Tips:** Use `\n` for newlines within the JSON string. Escape any backslashes as `\\`.
- **Example:**
```
"@article{phillips2019automatica,\n  author = {Sean Phillips and Ricardo G. Sanfelice},\n  title  = {Robust Distributed Synchronization...},\n  journal = {Automatica},\n  year   = {2019}\n}"
```

---

## SORTING & FILTERING BEHAVIOR

- **Default sort:** newest year first, then alphabetical by title within the same year.
- **Filter tabs:** All | Journal | Conference | Book Chapter | Thesis | (year buttons auto-generated from data)
- **Keyword filter:** Searches across `title`, `authors`, `keywords`, and `abstract`.

---

## TIPS FOR ADDING A NEW PAPER

1. Copy the template block at the top of this file.
2. Fill in all required fields: `id`, `type`, `title`, `authors`, `year`, `venue`.
3. Add optional fields as available — at minimum add `pdf` or `doi` so readers can access the paper.
4. Add the `bibtex` string so the Cite button works.
5. Paste the new object into `publications.json`. New entries go at the **top** of the array.
6. Save. The site re-renders automatically — no other files need to change.
