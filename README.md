# Repolex Knowledge Graph of glue-viz/glue-plugin-template

RDF knowledge graph data for [glue-viz/glue-plugin-template](https://github.com/glue-viz/glue-plugin-template), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [rlex](https://github.com/repolex-ai/rlex) query tool:

```bash
cargo install --git https://github.com/repolex-ai/rlex
```

Verify the install:

```bash
rlex --help
```

**rlex is designed to be used primarily by LLMs in a terminal.** Start up your favorite AI assistant and ask it to use rlex. It handles the SPARQL — you just ask questions in plain English.

To load this repo's data:

```bash
rlex download glue-viz/glue-plugin-template
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── c46742a3b3f0e873a97c0556462c380935255a9f
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── c46742a3b3f0e873a97c0556462c380935255a9f
│           └── chunk-001.nq.gz
├── blob
│   ├── 229e5765e04414dbb2906d0f1fbd11f088853d69.nq.gz
│   ├── 5a44a978cbc8461ed2d647067ac1132d81c87d4a.nq.gz
│   ├── aaff5ff6dad63173d615c01fd1a8b937bc4cd85c.nq.gz
│   ├── e0b254e0c571563ce1c332660f91eb402ca195af.nq.gz
│   └── e851e58bf4c7b631d2a67f501bb74c7a2b0a8217.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── c46742a3b3f0e873a97c0556462c380935255a9f.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 11 files
```

| Directory | What it contains |
|-----------|-----------------|
| `blob/` | Per-file AST graphs, content-addressed by git blob SHA. Each file in the source repo gets its own graph. |
| `aggregate/ast/` | Combined AST graph per parsed commit. Merges all blob graphs for a snapshot of the entire codebase at that point. |
| `aggregate/lsp/` | Language Server Protocol enrichment: resolved symbols, definitions, references, and type information. |
| `aggregate/dataflow/` | Interprocedural data flow edges between functions and modules. |
| `aggregate/repolex/` | Combined graph (AST + LSP + dataflow) per commit. |
| `commit/` | Git commit metadata (author, date, message, parent links). |
| `branch/` | Branch metadata. |
| `tag/` | Tag metadata. |
| `filetree/` | File tree snapshots per commit (which files existed and their blob SHAs). |
| `audit/` | Code architecture and graph audit reports per commit. |

## Source repository

[glue-viz/glue-plugin-template](https://github.com/glue-viz/glue-plugin-template)

---
*Parsed on 2026-10-21 by [repolex](https://repolex.ai)*
