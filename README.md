# Repolex Knowledge Graph of samuelcolvin/grablib

RDF knowledge graph data for [samuelcolvin/grablib](https://github.com/samuelcolvin/grablib), parsed by [repolex](https://repolex.ai).

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
rlex download samuelcolvin/grablib
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── bec5d4fb1bff852b9f60f25b9960b385670c7110
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── bec5d4fb1bff852b9f60f25b9960b385670c7110
│           └── chunk-001.nq.gz
├── blob
│   ├── 07417c7c0a1f0086cfdc99f93301ff9af06eadc4.nq.gz
│   ├── 0df6bda2a5b7002c90b01a804336941d3c626dde.nq.gz
│   ├── 1ecd3f9b6963bae51a6d4fcf73ad349402f49567.nq.gz
│   ├── 242d83f59ab3ea313c982210400fca19c8ead073.nq.gz
│   ├── 25ef144d1f5c09448f7934c9dbc46661dbe2a7d1.nq.gz
│   ├── 361c06602d4b4e608b083db91bde8ec503563190.nq.gz
│   ├── 3e8811e46c7b8b5b99fdf2a54e4a94c84eeee2a0.nq.gz
│   ├── 6fb1bedddd88033679cb1d174a350fb39a4abb95.nq.gz
│   ├── 74e05db3d97280b7cd3f51028502198458c8fd8c.nq.gz
│   ├── 765500e4c669025d48bf2be4c2fe7677943c38aa.nq.gz
│   ├── 775eb4a7cec84a3c8a6ac2c81328f43a791af6a7.nq.gz
│   ├── 7feec57770ce900d8d36943f995afafd9ebd5d9c.nq.gz
│   ├── 8f6b230f7c9011129a180413937fc6e1ecf66f47.nq.gz
│   ├── 9b3f0eee55d239ca3d77d73f5b0d7eca2fe858e6.nq.gz
│   ├── a12b4ab7bb6c71875001c028093b79593ebe7a17.nq.gz
│   ├── a14bb6c64fbf669e7b85631cd24c8994e5752e89.nq.gz
│   ├── a45faff2d93a989458aaf94cf8c3d05e8886b79b.nq.gz
│   ├── a78d84e162b2d1bd2dbc8d0b6e8dae00bbfa456d.nq.gz
│   ├── b80e463a4137f2e8a818553fa1bf5087d71b030f.nq.gz
│   ├── c49dd5fefd6f5a43d57fb050bf9f16e7db43589e.nq.gz
│   ├── c7ec7351c2c06733068882796f467451992cdd11.nq.gz
│   ├── d55e5806dc5757092306a7f5ea40c53623d6f348.nq.gz
│   ├── db7f6f32420f88ddcb982b38c75ead9737b4b285.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── e6a4e4e4ac42e83dbdd9915960ab7c00d2b53fb9.nq.gz
│   ├── ee5d20505d10f346952d88199bc1c7cae586577c.nq.gz
│   └── ff437fb55722e43b16cbbf95d38d0ca5877f576b.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── bec5d4fb1bff852b9f60f25b9960b385670c7110.nq.gz
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

[samuelcolvin/grablib](https://github.com/samuelcolvin/grablib)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
