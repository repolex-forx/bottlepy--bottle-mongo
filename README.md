# Repolex Knowledge Graph of bottlepy/bottle-mongo

RDF knowledge graph data for [bottlepy/bottle-mongo](https://github.com/bottlepy/bottle-mongo), parsed by [repolex](https://repolex.ai).

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
rlex download bottlepy/bottle-mongo
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 5f359898fb81b9168b79a0c8fb60bbe892763d51
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 5f359898fb81b9168b79a0c8fb60bbe892763d51
│           └── chunk-001.nq.gz
├── blob
│   ├── 5502228aafcd1e35411eaf244444a2eb935dee28.nq.gz
│   ├── 5e28dc925f75b2c2cdda9028e612a93badbe30e2.nq.gz
│   ├── 6f0899d6437ac63dbc1d64859c4bd43678309534.nq.gz
│   ├── 73e2551870b679f3fbe66816515d743caea66b1d.nq.gz
│   ├── 97051226e99793d982cf90147454c2aaf8bad25f.nq.gz
│   ├── a5b2eae2b0554555372f407bf0c9fd79064e2f1a.nq.gz
│   ├── a92202969f4a1bba558312e1c6b5211bb8acd941.nq.gz
│   ├── ae8633d81b81bcb4ce090f87be65e77c422d81b5.nq.gz
│   └── b0e99ed67fea548d3a79e1a0f8c5131cef590d71.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 5f359898fb81b9168b79a0c8fb60bbe892763d51.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 17 files
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

[bottlepy/bottle-mongo](https://github.com/bottlepy/bottle-mongo)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
