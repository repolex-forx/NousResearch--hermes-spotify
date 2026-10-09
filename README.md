# Repolex Knowledge Graph of NousResearch/hermes-spotify

RDF knowledge graph data for [NousResearch/hermes-spotify](https://github.com/NousResearch/hermes-spotify), parsed by [repolex](https://repolex.ai).

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
rlex download NousResearch/hermes-spotify
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 2f39a03ca83c5e36566018d888e81b46a9ee6371
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 2f39a03ca83c5e36566018d888e81b46a9ee6371
│           └── chunk-001.nq.gz
├── blob
│   ├── 0e605c1fc662dbb60bb500341676f37235bcaaf7.nq.gz
│   ├── 14e327fd011e786d986589562c3639d9dbde4b70.nq.gz
│   ├── 2d25a0ab3c3a86dca04d5de5c1716d2ea3b70078.nq.gz
│   ├── 318ca509b90415b37a4761a935e551c865503f68.nq.gz
│   ├── 42e72b04fcff3e5904750a8132811b5fd0644e1c.nq.gz
│   ├── 5700b997827973cb0eb6d84a2782bb08a5872434.nq.gz
│   ├── 6474f5492fb6e52d0b7815e507728ef79ec4b6f7.nq.gz
│   ├── 78d8c450ccd12540e75c513580ada26deef0e552.nq.gz
│   ├── 95e5e4c5fa453cae65e97e2b3bd24bcc341d9b59.nq.gz
│   ├── afb79e4f29167fd5faa0864c28577505bb318a37.nq.gz
│   ├── be2bd7727150eccd65365acb8e670365c5a6e23a.nq.gz
│   ├── cae6e299bbb4d11554fbddefb93b15e5fea92dbd.nq.gz
│   ├── e7706b4d8d96802b8d5344ea63a1512f3289fdae.nq.gz
│   ├── ee5b26c871c3d6b355dba3df899b1a00fee48adc.nq.gz
│   └── f088f2548a840dc91fe3524b1aad8ee8aba54b94.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 2f39a03ca83c5e36566018d888e81b46a9ee6371.nq.gz
├── issue
│   └── issue.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 22 files
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

[NousResearch/hermes-spotify](https://github.com/NousResearch/hermes-spotify)

---
*Parsed on 2026-10-09 by [repolex](https://repolex.ai)*
