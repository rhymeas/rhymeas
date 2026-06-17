# FC CA Playbook Research Source Folder

This folder is the stable source location for FC CA Playbook work.

Use `Research_Index.md` first. It explains what each source is for, what it should influence, and how strongly it should be weighted.

## Folder Structure

- `01_company_direction`
- `02_research_conversations`
- `03_art_playbook`
- `04_templates_questions`
- `05_current_presentation`
- `06_raw_notes`
- `97_do_not_quote_directly`
- `99_archive_do_not_use_unless_asked`
- `tools`

## Refreshing the Inventory

Run this from PowerShell:

```powershell
.\tools\Update-ResearchIndex.ps1
```

The script refreshes the auto-generated inventory section in `Research_Index.md`. The main index table is intentionally manual so descriptions, influence areas, and priority stay curated.
