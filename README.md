# Repolex Knowledge Graph of BurntSushi/tabwriter

RDF knowledge graph data for [BurntSushi/tabwriter](https://github.com/BurntSushi/tabwriter), parsed by [repolex](https://repolex.ai).

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
rlex download BurntSushi/tabwriter
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 85690b5ed54afdd8c28ebed8800b3736efb0cbb2
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 85690b5ed54afdd8c28ebed8800b3736efb0cbb2.nq.gz
│   └── repolex
│       └── 85690b5ed54afdd8c28ebed8800b3736efb0cbb2
│           └── chunk-001.nq.gz
├── blob
│   ├── 213c95660bcd3fef5d156508b6792471e473c349.nq.gz
│   ├── 2869fec98f72fbe4b7ea36d5128ee1650cb34370.nq.gz
│   ├── 2ea7420d4ec49efa257c3bf3dffb48a19f067338.nq.gz
│   ├── 3b0a5dc09c1e16357459ddc9182a50f360f3cdba.nq.gz
│   ├── 4af789ea6b8fff2cb0b996c80ff39eb0866c2cbc.nq.gz
│   ├── 68a49daad8ff7e35068f2b7a97d643aab440eaec.nq.gz
│   ├── 6a9db4767826cfd2c0344a92dc68f9b5d237d59c.nq.gz
│   ├── 6e2959d63f549f91cc04daa3383b5f19fef3661d.nq.gz
│   ├── 72d19fbc142582ac6f1e5df590c3cbfbda1b08fa.nq.gz
│   ├── 9a61c724e023c3a6cd0cfabefa8779bc3286f370.nq.gz
│   ├── 9da4a887b378612ab61c056f3f007272386bdaeb.nq.gz
│   ├── a07797915fb8d3c35f767b1f2739e833f542cd61.nq.gz
│   ├── a3344b8239f514d14122a89c45b535acc03b33dc.nq.gz
│   ├── a949e53b97e86ef86c8ff2cddb2f658a80c37b70.nq.gz
│   ├── aa37a218b97e5f6ad37a74a62b50727279a5e460.nq.gz
│   ├── bb9c20a094e41b7632d63bcff20c0b4b95e80777.nq.gz
│   ├── db025d912f570983a0a18acb7e6ad08578af5add.nq.gz
│   └── f7bcf5e94d1ed3b988310393f52c4ef87b26dd14.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 85690b5ed54afdd8c28ebed8800b3736efb0cbb2.nq.gz
├── filetree
│   └── 85690b5ed54afdd8c28ebed8800b3736efb0cbb2.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 28 files
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

[BurntSushi/tabwriter](https://github.com/BurntSushi/tabwriter)

---
*Parsed on 2026-11-22 by [repolex](https://repolex.ai)*
