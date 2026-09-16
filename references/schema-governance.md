# Schema governance and evolution

Read this reference only when the requested deliverable includes schema findings, repair handoff, migration history, or version comparison.

## Companion artifact bundle

Keep related artifacts together when the user requests a durable database workspace:

```text
database/
├── README.md
├── database-erd.html
├── schema-findings.md
├── schema-changelog.md
└── versions/
    └── <version>.json
```

Create only the files needed by the request. A standalone ERD does not require this full bundle.

- The schema, migrations, or ORM definitions remain authoritative.
- The HTML visualizes the current structure, product-page data flows, and optional version comparisons.
- `schema-findings.md` holds evidence-backed, actionable issues.
- Version snapshots contain normalized schema metadata and no database records.

## Findings

Separate confirmed structural problems from inferred risks. Give each finding a stable identifier such as `DB-001` and record:

- priority and status;
- affected tables and fields;
- evidence from the authoritative source;
- practical impact;
- recommended direction;
- acceptance conditions;
- completed change and validation when resolved.

Keep permanent findings out of the main canvas. In the HTML, show a compact count and a collapsed summary with a relative link to the Markdown file.

## Agent handoff

Prepare handoff around one selected finding or a tightly related set. Include the finding identifier, authoritative schema path, migration path when present, ERD path, requested scope, and acceptance conditions. Ask the implementing agent to update the migration or schema, application integration, meaningful validation, finding status, and generated artifacts.

The handoff must state that the ERD is reference material rather than the source of truth. Do not let generated findings authorize destructive migration or production deployment.

## Evolution view

Treat database schema versions separately from application marketing versions. Prefer migration identifiers, release tags, or dated baselines that can be traced to a commit.

Each normalized snapshot should record at least:

- version identifier;
- generation time;
- source commit or migration;
- source paths;
- schema hash;
- tables, columns, constraints, indexes, and relationships.

Provide three modes when the history is substantial enough to benefit from them:

1. Current structure for the latest schema.
2. Evolution timeline for ordered migration summaries.
3. Version comparison for added, changed, and removed structures.

Use restrained change semantics: green for additions, blue for modifications, red for removals, amber for unresolved migration risks, and reduced contrast for unchanged structures. Never infer a historical schema from the current state when the required migration or revision is unavailable; label the gap instead.

Generate snapshots deterministically when practical. Compare normalized structures rather than formatted SQL so whitespace and statement ordering do not create false changes.
