# Repolex Knowledge Graph of aio-libs/upload-coverage

RDF knowledge graph data for [aio-libs/upload-coverage](https://github.com/aio-libs/upload-coverage), parsed by [repolex](https://repolex.ai).

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
rlex download aio-libs/upload-coverage
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 31d1bc10402ba71d4d2a28171f41ff4d5a8fefb9
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 31d1bc10402ba71d4d2a28171f41ff4d5a8fefb9
│           └── chunk-001.nq.gz
├── blob
│   ├── 228b47d6709ab5fde8914b4423f0b64e6722ded6.nq.gz
│   ├── 261eeb9e9f8b2b4b0d119366dda99c6fd7d35c64.nq.gz
│   ├── 3f84d778d0ba62779ee906fce60d6904d54d6aa6.nq.gz
│   ├── 45fa05c268577aa14858f034717b0737df3b1d26.nq.gz
│   ├── 4b4a9abbf3196b264dc1c022ba7e0de991597cac.nq.gz
│   ├── 7b723625c1e0fe1b1064140b8ffdcd2fe48c906b.nq.gz
│   ├── 7ce3d793ad450fdfcf6736f6a28e4284da6d5941.nq.gz
│   ├── a99709f7170210ea9a1153178fd042ed0c374482.nq.gz
│   ├── ae8dd8e88a6d4126e24f3dbf20aefa95413f9f73.nq.gz
│   ├── b6e47617de110dea7ca47e087ff1347cc2646eda.nq.gz
│   └── ca26e3b7c30538a15e19c88d6ba84f0d144c3a0f.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 31d1bc10402ba71d4d2a28171f41ff4d5a8fefb9.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 18 files
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

[aio-libs/upload-coverage](https://github.com/aio-libs/upload-coverage)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
