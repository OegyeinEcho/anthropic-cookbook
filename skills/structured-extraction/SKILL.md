---
name: structured-extraction
description: Use when converting prose, forms, tables, images, PDFs, or webpages into structured JSON or a user-specified schema with validation, provenance, and explicit missing-value handling.
---

# Structured extraction

Produce usable structured data without inventing fields or values. This workflow covers summaries, entities, classifications, form transcription, table extraction, and JSON-shaped outputs.

## Workflow

1. Confirm the target schema before extracting. If the user supplied a schema, preserve its field names, types, required fields, allowed values, and cardinality. If no schema exists, propose a small schema and identify which choices are assumptions.
2. Inspect the input and determine its coverage and quality. Note missing pages, unreadable regions, image-only tables, ambiguous handwriting, duplicated content, and conflicting values.
3. Extract only what is supported by the input. Use null, an explicit missing marker, or an uncertainty note instead of guessing. Never convert an absent value into an empty fact.
4. Preserve provenance for material fields when practical: source name, page/section, table/row, image region, or quoted context.
5. Apply deterministic validation:
   - required fields are present or explicitly marked missing
   - types and units are consistent
   - enum values are within the allowed set
   - numeric ranges are valid
   - dates and identifiers retain their original precision
   - duplicate entities are merged only with evidence
6. Separate extraction from interpretation. If the user asks for sentiment, classification, or a score, state the rubric and scale; do not imply that a subjective score is a measured fact.
7. Return the requested machine-readable format first when feasible, followed by a short validation note. Keep commentary outside JSON unless the user asked for a mixed format.
8. If strict JSON is requested, output valid JSON only. Escape strings correctly and do not add Markdown fences.
9. Report validation failures and unresolved ambiguities instead of hiding them. Ask a focused clarification question only when the missing choice changes the structure or meaning of the result.
10. For images, charts, and PDFs, never claim visual details that were not actually visible. Identify low-resolution or OCR-related uncertainty.

## Quality checklist

Before handoff, check schema validity, completeness, provenance coverage, normalization choices, uncertainty markers, and whether any value was inferred rather than extracted.
