# FC CA Playbook Design Rules

Use this file before changing `ConceptArtOps.html` or creating/updating any companion HTML page.

The visual source of truth is:

`C:\Users\rimas\OneDrive\Desktop\ConceptArtOps.html`

All companion pages must look and behave like that file.

## Core Rule

Do not create a new mini web app style.

Every FC CA Playbook page should use the same playbook shell:

- `#design-ops-hub`
- `.hero`
- `.hero-inner`
- `.hero-subnav`
- `.container`
- `.sidebar`
- `.sidebar-inner`
- `.side-group`
- `.side-main`
- `.side-sub`
- `.main`
- `.panel`
- `.is-visible`

Avoid custom page systems like:

- `.shell`
- `.topnav`
- `.tabs`
- `.tab`
- `.template-card`
- `.bucket`
- `.route-card`
- `.flow-card`
- clickable checklist-only UI

If a new page needs a tab-like experience, use the original playbook pattern: sidebar links that reveal one `.panel` at a time.

## File Shape

Use the Confluence-friendly fragment shape from `ConceptArtOps.html`.

Preferred shape:

```html
<style>
    /* copied or aligned with ConceptArtOps.html */
</style>

<div id="design-ops-hub">
    <header class="hero">
        ...
    </header>

    <div class="container">
        <aside class="sidebar">
            ...
        </aside>

        <article class="main">
            <div id="..." class="panel is-visible">
                ...
            </div>
            <div id="..." class="panel">
                ...
            </div>
        </article>
    </div>
</div>

<script>
    /* same hash / sidebar panel behavior as ConceptArtOps.html */
</script>
```

Do not use:

```html
<!doctype html>
<html>
<head>...</head>
<body>...</body>
</html>
```

unless the user explicitly asks for a standalone browser-only page.

## Layout

Match the original playbook layout:

- Main wrapper: `#design-ops-hub`
- Page background: light gray `#f2f2f2`
- Content area: white
- Max content width: `1200px`
- Sidebar width: `280px`
- Main panel width: about `800px`
- Container spacing: `48px 24px`
- Sidebar and main content sit side by side on desktop.
- Sidebar stacks above content on mobile.

Do not make companion pages a single long scroll page unless explicitly requested.

## Hero

Use the original hero:

- Dark navy background
- Blue diagonal shape on the right
- Centered title
- White title text
- Small uppercase label above the title
- Optional short description below

Use these classes:

- `.hero`
- `.hero-inner`
- `.hero-label`
- `.hero-desc`
- `.hero-subnav`
- `.hero-subnav-inner`

Do not use a separate `.topnav` style.

## Sidebar

Use the original side panel pattern.

Required structure:

```html
<aside class="sidebar">
    <div class="sidebar-inner">
        <h3>Documentation</h3>
        <details class="side-group" open>
            <summary class="side-main">
                <span class="side-num c1">00</span>
                <span class="side-label">Overview</span>
                <span class="side-plus">+</span>
            </summary>
            <ul class="side-sub">
                <li><a href="#overview">Summary</a></li>
            </ul>
        </details>
    </div>
</aside>
```

Rules:

- Use `details` and `summary`.
- Use numbered side items.
- Use sublinks inside `.side-sub`.
- Links should point to section IDs inside `.main`.
- Opening a side link should show one panel, not scroll through all panels.

## Panels

Use `.panel` as the page unit.

Rules:

- First/default panel has `class="panel is-visible"`.
- Other panels have `class="panel"`.
- The script toggles `.is-visible`.
- Panels are hidden by default and shown one at a time.
- Sub-anchor links can target headings inside a panel, but the parent panel must become visible.

Do not rely on a custom tab script.

Do not display all sections at once unless the user asks for a print/export version.

## Content Cards

Use the original card language.

Preferred components:

- `.gbox` for compact cards
- `.grid2` for two-column card layouts
- `.grid3` for three-column card layouts
- `.stepbox` and `.step` for step flows
- `.hlight` for important callouts
- `.quote-block` for framed notes
- `.doc-table-wrap` and `.doc-table` for structured tables
- `.conv-card`, `.conv-head`, `.conv-inner` for full-page/panel blocks

Card style:

- White background
- `1px` border using `var(--ea-border)`
- No rounded corners
- No nested cards
- Small blue top border for compact cards: `border-top: 3px solid var(--ea-royal)`
- Keep hover subtle if used

Avoid new card systems unless they are intentionally mapped to the original classes.

## Typography

Use the original typography:

