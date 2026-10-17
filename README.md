# Repolex Knowledge Graph of colcon/colcon-mixin

RDF knowledge graph data for [colcon/colcon-mixin](https://github.com/colcon/colcon-mixin), parsed by [repolex](https://repolex.ai).

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
rlex download colcon/colcon-mixin
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 47fc23fff7b9e5ea391705def9cc7fb29ff45c32
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 47fc23fff7b9e5ea391705def9cc7fb29ff45c32
│           └── chunk-001.nq.gz
├── blob
│   ├── 0a00e73455cc03dff6a5f9e344329ebe0374673e.nq.gz
│   ├── 0d570b3d07ff09725dbcd24ac9c27838893ed2be.nq.gz
│   ├── 110093e5542f6eb63ac47c4d95ab4eee3fc508d0.nq.gz
│   ├── 167a2c1b103011581d168b29f22951341420feb0.nq.gz
│   ├── 18ebb1690adad6898e875cf6f05ab57c9729e2b3.nq.gz
│   ├── 2eaae40d58055259e104ed5d554c332de4c8cc09.nq.gz
│   ├── 3a14cec0f3a70331c115de68d4e5647da331dc68.nq.gz
│   ├── 4531b86272bc912b3eaaee1f7f0675ffedfc688d.nq.gz
│   ├── 559192b354556acc0082293b669bf0b3c377d2f5.nq.gz
│   ├── 6da1bc1dd148bd47908a301e393a1de8f00113d3.nq.gz
│   ├── 71737ef42b6bad1d78abbc26b6ae62f011067116.nq.gz
│   ├── 793c944701eca906a6e246c897c9410ecae5a00a.nq.gz
│   ├── 7f930f081e685013b2596b4b7cdce0a7ee854d54.nq.gz
│   ├── 8193709d7aa24233951af41979d16fabcc8de5a0.nq.gz
│   ├── 836a06d9d54e7e7120c6cd78dfa7e711ba5978c8.nq.gz
│   ├── a1fb03ce0f3acebcb5f3853a4b61f667ea5c6bda.nq.gz
│   ├── b3bcaf1117b4aba26453f7548edd1ea676f5087c.nq.gz
│   ├── bd17c0c76729c095bde6af6a894d035861e07d08.nq.gz
│   ├── be469dc97bbbbe48a043ae06362a4bd5752727fc.nq.gz
│   ├── d4099a68b3ce6a2b83cb825a20f0c3e61f6d2323.nq.gz
│   ├── d645695673349e3947e8e5ae42332d0ac3164cd7.nq.gz
│   ├── dffe460f162da9929178a7ce342532e7ba896425.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── e82fd0b0abbf1472480d19d468efe7819276e80d.nq.gz
│   ├── ecdb2c73df7396c7e48c9fa4bfd422d3e0b3ca4f.nq.gz
│   ├── eec9e30c9e940305447ff9121b38e4135daf550f.nq.gz
│   ├── f6616786163e7e75739324d5afcba496313a2073.nq.gz
│   └── fda11e9406a68933cb36b1438eac9d4cdbb2992d.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 47fc23fff7b9e5ea391705def9cc7fb29ff45c32.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 36 files
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

[colcon/colcon-mixin](https://github.com/colcon/colcon-mixin)

---
*Parsed on 2026-10-17 by [repolex](https://repolex.ai)*
