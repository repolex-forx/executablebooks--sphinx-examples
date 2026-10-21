# Repolex Knowledge Graph of executablebooks/sphinx-examples

RDF knowledge graph data for [executablebooks/sphinx-examples](https://github.com/executablebooks/sphinx-examples), parsed by [repolex](https://repolex.ai).

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
rlex download executablebooks/sphinx-examples
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 3a7a3300934249b9e32eccd0fbcdd39b3ab9e76c
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 3a7a3300934249b9e32eccd0fbcdd39b3ab9e76c
│           └── chunk-001.nq.gz
├── blob
│   ├── 050620f0956cdf2cbaefda280ccc1b1ffb264731.nq.gz
│   ├── 3f93e0c49e31648444e35443bdda4fc513d745d1.nq.gz
│   ├── 443bb8bd6b31587592c485fc566e1858ace80f2d.nq.gz
│   ├── 4657a92f0e05c2c89d915567c76ae69bfdff78b3.nq.gz
│   ├── 66efc0fecd1554e6e4681fcb149692591f388bf2.nq.gz
│   ├── 6825816332d27a87822f8fc5317373bb70b88056.nq.gz
│   ├── 6bb4e3a3e5f23d3731bf48c709a5e25514602656.nq.gz
│   ├── 7932dee5f3a6d95a16f3d4088edd39143ecb9240.nq.gz
│   ├── 81862f1e2a539c838346baf580b71970cc92298f.nq.gz
│   ├── 8e1bd5ddb3ac1e84fc99f530ff9ac8136872f42e.nq.gz
│   ├── 90c6177a98c9aecd8ab87944848737f62a3bf093.nq.gz
│   ├── a2d1418547ad3e63b874946e1653d59c145874b2.nq.gz
│   ├── bc01d1938d151f614fb16b35285dd610980cbecc.nq.gz
│   ├── be485844ff3ece82c0234cdf4db92a12b3ee4f54.nq.gz
│   ├── c21a88f905c4a98ba57a1d03233c6143237589c5.nq.gz
│   ├── dab6ba48f3dcb26eae65920afb84113b1ebb141f.nq.gz
│   └── f564d0295ef14a20d28d67d7633f9875a0c092bd.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 3a7a3300934249b9e32eccd0fbcdd39b3ab9e76c.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 25 files
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

[executablebooks/sphinx-examples](https://github.com/executablebooks/sphinx-examples)

---
*Parsed on 2026-10-21 by [repolex](https://repolex.ai)*
