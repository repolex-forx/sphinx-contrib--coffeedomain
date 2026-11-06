# Repolex Knowledge Graph of sphinx-contrib/coffeedomain

RDF knowledge graph data for [sphinx-contrib/coffeedomain](https://github.com/sphinx-contrib/coffeedomain), parsed by [repolex](https://repolex.ai).

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
rlex download sphinx-contrib/coffeedomain
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 1b0cbda761e8bf182d925a788ccecc370f9cfb47
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 1b0cbda761e8bf182d925a788ccecc370f9cfb47
│           └── chunk-001.nq.gz
├── blob
│   ├── 057783b11a2bf02e745f278573107fa9209a2330.nq.gz
│   ├── 11d595857564f3557f31989c0ff1615474a0afa2.nq.gz
│   ├── 381bd5ae9c6e617e769a85582cfe2b35d8838afd.nq.gz
│   ├── 611fdb821f32323921426f0dbdec273f98e06a4b.nq.gz
│   ├── 918a92499e47dd958ed6c046835fc71c2b6b35fa.nq.gz
│   └── b5a7dc29ef0f7f3593b1c61cfc5dfe8a17d3918c.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 1b0cbda761e8bf182d925a788ccecc370f9cfb47.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 12 files
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

[sphinx-contrib/coffeedomain](https://github.com/sphinx-contrib/coffeedomain)

---
*Parsed on 2026-11-06 by [repolex](https://repolex.ai)*
