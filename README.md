# Repolex Knowledge Graph of tj/connect-redis

RDF knowledge graph data for [tj/connect-redis](https://github.com/tj/connect-redis), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [lexq](https://github.com/repolex-ai/lexq) query tool using [uv](https://docs.astral.sh/uv/getting-started/installation/).

If you have uv installed, just copy/paste this into your terminal:

```bash
uv tool install git+https://github.com/repolex-ai/lexq
```

This installs lexq onto your system, in your user context. Verify the install:

```bash
lexq --help
```

**lexq is designed to be used primarily by LLMs in a terminal.** Start up your favorite LLM and ask it to use the lexq tool. It's that easy!

To load this repo's data:

```bash
lexq download tj/connect-redis
```

This will automatically download essential data files from the last parsed commit. Consult `lexq --moreinfo` for other options, including downloading multiple commits, blobs, etc.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 473bc4abdb5102e89482dc4904e3099009c7be1a
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 473bc4abdb5102e89482dc4904e3099009c7be1a.nq.gz
│   └── repolex
│       └── 473bc4abdb5102e89482dc4904e3099009c7be1a
│           └── chunk-001.nq.gz
├── blob
│   ├── 027a9fa2f83994e36aa994bdce41e97e2cbc9cd2.nq.gz
│   ├── 26454873312a40564c786fb80668cf06e09c5149.nq.gz
│   ├── 31ddb7d522b07a9bbcb9b91aa6608a8eb244569a.nq.gz
│   ├── 33f987ae960aed599da0278ab8903a260da08cac.nq.gz
│   ├── 40ad4addd2f172b09290f7202ebfa104e74d8140.nq.gz
│   ├── 4aba80bd74d067dcafe1ec7981ca24ad4ff0fa41.nq.gz
│   ├── 4b66744bab40fa4200baff07a56b409708f90333.nq.gz
│   ├── 8b615ee045b9d0dd9067739011afd0f6880e6f3e.nq.gz
│   ├── 9c7d1b728ab2b83376c7540e55df31f86cdcf31a.nq.gz
│   ├── a748ffcdf6eecfb036291916eab0ad3862adeee7.nq.gz
│   ├── a7a68263c99794425f3ce6ed1de04d0e2b7f87d6.nq.gz
│   ├── c2d9233dd7d8cb49671823196bf3a474bf37fa58.nq.gz
│   ├── c467582e1774584ac7aedf06972fa56044b42031.nq.gz
│   ├── d9574425a744cb416509bccc910197f098019328.nq.gz
│   └── f81f0d1dbe4af98865d08abfe40ff7ce158e1c52.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 473bc4abdb5102e89482dc4904e3099009c7be1a.nq.gz
├── filetree
│   └── 473bc4abdb5102e89482dc4904e3099009c7be1a.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 25 files
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

## Source repository

[tj/connect-redis](https://github.com/tj/connect-redis)

---
*Parsed on 2026-04-10 by [repolex](https://repolex.ai)*
