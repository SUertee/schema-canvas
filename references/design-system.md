# Visual system

## Product character

Aim for a quiet working document: warm off-white canvas, white information surfaces, deep navy text, restrained blue interaction accents, and small amounts of amber for warnings. The visual hierarchy should come from spacing, grouping, typography, and line weight rather than gradients or decorative effects.

Use design tokens in `:root`. A suitable starting palette is:

- page `#f5f5f1`
- canvas chrome `#ebece8`
- card `#ffffff`
- primary ink `#102a43`
- secondary text `#526577`
- faint text `#7d8d9b`
- border `#d7dedf`
- accent `#1776a8`
- accent surface `#dff2fb`
- warning `#b45309`
- warning surface `#fff4df`

Use the host product's existing tokens when supplied. Do not force this palette over an established design system.

## Composition

- Put the title, source, generation date, and a few schema facts in one compact header.
- Keep search and filters in a single toolbar directly above the diagram.
- Give the diagram most of the viewport; allow deliberate horizontal scrolling for large schemas.
- Group nodes inside softly bounded domain regions.
- Keep each collapsed node compact: table name plus one short metadata line is usually enough.
- Reveal full fields and constraints only for the selected table.
- Use a 10–13 px radius consistently. Shadows should be subtle and optional.
- Prefer a sticky detail panel on wide screens and a drawer or stacked panel on narrow screens.

## Typography

Use a clear sans-serif for interface text and a monospace face for table names, field names, types, and paths. Chinese interfaces should use natural Chinese labels throughout. Avoid mixed English labels unless they are literal schema identifiers.

## Relationship styling

- Real foreign key: solid neutral line, with direction and cardinality.
- Logical relationship: blue dotted line and explicit `逻辑关系` label.
- Confirmed structural gap: amber dashed line and explicit `结构缺口` label.
- Selected paths: stronger weight and full opacity.
- Unrelated paths after selection: fade heavily but remain discoverable.

Do not create an unreadable web of lines. Reposition nodes, route edges, split domains, or use a focused related-table mode when paths cross excessively.

## Density rules

The overview is for orientation, so show less. The detail surface is for inspection, so show complete evidence. Do not repeat the same facts in the header, node, panel, legend, and footer. Keep legends small and place project-specific findings below the diagram only when they help a real review decision.
