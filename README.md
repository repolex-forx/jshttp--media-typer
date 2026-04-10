# Repolex Knowledge Graph of jshttp/media-typer

RDF knowledge graph data for [jshttp/media-typer](https://github.com/jshttp/media-typer), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [lexq](https://github.com/repolex-ai/lexq) query tool using [uv](https://docs.astral.sh/uv/getting-started/installation/).

If you have uv installed, just copy/paste this into your terminal:

```bash
uv tool install git+https://github.com/repolex-ai/lexq
```

This installs lexq onto your system, in your user context. Verify the install:

```bash
lexq --help
```

**lexq is designed to be used primarily by LLMs in a terminal.** Start up your favorite LLM and ask it to use the lexq tool. It's that easy!

To load this repo's data:

```bash
lexq download jshttp/media-typer
```

This will automatically download essential data files from the last parsed commit. Consult `lexq --moreinfo` for other options, including downloading multiple commits, blobs, etc.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 1332b73ed8584b7b25d556c55b6de9d64fa3ce2c
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 1332b73ed8584b7b25d556c55b6de9d64fa3ce2c.nq.gz
│   └── repolex
│       └── 1332b73ed8584b7b25d556c55b6de9d64fa3ce2c
│           └── chunk-001.nq.gz
├── blob
│   ├── 1dca712ee162c2ae9cb7ee3011948018c845ca39.nq.gz
│   ├── 1eece14ad8cb98de2093fac5eef5ccee89472ff8.nq.gz
│   ├── 37edad16f5aca0263d8350f3654cf1f04a5c32cf.nq.gz
│   ├── 4848b02b6a74cbd6961688dfd045b37f6af3117e.nq.gz
│   ├── 4bf435e39138872732d868919b1e30cbf2a17f2d.nq.gz
│   ├── 538ade14fa848dcce1b5b839ced17f5817fcd5ff.nq.gz
│   ├── 76b1021d09a5774679c815f83d1c9a4bccf21c28.nq.gz
│   ├── 84441fbb5709262c2bfc9b5ff0166ad4f024a1b8.nq.gz
│   ├── 897cae1570efe9b622229f15e07fe45fe8284350.nq.gz
│   ├── 9808c3b2b6602da61eb4afcb4caf33368e3e2bd4.nq.gz
│   └── fd4a2d5322496dca492784ea786a02a6cbae1e4b.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 1332b73ed8584b7b25d556c55b6de9d64fa3ce2c.nq.gz
├── filetree
│   └── 1332b73ed8584b7b25d556c55b6de9d64fa3ce2c.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 21 files
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

## Source repository

[jshttp/media-typer](https://github.com/jshttp/media-typer)

---
*Parsed on 2026-04-10 by [repolex](https://repolex.ai)*
