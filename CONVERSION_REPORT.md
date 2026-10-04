# Claude Cookbook to Plugin conversion

## Source and provenance

- Source repository: https://github.com/OegyeinEcho/anthropic-cookbook
- Inspected ref: main
- Conversion branch: codex/claude-cookbook-plugin-skills
- License: MIT, Copyright (c) 2023 Anthropic
- Source material remains in its original locations; this branch adds derived, product-neutral workflow instructions with attribution.

## Converted capabilities

| Plugin Skill | Source evidence | Why it was selected |
| --- | --- | --- |
| evidence-grounded-analysis | misc/using_citations.ipynb, misc/pdf_upload_summarization.ipynb, multimodal/reading_charts_graphs_powerpoints.ipynb, multimodal/using_sub_agents.ipynb | Generalizes citation ledgers, document/image inspection, staged extraction, and answer synthesis without requiring a vendor SDK. |
| structured-extraction | tool_use/extracting_structured_json.ipynb, misc/how_to_enable_json_mode.ipynb, multimodal/how_to_transcribe_text.ipynb | Generalizes schema-first extraction, strict JSON output, entity extraction, classification, and transcription with validation and provenance. |
| evaluation-and-safety-review | misc/building_evals.ipynb, misc/building_moderation_filter.ipynb | Combines reusable evaluation design, grader selection, moderation boundaries, edge-case coverage, and conservative escalation. |

## Skipped or reference-only material

- Anthropic SDK installation, model names, API calls, token limits, and prompt syntax: vendor/runtime-specific; kept as source reference.
- Third-party integrations (Brave, Deepgram, LlamaIndex, MongoDB, Pinecone, VoyageAI, WolframAlpha): require external credentials or runtime services and are not honest skills-only capabilities.
- Customer-service tool execution and order cancellation: action-specific and potentially consequential; requires a real authenticated app with authorization and confirmation controls.
- Image-generation and model-written Matplotlib execution: illustrative or unsafe without a sandbox and explicit execution path; not mirrored.
- Sub-agent model orchestration: generalized only into staged evidence extraction; no claim is made that a host can spawn a particular model or agent.

## Architecture

This conversion is skills-only. The selected workflows can use host-provided files, images, documents, web access, and Python when available, but they do not require a bundled MCP server or vendor authentication.

## Validation status

The branch contains a minimal plugin manifest and three immediate-child Skills. Public-directory submission is not claimed: verified publisher identity, listing URLs, brand assets, package ZIP, clean-install smoke tests, and portal review evidence remain separate release gates.
