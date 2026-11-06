# Repolex Knowledge Graph of sphinx-contrib/sphinx-rdme

RDF knowledge graph data for [sphinx-contrib/sphinx-rdme](https://github.com/sphinx-contrib/sphinx-rdme), parsed by [repolex](https://repolex.ai).

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
rlex download sphinx-contrib/sphinx-rdme
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── d1614380ccde078fbfdf27d004eeedde514c23b5
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── d1614380ccde078fbfdf27d004eeedde514c23b5
│           └── chunk-001.nq.gz
├── blob
│   ├── 1028d666bd9c5e0f3d158bd6baab0615b2600df4.nq.gz
│   ├── 1037ba8ec4c742388751bb5357f1ad9740a9ebb7.nq.gz
│   ├── 1e340322424fed0596edae2ff31879ea791d360f.nq.gz
│   ├── 269352f78016bd6a449e85fa905d50c8f454a0a4.nq.gz
│   ├── 2877b422d804942bb1be04e7b3912e4c0e49f590.nq.gz
│   ├── 375f6721b5632b7cb2e137f82f7e0a6eb1ae2588.nq.gz
│   ├── 42b639ac5b5cf49d4b657e4445a352d7548c99d4.nq.gz
│   ├── 5b4d8c20a582424f7945fd61bb38aac747181d94.nq.gz
│   ├── 667cd5ad510b7c02dbfa838d54ba79bffb08a26d.nq.gz
│   ├── 8560f0ee058d3b9cf7e39181264c8aebed8c29a5.nq.gz
│   ├── 8d3cd2289c9b9a475a44edd69d997a9bf9b2997a.nq.gz
│   ├── a6d31c5cc9e35bcbbb56be295032ea3270adfeec.nq.gz
│   ├── c9744766db8c724ad05e531468b2090fe807dc09.nq.gz
│   ├── d1ef35d7edd7cfc7506a5aff1c22606235ade9c6.nq.gz
│   ├── df9ccde4bf433568703c7f927413dc58e02b285d.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── ebb5d8072b5290de2ec0165b5dcfd95577d34de0.nq.gz
│   └── f771d560e490268b5d10f95b7108ab0131fcdfce.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── d1614380ccde078fbfdf27d004eeedde514c23b5.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 24 files
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

[sphinx-contrib/sphinx-rdme](https://github.com/sphinx-contrib/sphinx-rdme)

---
*Parsed on 2026-11-06 by [repolex](https://repolex.ai)*
