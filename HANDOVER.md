# FC CA Playbook Handover

## What this repo is

This repo is the working package for the FC CA Playbook docs. It keeps the playbook split into separate pages so the content stays easier to maintain and easier to read in Confluence.

## Current structure

### Main pages

- `ConceptArtOps.html` - executive overview and in-depth framework
- `FC_CA_Playbook_Process.html` - short operating loop and process questions
- `FC_CA_Playbook_Templates.html` - fuller question bank and reusable templates
- `FC_CA_Playbook_Research_Documentation.html` - source evidence and research notes

### Support files

- `FC_CA_Playbook_Research/README.md` - source folder intro
- `FC_CA_Playbook_Research/Research_Index.md` - source map and priority guide
- `FC_CA_Playbook_Research/design.md` - visual and HTML rules
- `FC_CA_Playbook_Research/Request_Rules_Template.md` - short request rule helper

## Current working idea

The playbook is framed as a lightweight creative decision engine.

The main spine is:

- `Intent`
- `Explore`
- `Align`
- `Decide`
- `Save and learn`

The process page keeps the short loop.
The templates page keeps the fuller question bank.
The overview page stays the executive summary.
The research documentation stays the evidence layer.

## Key content rules

- Keep the wording simple.
- Use `Concept Art`, `Concept Art support`, or `the playbook` in body copy.
- Use `FC CA Playbook` only when a formal title is needed.
- Keep AI human-led.
- AI can summarize, sort, draft, and structure.
- People keep the judgment and final decision.
- Keep mode, team, dependency, and handoff context visible when it matters.
- Do not turn the docs into a heavy checklist unless a section really needs one.
- Preserve existing layout choices, anchors, and sidebar behavior.

## Source buckets to keep using

- `01_company_direction`
- `02_research_conversations`
- `03_art_playbook`
- `04_templates_questions`
- `05_current_presentation`
- `06_raw_notes`
- `97_do_not_quote_directly`
- `99_archive_do_not_use_unless_asked`

## Default request rule

Use the source folder as background, but keep the output simple and presentation-ready.

If a request is about the main overview, usually update Section 00.
If a request is about the operating model or framework, usually update Section 11.
If a request is about workflow, templates, or question banks, keep the split across the Process and Templates pages.

## Setup on another PC

### 1. Install Codex

Install Codex on the new machine and make sure the Browser tool is available.

### 2. Add the project skill

Copy the `fc-ca-playbook` skill folder into the Codex skills location on the new PC.

Expected path shape:

- Windows: `C:\Users\<you>\.codex\skills\fc-ca-playbook\SKILL.md`
- macOS/Linux: `~/.codex/skills/fc-ca-playbook/SKILL.md`

If the skill folder is already in this repo or on another machine, copy the whole folder, not only the markdown file.

### 3. Keep the source folders together

Recommended local source layout:

- `FC_CA_Playbook_Research`
  - `01_company_direction`
  - `02_research_conversations`
  - `03_art_playbook`
  - `04_templates_questions`
  - `05_current_presentation`
  - `06_raw_notes`
  - `97_do_not_quote_directly`
  - `99_archive_do_not_use_unless_asked`

### 4. Open the HTML files locally

The docs are plain HTML pages and can be opened in a browser directly from disk or served with a simple local static server.

### 5. Keep the reference files handy

Use these first when continuing work:

- `FC_CA_Playbook_Research/Research_Index.md`
- `FC_CA_Playbook_Research/design.md`
- `FC_CA_Playbook_Research/Request_Rules_Template.md`

## How to continue the work

- Check the overview first.
- Then check the in-depth framework.
- Then update the process page if the workflow needs more clarity.
- Then update the templates page if the question bank needs more detail.
- Keep the research page as evidence, not the main operating page.

## GitHub target used here

This repo is published to:

- `rhymeas/rhymeas`

If you move this to another repo later, keep the file structure and the handover notes the same.
