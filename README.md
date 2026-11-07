# Repolex Knowledge Graph of plotly/dash-auth

RDF knowledge graph data for [plotly/dash-auth](https://github.com/plotly/dash-auth), parsed by [repolex](https://repolex.ai).

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
rlex download plotly/dash-auth
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── a78a757c40c911dc1b558224a953d98d18a4fffd
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── a78a757c40c911dc1b558224a953d98d18a4fffd
│           └── chunk-001.nq.gz
├── blob
│   ├── 0444d3c8ab59c4e08147f4dceb4c559db0606a47.nq.gz
│   ├── 072f15428e472a3e63229fe8fa1fa03cfa2f3dd7.nq.gz
│   ├── 1a6a5340af557c91f4432fc8fc8f93b8750a15cf.nq.gz
│   ├── 2f4988dca24af5d6208ea10c4f3cafd75c0bf6b0.nq.gz
│   ├── 329daaaf33424a4c1ee602b90950e2366965938f.nq.gz
│   ├── 4f6703781b6a57a0aae86da22f19e678a9955a9b.nq.gz
│   ├── 5442a67ebc56b36ba9a3f583e604754d59d8a1f9.nq.gz
│   ├── 653770e87d87aa08dbfe99b240bad23533f934a4.nq.gz
│   ├── 72b6e20097ef229b5c9b5d7524ed3f8147d8b50c.nq.gz
│   ├── 82190396f2ff50b1bddd2bf9495146ebc4265d13.nq.gz
│   ├── 862bb5e7b35e6a0c49b30c7481565e6922acf751.nq.gz
│   ├── 86e6c7ef660c05f5642c51deadf29dc69b346ca8.nq.gz
│   ├── 8b16d3d9a5bb039353d42c45bb8d95f98d321fab.nq.gz
│   ├── 8ba759b15d72a53895614ecba399d00959bc8f6d.nq.gz
│   ├── b30a55a604bc67731aa6657626e77e154bdf1f31.nq.gz
│   ├── b3cc0abad3d92d20ae8eb4b5b51d3a985b6bfe89.nq.gz
│   ├── bb3ec5f0d4c70ef732aa4d399282a5ddb2a008fd.nq.gz
│   ├── bc7984c4d2811c197ad70ad5d7f97e21c482d9d3.nq.gz
│   ├── bc8371522911dae5c57fa15028a9c84eeb316709.nq.gz
│   ├── c281f7031b7f9977b332de3eb5452aa0993af36f.nq.gz
│   ├── dab733549dcd28d6ab4cfcb99f43a60ca34f8c60.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   └── f8be30d59b90a1cbfd6c029ffe16f3f7e2af5e7f.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── a78a757c40c911dc1b558224a953d98d18a4fffd.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 31 files
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

[plotly/dash-auth](https://github.com/plotly/dash-auth)

---
*Parsed on 2026-11-07 by [repolex](https://repolex.ai)*
