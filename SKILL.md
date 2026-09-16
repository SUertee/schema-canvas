---
name: schema-canvas
description: Create polished, self-contained HTML database ERDs with a calm light visual system, strong information hierarchy, table and field search, domain filters, relationship focus, and detailed schema inspection. Use for documenting or exploring schemas with several related tables, especially when the result should feel like a designed product rather than a generic developer diagram.
---

# Schema Canvas

Create an ERD that answers three questions quickly: what tables exist, how they relate, and what is inside the selected table. Preserve the supplied product's visual language when one exists. Otherwise use the design baseline in [references/design-system.md](references/design-system.md).

## Build from evidence

Read the authoritative schema, migrations, or ORM definitions before drawing. Derive tables, columns, types, nullability, primary keys, foreign keys, unique constraints, indexes, defaults, checks, and delete behavior from source. Label inferred application relationships as logical; never present them as database foreign keys.

For a changing repository, report schema parity in the page footer or metadata and identify the exact source files and generation date. Do not include database records, credentials, or personal data.

## Choose the view

- Use a full schema overview for orientation and onboarding.
- Use a focused 3–8 table view for one feature or query path.
- Use a page data-flow view when the user wants to understand which tables, calculations, and inputs support a product page. Rebuild the canvas around that page instead of merely fading the complete schema.
- Use a before/after view when the request is about a migration.
- Use a data lineage view when direction represents data movement rather than referential integrity.

For more than about ten tables, group by business domain and provide progressive disclosure. Keep the diagram as the primary surface. Avoid large permanent sidebars, decorative metric cards, and dense fields inside every node.

## Optional governance bundle

When the user wants schema findings, repair handoff, or database-version evolution, read [references/schema-governance.md](references/schema-governance.md). Keep the authoritative schema or migrations as the source of truth; use the HTML as the visual explorer and Markdown as the actionable findings record.

## Required interaction

For schemas larger than ten tables, include:

- one search field that matches table names first and may also match column names;
- domain filters with an obvious all-domains state;
- table selection that highlights direct relationship paths and fades unrelated nodes;
- a related-only mode;
- a detail panel or drawer with all columns, types, constraints, defaults, indexes, and inbound/outbound relations;
- separate visual styles and toggles for real foreign keys, logical relations, and known schema gaps when those categories exist;
- keyboard focus states and responsive behavior.

Search results must remain visible in context. Selecting a search result should reveal the table, focus it, and open its details. Empty searches and no-match states must be explicit.

## Visual and implementation contract

Read [references/design-system.md](references/design-system.md) before building the HTML. Read [references/interaction-contract.md](references/interaction-contract.md) when the schema has more than ten tables or when interactive exploration is requested.

Use [assets/reference-erd.html](assets/reference-erd.html) as a visual and interaction reference when helpful. It is not a drop-in schema: replace all example-specific data, titles, positions, annotations, and audit notes with evidence from the current project.

Write one self-contained `.html` file with inline CSS and JavaScript and no required build step. Use semantic HTML, real text, and inline SVG or positioned DOM nodes. Build dynamic content with `createElement` and `textContent`; never insert imported schema data with dynamic `innerHTML`.

Keep the page useful offline. If an external font is used, declare robust system fallbacks. Ensure print output remains readable.

## Verify before delivery

Check:

1. Every active table in the authoritative source is represented or explicitly excluded.
2. Column counts and relationship counts match the source.
3. Real foreign keys, logical links, and gaps are visually and semantically distinct.
4. Search, filters, selection, related-only mode, relationship navigation, and detail close behavior work.
5. The browser console has no errors and dynamic schema data never reaches `innerHTML`.
6. The page contains no private records or unrelated project text.

Open the generated file for visual review when the environment permits it, then iterate on overlaps, clipped labels, unreadable edges, excessive density, and small-screen layout.