- Font: system UI stack from `ConceptArtOps.html`
- Body line-height: `1.6`
- Hero H1: large, bold, white
- Panel headers: clear black or navy, always bold (`font-weight: 700`)
- Card titles: small, bold navy (`font-weight: 700`)
- Body copy: dark readable gray, not pale gray

Do not use overly light gray headlines.

For companion pages, explicitly protect heading weight because Confluence can override default `h2` styling:

```css
#design-ops-hub h2 {
    color: var(--ea-navy) !important;
    font-weight: 700 !important;
    letter-spacing: 0;
}
```

Do not scale text with viewport width except where the original hero already does.

## Tables

Use the original table style:

- `.doc-table-wrap`
- `.doc-table`
- Header background: light blue gray `#eef5fb`
- Header text: dark blue `#203b5a`
- Header top inset line: `#7fa6ce`
- Cell text: `#34495e`
- Borders: `var(--ea-border)` or the original table border color

Do not create plain unstyled tables in companion pages.

## Checklists

If a template needs a checklist, make it visual but not app-like.

Preferred options:

- Use `.doc-table` for checklist rows.
- Use `.gbox` cards with short bullets.
- Use simple square markers inside the card if needed.
- If the user asks for a working checklist, keep the HTML readable and add light browser behavior:
  - use `.check-item`
  - use `.check-box`
  - toggle `.is-done`
  - add `role="button"`, `tabindex="0"`, and `aria-pressed`
  - keep checked state green and simple

Avoid:

- Interactive checklist behavior that replaces readable content.
- Strike-through task UI unless explicitly requested.
- Large checkbox blocks that do not match the original playbook style.

## Navigation Behavior

Use the same hash navigation logic as `ConceptArtOps.html`.

Required behavior:

- Sidebar link updates `location.hash`.
- Target panel gets `.is-visible`.
- Other panels lose `.is-visible`.
- The matching `details` group opens.
- Subsection links reveal their parent panel.

Do not create separate tab-button JavaScript.

## Canonical Page Links

Use these exact Confluence links in the shared top navigation and in every `Related pages` sidebar block:

- `Playbook`: `https://confluence.ea.com/spaces/FIFAG4/pages/1405731598/FC+CA+Playbook`
- `Process`: `https://confluence.ea.com/spaces/FIFAG4/pages/1409813793/FC+CA+Process`
- `Templates`: `https://confluence.ea.com/spaces/FIFAG4/pages/1409813869/FC+CA+Playbook+Templates`
- `Research`: `https://confluence.ea.com/spaces/FIFAG4/pages/1409813867/Research+Documentation`

## Companion Pages

Process, Templates, and future companion pages should feel like smaller playbook chapters.

They should use:

- Same hero
- Same sidebar
- Same `.main .panel` behavior
- Same cards/tables/callouts
- Same spacing
- Same colors
- Same hover restraint

Research conversations and detailed source notes should live in the separate research documentation page. The main `ConceptArtOps.html` should link to that page, not embed conversation panels in its sidebar or main content.

They should not use:

- Full browser-app layout
- Separate tab bars
- Big standalone cards that ignore `.gbox`
- New palettes
- Custom components that look different from `ConceptArtOps.html`

## Content Tone

Keep wording simple.

Use:

- `Concept Art`
- `Concept Art support`
- `the playbook`
- `Intent`
- `goal`
- `context`
- `owner`
- `decision`
- `handoff`
- `feature brief`
- `creative brief`

Avoid:

- corporate filler
- academic wording
- source-name explanations
- negative framing
- repeating `FC CA Playbook` in every paragraph

## Pre-Change Checklist

Before editing or creating a page:

1. Open `ConceptArtOps.html`.
2. Reuse its design tokens and page structure.
3. Use `#design-ops-hub`.
4. Use `.container`, `.sidebar`, and `.main`.
5. Use `.panel` and `.is-visible`.
6. Use `.gbox`, `.grid2`, `.grid3`, `.hlight`, and `.doc-table` before inventing new components.
7. Keep the page Confluence-friendly.
8. Confirm no new full-page wrapper was added.
9. Confirm only one panel is visible by default.
10. Confirm all sidebar links point to valid IDs.

## Review Checklist

After editing:

- Search for `<html`, `<head`, `<body`, `</html>`, and `</body>` in companion fragments.
- Search for `.tabs`, `.tab`, `.shell`, `.template-card`, `.bucket`, `.route-card`, and `.flow-card`.
- If those custom classes exist, replace or restyle them to match the original playbook classes.
- Confirm page has a left sidebar.
- Confirm panel links show dedicated content instead of one long scroll page.
- Confirm headings are dark and readable.
- Confirm cards match the original square, bordered, blue-accent style.
