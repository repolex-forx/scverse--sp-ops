# Repolex Knowledge Graph of scverse/sp-ops

RDF knowledge graph data for [scverse/sp-ops](https://github.com/scverse/sp-ops), parsed by [repolex](https://repolex.ai).

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
rlex download scverse/sp-ops
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 4444ac9d0c389f9c365db6f6c45085754a1f0902
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 4444ac9d0c389f9c365db6f6c45085754a1f0902
│           └── chunk-001.nq.gz
├── blob
│   ├── 05bb7caae10ba4b0959c28148badd8600e92ac9b.nq.gz
│   ├── 06c68591c075ff231092f752d3b7a51e854ba503.nq.gz
│   ├── 2b3377dfda0bcbcb0dd3d78d742086f02ede6b96.nq.gz
│   ├── 3887e9f03603f0edb456a7f0549b565a07df17b1.nq.gz
│   ├── 4c180d513f9a24cf067ce6ccda25da290b853cb3.nq.gz
│   ├── 574a4f9c93a6c88f8782ab953ce732bb7fd7a5d2.nq.gz
│   ├── 5d72dfc102d749100c8fa451642e86e0bce9d436.nq.gz
│   ├── 63d42df5e809db969162f0391bf7a215796e22d6.nq.gz
│   ├── 6b300b1591f303f33ffc5756766f16d7dad0d72d.nq.gz
│   ├── 6e5933e9043733096ef32e89f0e1f6112586450e.nq.gz
│   ├── 73168b985c543417a3596d9e2eb9c2a949a91cda.nq.gz
│   ├── 7b9548a101773a4414ba74a71a9c76896652f58d.nq.gz
│   ├── 7b9a74cd6772819b45ef59b5b9042e1d89e5111a.nq.gz
│   ├── 8a7b01bbc6a57dbbaff89b036b822f373db508ab.nq.gz
│   ├── 8b1b5ef2d366ebe0561f5f5d14bc6197d85d0bc8.nq.gz
│   ├── 9615b0f2eb851d8462c8b17d4b566afc098c9b12.nq.gz
│   ├── 9f0cca6d4d1f3468a91d5e2349bff37888dd376c.nq.gz
│   ├── a07627936dc05a95c54aa12787ff2615f6f05f4e.nq.gz
│   ├── a130f855509f9911e59ad162e368a1b4f458f336.nq.gz
│   ├── a8bec62650f745717d9f327b1d67112762b5eed6.nq.gz
│   ├── ac0bddcfd4e7c049a49fcc515892d6fb9357e644.nq.gz
│   ├── cccdb9388ed92c2fe248da7aa84c062551ebccee.nq.gz
│   ├── cd5afe6eaa33a1a24d3752e1663682face91195b.nq.gz
│   ├── ced0c8e242d203c2400a11494ac6994a726ff0d4.nq.gz
│   ├── d0f5e661a7f3aa38e75d5d0c9b0cca52ba1475ea.nq.gz
│   ├── e05c3b2b41ad543d9b7c43c561e61780b2cea478.nq.gz
│   ├── e4e5e6c7e068fca4ebbc31b3fed70e7b4b65ea5a.nq.gz
│   ├── e4fba2183587225f216eeada4c78dfab6b2e65f5.nq.gz
│   ├── e6c49959f02423e8060142cff0f0feb6804f0e9a.nq.gz
│   └── ea97351fab144364546b2b418f3417068c418876.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 4444ac9d0c389f9c365db6f6c45085754a1f0902.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 37 files
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

[scverse/sp-ops](https://github.com/scverse/sp-ops)

---
*Parsed on 2026-10-21 by [repolex](https://repolex.ai)*
