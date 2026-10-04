---
name: evidence-grounded-analysis
description: Use when answering questions from supplied documents, webpages, images, charts, or other sources and the result must distinguish evidence, inference, uncertainty, and citation coverage.
---

# Evidence-grounded analysis

Turn supplied sources into a traceable answer. This workflow is useful for research, document review, chart interpretation, and multi-source synthesis.

## Workflow

1. Inventory the sources before interpreting them. Record the source label, type, date if known, location, and whether it is complete or partial.
2. Restate the question as answerable claims. Separate factual extraction, comparison, calculation, interpretation, and recommendation.
3. Inspect the sources for the evidence relevant to each claim. For documents, preserve page/section/paragraph references. For images or charts, record the visual region, axis/legend, and any transcription uncertainty.
4. Build a compact evidence ledger with one row per claim:
   - claim
   - supporting source reference
   - exact or closely bounded evidence
   - confidence
   - unresolved gap or conflicting source
5. Distinguish evidence from inference explicitly. Do not turn a plausible reading into a quoted fact, and do not fill missing values from general knowledge without labeling the assumption.
6. Answer the user's question first, then provide concise supporting citations or source references. Cite the source nearest to the claim it supports.
7. If the source set cannot support the requested conclusion, say what is missing and give the strongest narrower conclusion available.
8. For calculations, show the inputs, formula, units, rounding, and whether the result is exact or estimated.
9. For conflicting sources, preserve both positions, explain the conflict, and avoid silently choosing the more convenient one.
10. Finish with a coverage check: every material claim has evidence, every citation resolves to a source, and uncertainty is visible.

## Output shape

Use this structure when it helps:

- Answer
- Evidence
- Inference or interpretation
- Uncertainty and gaps
- Source list

Do not manufacture URLs, page numbers, quotations, dates, or tool results. If a source was not actually read or inspected, say so.
