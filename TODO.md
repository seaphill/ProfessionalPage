# To-Do List

Outstanding items from the site rebuild. Two sections: things only Sean can
resolve (real accounts, data, judgment calls), and a running backlog of
requests for Claude to pick up in a future session.

---

## To-Dos (Sean)


- [ ] Test the Contact form end to end (Formspree, form ID `mlgvbydq`) to confirm submissions actually arrive — not verified this session.

---

## Feedback / To-Dos for Claude

Add notes here anytime — next session, ask Claude to read this file and work
through it.

- [X] Look up and add DOIs / PDF links / BibTeX for the 42 publications added from the CV in `publications.json` — done via the CrossRef and arXiv APIs: 26 got a verified DOI + real BibTeX (cross-checked by title, author, type, and year to rule out false matches — one near-miss was caught this way and corrected before writing), plus 2 more got arXiv links. 14 had no record on either service and are still blank; likely either not yet indexed or the CV's title differs slightly from the final published one. Worth a manual Google Scholar check if you want those filled in too: `journal-jgcd-2025-rpo-safety-under-review`, `journal-nahs-2026-saver-tubes-under-review`, `journal-tcns-2026-omniscience-under-review`, `conf-aas-2026-boundary-fitting`, `conf-gnc-2026-blender-imagery`, `conf-gnc-2026-passive-imagery-pose`, `conf-nato-2026-hybrid-architecture`, `conf-gnc-2025-trusted-autonomy-demo`, `conf-gnc-2025-multiagent-benchmark`, `conf-gnc-2024-sensor-tasking`, `conf-gnc-2024-resource-management`, `conf-gnc-2024-drl-stability-testbed`, `conf-aas-2022-sliding-mode-charlotte`, `conf-aas-2022-observability-function`.
- [X] Add a `.gitignore` entry for `.DS_Store` — done, and also untracked the two already-committed copies (`git rm --cached`), since a `.gitignore` entry alone doesn't stop already-tracked files from showing as modified. Committed as `e684cb4`.
- [ ] Adjust the organization of the publications page so that theses and book chapters are first
- [ ] Remove journals that are under review or under development from the publication list JSON file

---

## Future Development

Larger, optional builds — not urgent, worth doing only if you decide you want
the capability. Ask Claude to scope and build one of these when you're ready.

- [ ] **Hosted, GitHub-connected publication editor.** Replace (or supplement) the local-only `admin/add-publication.html` tool with a real web-based CMS — e.g. Decap CMS — that you log into from any browser, anywhere, via GitHub auth, and that commits new publication entries straight to the repo. No local file downloads, no manual git push. Requires real setup: registering an OAuth app (or using a hosted auth proxy), adding a CMS config file, and testing that it deploys cleanly alongside GitHub Pages. Current tool works fine for occasional local edits; this is only worth it if you want to add papers from your phone or a machine without the repo cloned.