# Repolex Knowledge Graph of zenml-io/trmnl-zenml

RDF knowledge graph data for [zenml-io/trmnl-zenml](https://github.com/zenml-io/trmnl-zenml), parsed by [repolex](https://repolex.ai).

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
rlex download zenml-io/trmnl-zenml
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── b3460ce1f49bc2b04feedde9a0ff12dad0e3d294
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── b3460ce1f49bc2b04feedde9a0ff12dad0e3d294
│           └── chunk-001.nq.gz
├── blob
│   ├── 5ef8f24751b7e247915b6ad00667144dace418dd.nq.gz
│   ├── 771a71ca6eceaf802ba28c77f7aeb607e09b96bf.nq.gz
│   ├── 8db293714753e6e2845fef83148f0f26b22ed534.nq.gz
│   ├── 903ba603da154f0c0323f02a8435080219839c6b.nq.gz
│   ├── 98a9f74101c835cbf13acfc5a1f52b7c0371bcb5.nq.gz
│   ├── a8608b2c6a57e72113cd5743a8022109d1db0a96.nq.gz
│   ├── ae303a9caf006064985ed96625c6af2970914dab.nq.gz
│   ├── b199d0bc780250b04566c43145a0d17d9b8ad22f.nq.gz
│   ├── b8a760080856d1b1e36c6a890cf2e20e4c743046.nq.gz
│   ├── ba19908dd2f2722fefd1a385808e9bea2e174b80.nq.gz
│   └── bf74936bd53cbe75734e469a83b23d679bb95393.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── b3460ce1f49bc2b04feedde9a0ff12dad0e3d294.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 17 files
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

[zenml-io/trmnl-zenml](https://github.com/zenml-io/trmnl-zenml)

---
*Parsed on 2026-11-08 by [repolex](https://repolex.ai)*
