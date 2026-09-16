# Interaction contract

## Search

Search table names and column names case-insensitively. Rank exact table-name matches, table-name prefixes, table-name substrings, then field matches. Visually mark why a field-only result matched. Clear search restores the previous domain view.

## Filters

Domain filters are mutually exclusive unless the task needs multi-select. Always provide `全部`. Filtering should update the visible table count and must not silently change the authoritative total.

## Selection and focus

Clicking a table selects it, opens complete details, highlights inbound and outbound paths, and fades unrelated nodes and edges. The selected state must remain clear without relying on color alone. Clicking a relationship in the detail panel navigates to the other table.

`只看关联表` keeps the selected table and its direct neighbors. If no table is selected, explain how to activate the mode instead of showing an empty canvas.

## Detail surface

Show table description, business domain, columns, types, PK/FK/UQ/index markers, nullability, defaults, checks, composite constraints, indexes, and inbound/outbound relations when the source provides them. Long content should scroll inside the panel without shrinking the diagram.

## State and accessibility

Use buttons for interactive nodes and controls. Support visible keyboard focus, Escape to close drawers, and useful `aria-label` values. Keep interaction state in memory unless reload persistence is explicitly useful; if persisted, use a unique per-artifact storage key and never store schema secrets.

## Responsive behavior

Below roughly 1050 px, stack the detail surface below the diagram or use a full-height drawer. Below roughly 700 px, wrap filters, preserve at least a usable diagram viewport, and avoid reducing text below readable sizes.
