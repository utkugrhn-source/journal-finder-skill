---
name: journal-finder
description: Find and shortlist target journals for a manuscript. Use when asked "which journal should I submit to", "suggest journals", or "find a new journal after a desk rejection". Runs publisher journal-finder tools first, merges the candidates, then verifies indexing, JCR quartile, fees and speed from primary sources before recommending a shortlist.
---

# Journal Finder

Recommend target journals the way a careful senior author would: **let the publishers' own matching tools generate candidates, then filter them hard against verified facts.** Never start from the model's memory of "good journals", and never state a metric that was not read from a source in this session.

The author makes the final choice. You recommend; you do not pick, and you do not submit.

## Step 0 — Gather inputs before searching

Ask for (or read from the project files) anything missing:

1. **Title and abstract** (required — never run the tools on an invented abstract).
2. Study design, article type, approximate word count, number of figures/tables.
3. **Journals already used**: rejected, withdrawn, or under review. Exclude them. Note any **transfer offers** in rejection letters — they join the candidate pool.
4. **Thresholds** (set by the author, per manuscript):
   - Indexing requirement (e.g. Web of Science SCIE / SSCI, Scopus, PubMed/MEDLINE, a national index).
   - Minimum JCR quartile (e.g. Q1 only, or Q1–Q2).
   - Fee policy (e.g. "no APC — subscription/hybrid route only", or a maximum APC).
   - Publishers to avoid, if any.
   If the author has not said, ask once. A lowered threshold applies to **this manuscript only**.

## Step 1 — Generate candidates with publisher tools

Paste the title + abstract into each tool (needs a browser; plain web fetching cannot fill these forms):

| Tool | URL |
|---|---|
| Elsevier JournalFinder | https://journalfinder.elsevier.com/ |
| Springer Nature Journal Suggester | https://journalsuggester.springer.com/ |
| Wiley Journal Finder | https://www.wiley.com/en-gb/journal-finder/abstract |
| Taylor & Francis Journal Suggester | https://authorservices.taylorandfrancis.com/publishing-your-research/choosing-a-journal/journal-suggester/ |
| JANE (publisher-independent) | https://jane.biosemantics.org/ |
| Web of Science Manuscript Matcher (if the author has access) | https://mjl.clarivate.com/ |

- Use the tools' own filters when available (subject area, subscription/hybrid only).
- Record **how many suggestions each tool returned**.
- If a tool shows a CAPTCHA or bot check, **do not try to bypass it** — mark it "not reached" and move on (or ask the author to run it and paste the list).
- Supplement with **precedent**: search PubMed (or the field's main database) for similar studies from the last ~5 years and note where they were actually published. This catches journals the tools miss.

## Step 2 — Merge

- Deduplicate. For each candidate, note which tools suggested it.
- Rank candidates suggested by **two or more independent tools** higher.
- Remove excluded journals.
- If the overlap is empty, say so: the problem may be how the manuscript is positioned, not the journal pool.

## Step 3 — Hard filter: four facts, each verified at the source

For every remaining candidate, read each fact from a source in this session. Anything not verified is written **NOT VERIFIED** — never filled in from memory.

1. **Indexing.** Check the Clarivate Master Journal List by ISSN (`https://mjl.clarivate.com/search-results?issn=XXXX-XXXX`) for SCIE/SSCI/ESCI.
   - **ESCI is not SCIE.** Since 2023 Clarivate gives ESCI journals an Impact Factor too, so having an IF does not prove SCIE status.
2. **Impact Factor and JCR quartile.** Use JCR data (publisher "journal metrics/insights" page, MJL, or a named secondary site).
   - **A SCImago (SJR) quartile is not a JCR quartile.** If only SJR is available, label it "SJR, not JCR".
   - A journal can sit in several JCR categories with different quartiles; use the highest and **name the category** (e.g. "Surgery Q1, Orthopedics Q2").
3. **Fees.** Hybrid (free subscription route) or fully open access (APC amount + currency + URL)? Also check submission fees, paid fast-track, and waiver policies. If measured speed is much faster than the journal's own stated timeline, open the pricing page — the speed may be paid fast-track.
4. **Speed.** Time to first decision, desk-reject time, submission-to-acceptance. Sources: the journal's own metrics page, SciRev, Peeref.
   - **For every figure, state how many reports or manuscripts it is based on**; if the source does not say, write "n not stated".
   - A figure based on 1–2 reports carries the same weight as "no data" and must not change the ranking on its own.
   - Check issue frequency and whether the journal publishes online-first / continuously — the acceptance-to-publication queue can be half the total time.

Journals that fail the thresholds are dropped — not listed as "backups". Speed and low cost never substitute for quality.

## Step 4 — Scope and method fit

- Read the aims & scope. Does any wording exclude this study type (e.g. bibliometrics, survey, LLM evaluation, database re-analysis, non-clinical work)?
- **Precedent:** has the journal published the same kind of study in the last ~3 years? Give 1–2 real examples verified by DOI or PubMed.
- Look for editorials or author guidelines that discourage this type of submission; cite them if found.
- Check article-type constraints: word limit, abstract structure and limit, reference limit, required reporting checklist, blinding, preprint policy, AI-use disclosure rules.
- If earlier rejections gave a reason ("out of scope", "not clinical"), say whether the same objection is likely here.

## Step 5 — Trust check

Warning signs: fees hidden until acceptance, "indexed in" pages padded with low-bar indexes, gaps in the archive, name or publisher changes, very fast acceptances without real review, frequent retractions or corrections, no subject experts on the editorial board. When in doubt, run https://thinkchecksubmit.org/.

## Step 6 — Output

Write in the author's language.

1. **How the search was done** — tools used, number of suggestions from each, tools not reached.
2. **Shortlist (max 5, ranked)** — for each journal:
   - Indexing (source) · IF + JCR quartile + category (source) · Fees · Speed (+ n) · Scope fit and precedent · Why it fits · Risk.
   - Among journals of equal quality, rank the faster one first.
3. **Excluded** — grouped, one-line reason each (not SCIE, below quartile, APC only, out of scope, rejected before).
4. **NOT VERIFIED** — every data point in the shortlist that is still unconfirmed.
5. **Next step** — the author's decision; once a journal is chosen, fetch its author guidelines and adapt the package (give a time estimate).
6. **Sources** — list of URLs used.

## Do not

- Start from a remembered list of journals, or write IF/quartile/APC from memory.
- Present an SJR quartile as a JCR quartile, or treat an Impact Factor as proof of SCIE.
- Give a speed figure without its sample size.
- Bypass bot checks or CAPTCHAs.
- Choose the journal or start the submission on the author's behalf.
