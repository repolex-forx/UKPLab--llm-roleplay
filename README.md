# Repolex Knowledge Graph of UKPLab/llm-roleplay

RDF knowledge graph data for [UKPLab/llm-roleplay](https://github.com/UKPLab/llm-roleplay), parsed by [repolex](https://repolex.ai).

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
rlex download UKPLab/llm-roleplay
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 92b3950dc49df78a6ee0ae36f7b6d064921d921a
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 92b3950dc49df78a6ee0ae36f7b6d064921d921a
│           └── chunk-001.nq.gz
├── blob
│   ├── 083e5bed7583bbd696b30647c991860dae7280ce.nq.gz
│   ├── 0cd12a45a94d6f4c38bceed076b6fcdd018bc715.nq.gz
│   ├── 0ef4dd9dbbd4b7c15332a05cfc96805d86ead8e1.nq.gz
│   ├── 25dc3a32d27802b1b5fe62911e8540a7ba342c57.nq.gz
│   ├── 2adf85f336950ffb778031115b47a7ae8d4ec84a.nq.gz
│   ├── 3281d1df56a6719cd0376f57c21f1afa1488678f.nq.gz
│   ├── 49ef2b2acdef1c822d302352b3c2d7d5dfd23d0a.nq.gz
│   ├── 526d17e58993b5292676f1700b80e8cde83b2ae6.nq.gz
│   ├── 560070ae042e1f683039243491f154976ccafd4d.nq.gz
│   ├── 5b8f238513568492c9c53a79a767903da1509533.nq.gz
│   ├── 5df5af8625b644af09b7cff4b31eaadd07a437b7.nq.gz
│   ├── 5edc7ce00685f8b22f694fd276061d283463f3a0.nq.gz
│   ├── 6e58c53ab3a229800700864f6738b033c1d5b079.nq.gz
│   ├── 7917094a96a314153b33895e83545ed7c3a02aaa.nq.gz
│   ├── 81ea84d316df6d122c15c38779d5a28efa5cf098.nq.gz
│   ├── 8632e45c21ad4db6a83b34dbea02b08251111d90.nq.gz
│   ├── 9050e2149c3ab5d12ca0a0ab7e1831a969ddef1d.nq.gz
│   ├── b8b9f8adf5f536ff099c1ec52dc50d6a614fb292.nq.gz
│   ├── bf34cae6051335e5986697f74be80e7f59364d62.nq.gz
│   ├── c354ab16965381a0b7eb2b54c831b21558a3b089.nq.gz
│   ├── d2b4eed55f3b6501a8371cfa50dc611696a45058.nq.gz
│   ├── e21750eacadac16e385af6bde4362fa997fb02d1.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── e8f41f06d07e920e0938451fdc3e027e51751b23.nq.gz
│   ├── f20af45d953f5c3c02334fb848d938daefc1494d.nq.gz
│   ├── f49a4e16e68b128803cc2dcea614603632b04eac.nq.gz
│   └── f5c63ddde83bf3162ee9cd148d14b4e36f996ff4.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 92b3950dc49df78a6ee0ae36f7b6d064921d921a.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 35 files
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

[UKPLab/llm-roleplay](https://github.com/UKPLab/llm-roleplay)

---
*Parsed on 2026-11-08 by [repolex](https://repolex.ai)*
