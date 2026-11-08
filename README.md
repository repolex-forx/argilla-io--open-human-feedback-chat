# Repolex Knowledge Graph of argilla-io/open-human-feedback-chat

RDF knowledge graph data for [argilla-io/open-human-feedback-chat](https://github.com/argilla-io/open-human-feedback-chat), parsed by [repolex](https://repolex.ai).

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
rlex download argilla-io/open-human-feedback-chat
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── d8dddd15df0f5cb43cedfe39e72b4006f52b2020
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── d8dddd15df0f5cb43cedfe39e72b4006f52b2020
│           └── chunk-001.nq.gz
├── blob
│   ├── 261eeb9e9f8b2b4b0d119366dda99c6fd7d35c64.nq.gz
│   ├── 2c0733315e415bfb5e5b353f9996ecd964d395b2.nq.gz
│   ├── 2cea24e40be0e9dd1a8c95c43570c3a76ddeade8.nq.gz
│   ├── 2e4712a6b2566466a9ee1d2609a766ac8388c266.nq.gz
│   ├── 306eac492390928bedb7a6671bf310531cd31166.nq.gz
│   ├── 6ca0a4d39376cc2aaa813678a5de0cbcf4e8b052.nq.gz
│   ├── 752c6b72b333dc240e0ecc45037bdbabdb622920.nq.gz
│   ├── 77f208ac1054fab4393ec0786ac86b509134ff83.nq.gz
│   └── d4cf7c5e2a64c23663cc252c8faf52efc2dd0660.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── d8dddd15df0f5cb43cedfe39e72b4006f52b2020.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 16 files
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

[argilla-io/open-human-feedback-chat](https://github.com/argilla-io/open-human-feedback-chat)

---
*Parsed on 2026-11-08 by [repolex](https://repolex.ai)*
