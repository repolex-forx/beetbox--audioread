# Repolex Knowledge Graph of beetbox/audioread

RDF knowledge graph data for [beetbox/audioread](https://github.com/beetbox/audioread), parsed by [repolex](https://repolex.ai).

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
rlex download beetbox/audioread
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 9b749f0c4d61df763ac6dbf151c64a2366fcf2c3
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 9b749f0c4d61df763ac6dbf151c64a2366fcf2c3
│           └── chunk-001.nq.gz
├── blob
│   ├── 1330a402567ecbcbe16313fe56ba3bf52cbe13da.nq.gz
│   ├── 26e03fc39c07c1c505a7a7ea8e67a147676ed002.nq.gz
│   ├── 29202c91d593376745250e7cd2836d1ae24fc9aa.nq.gz
│   ├── 36b4dd8db02130b8dcf3819e0949e79a0c252230.nq.gz
│   ├── 66804ed91f2f067143fe85013893cd18ffb9bc70.nq.gz
│   ├── 6c2ef510a842a77790f1b020c730b4f80b2cb4c9.nq.gz
│   ├── 73c3db219bb51298b52c48036a315fa1c49e93ac.nq.gz
│   ├── 8073f91b665fcf11e00c39cf29fbb7966dc62ad2.nq.gz
│   ├── 8230e246f18879faa9d9649ceafee22499e6cb8b.nq.gz
│   ├── 849ddff3b7ec917b5f4563e9a6d3ea63ea512a70.nq.gz
│   ├── 95ce41201b327b9ab4fd557ce22ff4b615acb15f.nq.gz
│   ├── 99f2124b45cf531db505eae677944fc4a5da768e.nq.gz
│   ├── 9d16f6fcffc34788166f4c7c28f78c3513a503f2.nq.gz
│   ├── 9df9c5ab325db5fc6ea76c87bbb235218ae27beb.nq.gz
│   ├── a2e5a6abdac798bfac7f6cb89d2fc63093a15208.nq.gz
│   ├── a7010af780162fa328951897ffacb99ab00bc9dd.nq.gz
│   ├── a971549442a1a4ba728a45ee8fc4add49eafd523.nq.gz
│   ├── af6d9bff08ae62d3c186303aab391fd2c8702224.nq.gz
│   ├── b44e37d87b062f36258e36ea4f8060d46f7a20da.nq.gz
│   ├── bbd4c768d0f4f90d7088f1142efbeb69011e142a.nq.gz
│   ├── c0ca48023749e10f53c33394f86105a9b0ffa25a.nq.gz
│   ├── c605f327f156233d2b8386f6a16dea39c5217303.nq.gz
│   ├── c74459bb1303217e4d90e184544459899bc7f885.nq.gz
│   ├── ccc91819737fe25073b2a240f3bb3bc949ecaefd.nq.gz
│   └── f765d696f12d2ec79d311fa75444238c0a1325a7.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 9b749f0c4d61df763ac6dbf151c64a2366fcf2c3.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 33 files
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

[beetbox/audioread](https://github.com/beetbox/audioread)

---
*Parsed on 2026-10-17 by [repolex](https://repolex.ai)*
