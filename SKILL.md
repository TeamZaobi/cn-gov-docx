---
name: cn-gov-docx
description: Use this skill when the user needs a Chinese formal Word document or government-style document workflow, especially for `.docx` outputs such as reports, briefings, implementation plans, FAQs, official letters, requests, meeting minutes, or outward-facing project materials. This skill handles document-type selection, Chinese formal structure, typography and layout defaults, wording discipline, and final review rules. When the task also requires actual `.docx` generation or XML-level editing, coordinate with the installed `docx` skill instead of replacing it.
---

# Chinese Formal DOCX

## Overview

`cn-gov-docx` is a companion skill for Chinese formal writing in Word documents.
It does not try to replace the general `docx` skill. Its job is to decide what kind of formal document the user really needs, apply appropriate Chinese structure and wording discipline, and give stable layout defaults when no organization-issued template is available.

Use this skill for:

- Chinese project briefings, reports, implementation plans, and outward-facing scheme documents
- FAQs, meeting minutes, official letters, requests, replies, and situation notes
- `.docx` deliverables that need Chinese formal structure, typography, and review discipline
- Converting rough Markdown, notes, or slide content into a polished formal Word draft

Do not treat these defaults as stronger than a real institutional template.
If the user provides a government, hospital, university, or enterprise template, that template is the source of truth.

## Workflow

### 1. Classify the document

First determine which category the request belongs to:

- `briefing-report`: briefing, report, situation note, project summary
- `implementation-plan`: construction plan, work plan, phased rollout plan, execution plan
- `official-letter`: outbound letter, reply letter, communication letter
- `request`: request for approval, application, submission note
- `faq`: common questions, service explanation, usage guide
- `meeting-minutes`: minutes, decisions, follow-up record
- `general-formal`: a formal Chinese document that does not clearly fit the above

If unclear, prefer the document's intent over its title.
For example, a file named "建设方案" may actually behave like a phased implementation plan, not a legal-style official document.

See [references/document-types.md](references/document-types.md) for the detailed mapping.

### 2. Decide the strictness level

Use one of three levels:

- `strict-official`: formal external submission to an authority or regulated institution
- `formal-business`: outward-facing project material, construction plans, reports, FAQs, and standard formal documents
- `light-formal`: internal materials that should remain formal but not fully official-style

Default to `formal-business` unless the user explicitly asks for a strict official format or provides an official template.

See [references/layout-and-typography.md](references/layout-and-typography.md).

### 3. Build the structure before writing

For every document, confirm:

- title
- addressee or applicable audience, if needed
- opening paragraph or abstract
- main section hierarchy
- conclusion or request/closing formula
- attachment note, if any
- issuer, department, date, and contact information when relevant

Avoid drafting full prose before the structure is stable.
Most quality failures in formal documents come from choosing the wrong structure, not from sentence-level writing.

### 4. Write in the right register

When writing:

- prefer stable, explicit, responsibility-bearing language
- keep terminology consistent across the whole document
- make phase sequencing and ownership easy to scan
- separate policy statements, current state, implementation steps, and safeguards
- avoid marketing language, slogans, and product-brand digressions unless the user explicitly asks for them

For outward-facing materials, describe the solution and rollout path directly.
Do not spend space explaining how the document itself was written.

### 5. Generate or edit the `.docx`

If the user wants an actual Word file:

- use this skill to choose the structure and formatting rules
- use the installed `docx` skill for document generation, conversion, XML-level edits, comments, tracked changes, or image insertion

If a quick starter `.docx` is useful, generate a base file with:

```bash
python scripts/render_starter_template.py \
  --type implementation-plan \
  --title "山东省医学开放数据科研平台建设方案" \
  --output ./山东省医学开放数据科研平台建设方案.docx
```

The starter template is a scaffold, not a final formatted authority template.

### 6. Run the review pass

Before delivery, check:

- document type and closing formula match the intent
- heading hierarchy is consistent
- terminology is stable
- dates, names, departments, and attachments match the latest source
- strictness level matches the intended audience
- the wording is formal and direct, without unnecessary self-explanation

Use [references/review-checklist.md](references/review-checklist.md) when the document is externally shared.

## Working With Other Skills

Use `cn-gov-docx` together with `docx` when any of the following are true:

- the output must be a real `.docx`
- an existing Word file must be edited in place
- tracked changes, comments, or XML-level fixes are required
- the user provides a template document that must be preserved

In that pairing:

- `cn-gov-docx` decides structure, Chinese formal writing rules, and layout defaults
- `docx` handles the actual document manipulation workflow

## Common Scenarios

This skill is especially useful for requests such as:

- "把这份省平台建设方案整理成正式 Word 文档"
- "把 FAQ 改成对外汇报材料的格式"
- "按中文正式公文风格起草一份函"
- "把会议纪要整理成可发文的版本"
- "把 Markdown 方案转成正式 `.docx`，保留标题层级和规范版式"

## Resources

- [references/document-types.md](references/document-types.md): document selection and canonical structure
- [references/layout-and-typography.md](references/layout-and-typography.md): Chinese formal layout defaults and font guidance
- [references/review-checklist.md](references/review-checklist.md): pre-delivery QA checklist
- `scripts/render_starter_template.py`: generate a Chinese formal `.docx` starter scaffold
