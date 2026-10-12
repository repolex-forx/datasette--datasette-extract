# Repolex Knowledge Graph of datasette/datasette-extract

RDF knowledge graph data for [datasette/datasette-extract](https://github.com/datasette/datasette-extract), parsed by [repolex](https://repolex.ai).

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
rlex download datasette/datasette-extract
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 4456f54f0cebf6aee9d0d5f7ee06f5988b34402e
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 4456f54f0cebf6aee9d0d5f7ee06f5988b34402e
│           └── chunk-001.nq.gz
├── blob
│   ├── 0d25eba987fb60d3a9c7f24c033b6d9a333e92ea.nq.gz
│   ├── 261eeb9e9f8b2b4b0d119366dda99c6fd7d35c64.nq.gz
│   ├── 3334a3c009f25a2c8b9512b847f8869090f8e8db.nq.gz
│   ├── 3760d9298c95ef38b9eaa7e4f89eee03c5872494.nq.gz
│   ├── 3eb871944ba060e652582342cecb018b41f78bda.nq.gz
│   ├── 6a0888c40f0230316524a86e9170e6e5d4509fe7.nq.gz
│   ├── 8b7614194523a8af3a358edf9186a3a09241dab6.nq.gz
│   ├── cc91a5279aeec0bc0eb85688744df1280a895d93.nq.gz
│   ├── d49d309499efb2c0c1d38efdd53056249a7d74d8.nq.gz
│   ├── dbbe30ad39a64f2a335ad59736dcaa8bc0fdd9ce.nq.gz
│   ├── dd3d4e8906d3ca043602e1ae5151b038eb71832a.nq.gz
│   └── f4ae73edce9ec5d061659caf0f328bdff701ced5.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 4456f54f0cebf6aee9d0d5f7ee06f5988b34402e.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 20 files
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

[datasette/datasette-extract](https://github.com/datasette/datasette-extract)

---
*Parsed on 2026-10-12 by [repolex](https://repolex.ai)*
