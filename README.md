# Journal Finder Skill

A reusable method for AI assistants (Claude, ChatGPT) to help researchers choose a target journal for a manuscript — without hallucinated metrics.

[Türkçe README](README.tr.md)

## Why

Ask a chatbot "which journal should I submit to?" and you usually get a list from memory, with impact factors and quartiles that are out of date or simply wrong, open-access fees that were never checked, and "fast" journals whose speed rests on one anonymous report.

This skill makes the assistant work the other way round:

1. **Publisher tools generate the candidates.** The title and abstract go into Elsevier JournalFinder, Springer Nature Journal Suggester, Wiley Journal Finder, Taylor & Francis Journal Suggester and JANE; transfer offers from rejection letters and journals where similar studies were published are added.
2. **Candidates are merged.** Journals suggested by several independent tools rank higher.
3. **Every candidate is verified at the source** for four facts: indexing (Clarivate Master Journal List), Impact Factor and **JCR** quartile, fees (APC vs free subscription route), and speed — always with the number of reports behind each speed figure.
4. **Scope and precedent are checked**: has the journal actually published this kind of study recently?
5. **A short, ranked list** comes back with every unverified data point flagged, plus the excluded journals and the reason each was dropped.

The author decides. The assistant recommends; it does not choose or submit.

## Built-in traps it avoids

- **ESCI ≠ SCIE.** Clarivate has given ESCI journals Impact Factors since 2023, so an IF alone does not prove SCIE status.
- **SJR quartile ≠ JCR quartile.** SCImago quartiles are labelled as such and never presented as JCR.
- **Multiple JCR categories.** The quartile is reported with its category (e.g. "Surgery Q1, Orthopedics Q2").
- **Speed with n = 1.** A speed figure based on one or two reports counts as "no data".
- **Paid fast-track.** If measured speed beats the journal's own stated timeline, the pricing page is checked.
- **Acceptance-to-publication queue.** Issue frequency and online-first publication are checked.

## Use with Claude

Copy `skills/journal-finder/` into your skills folder:

- **Claude Code:** `~/.claude/skills/journal-finder/SKILL.md` (or `.claude/skills/` inside a project).
- **Claude apps (claude.ai / desktop):** zip the `journal-finder` folder and upload it under *Settings → Capabilities → Skills* (availability depends on your plan).

Then just ask: *"Find a target journal for this manuscript"* and paste the title and abstract. Claude in Chrome (or another browser tool) lets Claude fill in the publisher tools itself; without one, it will ask you to paste their results.

## Use with ChatGPT

Open [`chatgpt/journal-finder-instructions.md`](chatgpt/journal-finder-instructions.md) and paste the block into a **Custom GPT's instructions**, a **Project's instructions**, or the start of a chat. Turn on web search, and Agent mode/browsing if you have it.

## Set your own thresholds

The skill has no built-in quality bar. At the start it asks for yours, per manuscript — for example:

- "SCIE only, JCR Q1, no APC (subscription route)"
- "Scopus-indexed, Q1–Q2, APC up to USD 2,000"
- "MEDLINE-indexed, any quartile, avoid publisher X"

## Repository layout

```
skills/journal-finder/SKILL.md          Claude skill
chatgpt/journal-finder-instructions.md  ChatGPT instructions (Custom GPT / Project / chat)
README.md / README.tr.md
LICENSE
```

## Limitations

- Clarivate JCR itself requires a subscription; quartiles often come from publisher pages or named secondary sites and are flagged accordingly.
- Some publisher tools use bot protection. The assistant will not bypass it; you may need to run that tool yourself and paste the list.
- Publisher tools only suggest their own journals — which is why several are combined, plus JANE and a precedent search.
- Metrics change every year. Always confirm on the journal's own site before submitting.

## License

MIT — see [LICENSE](LICENSE).
