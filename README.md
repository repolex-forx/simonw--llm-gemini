# Repolex Knowledge Graph of simonw/llm-gemini

RDF knowledge graph data for [simonw/llm-gemini](https://github.com/simonw/llm-gemini), parsed by [repolex](https://repolex.ai).

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
rlex download simonw/llm-gemini
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── e8de0b30d641844f62f2d766a0fada76d7f49c20
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── e8de0b30d641844f62f2d766a0fada76d7f49c20
│           └── chunk-001.nq.gz
├── blob
│   ├── 18e191648416b0316c09a75941c25cf7a3bd0537.nq.gz
│   ├── 261eeb9e9f8b2b4b0d119366dda99c6fd7d35c64.nq.gz
│   ├── 3004fed3491c2da660e88f6736c3ef4040901569.nq.gz
│   ├── 37ec7c85f446423ec7136711d54141c99a605127.nq.gz
│   ├── 3ab06375eb2d1fe83cd248fe25416911fe79c5d2.nq.gz
│   ├── 3e29aa926fc2ddc9aaeb71023a7c6eb2c15fa902.nq.gz
│   ├── 4b7ae8bc05088b12a63b5f11d1ea4a93f12b245f.nq.gz
│   ├── 4d37546307bb07a6a4226f594b40bc32632ad146.nq.gz
│   ├── 5e558e620a2e8aae1ca287eec823a35c21513e2b.nq.gz
│   ├── 7c185326f909cf6b599f9dca738f65e41008498a.nq.gz
│   ├── 9163c19999764d85c34ff8a5dc94952225523fb5.nq.gz
│   ├── 929965fb2e13ceffff6d01ce18dd73f14fc09310.nq.gz
│   ├── 9e1ff29a88680cc52ddab54750f092c6ae0d073e.nq.gz
│   ├── 9ef9ce2701a5d2eed35b51ae04516910ba374ca4.nq.gz
│   ├── a9fe5b5e65e7952a10a2c4622c0cb4a2c5807e0a.nq.gz
│   ├── c329294c50898b341c717c03594252452fcb3787.nq.gz
│   ├── c496d663edae84a8363a4d4f24601b6ad9409a84.nq.gz
│   ├── c897e856debabe4f743e4c1181006011460e5287.nq.gz
│   ├── ce1a83acebd3acf4101d73ea884a2e7acd33698f.nq.gz
│   ├── d0d5ce3ee8fa6494d61b4f902ee7d8de943e1b36.nq.gz
│   ├── d726b9e517d48d6e79807c207546f35014edc356.nq.gz
│   ├── e28177bec437bb635060594c907fe271a7daec39.nq.gz
│   ├── e40b1215cdebf9a8b5a33452328098fdd5830773.nq.gz
│   ├── e87d86eab877b97a1ca360fadbc9cf5ff3518a70.nq.gz
│   ├── eaa71ecb76f18b24a790c4580dba0d28cabc0c8e.nq.gz
│   └── fa09acdb8f72825ca0b500fe73dc883d9e669e2a.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── e8de0b30d641844f62f2d766a0fada76d7f49c20.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 34 files
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

[simonw/llm-gemini](https://github.com/simonw/llm-gemini)

---
*Parsed on 2026-10-12 by [repolex](https://repolex.ai)*
