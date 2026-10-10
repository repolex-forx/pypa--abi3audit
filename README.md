# Repolex Knowledge Graph of pypa/abi3audit

RDF knowledge graph data for [pypa/abi3audit](https://github.com/pypa/abi3audit), parsed by [repolex](https://repolex.ai).

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
rlex download pypa/abi3audit
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── a33c6e0fe6988d3a6340b0460589a80c19f1b6b1
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── a33c6e0fe6988d3a6340b0460589a80c19f1b6b1
│           └── chunk-001.nq.gz
├── blob
│   ├── 0760d2a76db7ed9810613529579b70b5a2b3d8ee.nq.gz
│   ├── 082733f2dcf68cf4cdf62301f8c8b44f26b70f85.nq.gz
│   ├── 18036d69e12db3b48a38d49d533f2f14573c8a12.nq.gz
│   ├── 2a6fae4f2dafabbb8c9f74c42269d0addbcdcd62.nq.gz
│   ├── 3d478631e26a23b107d9df12ddbcda19b3dab5f6.nq.gz
│   ├── 4cf152c24ec6bc5ea0d593289caa62b9a9638953.nq.gz
│   ├── 4fc49162f7956ffba44570c73689b439f8334c1f.nq.gz
│   ├── 51f5b6bf86608a82f348d34dafa6fd56bbd2c0ff.nq.gz
│   ├── 5f85ac116621661258d1e2861db99201f7fffe86.nq.gz
│   ├── 635e86da02f0f404843e2cf8c5e5a2e91408508d.nq.gz
│   ├── 751c9f3f4e530fe1ec6982bf1d4ba0e2db13a7c4.nq.gz
│   ├── 77ca6fc2e437265fcd28e86ca66f366bd4aef7cc.nq.gz
│   ├── 7998888355b98b06257e89e56f6d6cf9816f76cb.nq.gz
│   ├── 79be29eef89c03d20f34591d3ec56960d4a57344.nq.gz
│   ├── 964632381be11ca104187a6d2a3d72f76584e379.nq.gz
│   ├── 976c58101a40deddd59a466f65755d4a76c30e52.nq.gz
│   ├── a0702ce345847de019f004a5efe2286c9e36339f.nq.gz
│   ├── acf50e30424af38aae6723dc840fd6847ccf5619.nq.gz
│   ├── c3d584917e6cc771c7ee36910c6900563d1bbf60.nq.gz
│   ├── d8c7e0794e2e7b2ebaeb01f499eef461c7df6db8.nq.gz
│   ├── dd4d89162dfebd8b84ae9da18232bdaa2cee3a6e.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── e7001b484f253741f8dc05eec383443f3a89e8c6.nq.gz
│   ├── e7f6b9a44cb2947637d34b51c7d375774aa1ef92.nq.gz
│   ├── e8b07d1a3c2c1b98f71471cc726368d7096e5a3a.nq.gz
│   ├── e9423bec4464c2efd4c72d06f5174e348176702c.nq.gz
│   └── f7c31db365aa57b600157f0477eb77e65e77c4d1.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── a33c6e0fe6988d3a6340b0460589a80c19f1b6b1.nq.gz
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

[pypa/abi3audit](https://github.com/pypa/abi3audit)

---
*Parsed on 2026-10-10 by [repolex](https://repolex.ai)*
