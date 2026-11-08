# Repolex Knowledge Graph of langchain-ai/gen-ui-workflow

RDF knowledge graph data for [langchain-ai/gen-ui-workflow](https://github.com/langchain-ai/gen-ui-workflow), parsed by [repolex](https://repolex.ai).

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
rlex download langchain-ai/gen-ui-workflow
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── addec0c51e38ca5dbab6f3f470f6ca82ce54a670
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── addec0c51e38ca5dbab6f3f470f6ca82ce54a670
│           └── chunk-001.nq.gz
├── blob
│   ├── 059589643346dae4d667e287242908cf4b90402a.nq.gz
│   ├── 13dbc979df85f65a57a23d731e7da5289480abdb.nq.gz
│   ├── 2b065ea0e5161e02f67519e526f8197c5a8fa1a8.nq.gz
│   ├── 4496147004eed2ad1fdc63784c6fc9a20a3c9daa.nq.gz
│   ├── 46738ce3d5bc0bae55a195abd1005d348369ccfd.nq.gz
│   ├── 89c6946493c1d14da6d5823427be842c746dbb8e.nq.gz
│   ├── a130792447162d752181bf29d8dd307271506af7.nq.gz
│   ├── a3cab12230b134b0b7f91767d394a2d2385a5d36.nq.gz
│   ├── a4814f914654373740cc2596d0e139920c9ec806.nq.gz
│   ├── b15cdd63a30348764ff21d11271eba3bb1fa928f.nq.gz
│   ├── b24b49a173d24d11e15d677aa5d3e13011d2c5ca.nq.gz
│   ├── bddf44fd6452082bbbfa0995c88eabfd2d6f524c.nq.gz
│   ├── c7460a167fd7eec89e708f17a02fbf3247cf77a2.nq.gz
│   ├── c963857a61d61b4c92700282feda4b516dfd0ad7.nq.gz
│   ├── ca8d1f918f7b1792a5a8161d576b3df15263a17b.nq.gz
│   ├── e4a344f88ba1fbb3111acfd45fb4876eb3576d3e.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   └── fa2d411bd40a437a762b80e2940852c955d256cf.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── addec0c51e38ca5dbab6f3f470f6ca82ce54a670.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 25 files
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

[langchain-ai/gen-ui-workflow](https://github.com/langchain-ai/gen-ui-workflow)

---
*Parsed on 2026-11-08 by [repolex](https://repolex.ai)*
