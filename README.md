# Repolex Knowledge Graph of huggingface/traj2envs

RDF knowledge graph data for [huggingface/traj2envs](https://github.com/huggingface/traj2envs), parsed by [repolex](https://repolex.ai).

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
rlex download huggingface/traj2envs
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── a09204ed6d4b38ae549acce3ba462f5561367556
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── a09204ed6d4b38ae549acce3ba462f5561367556
│           └── chunk-001.nq.gz
├── blob
│   ├── 0388c4e6eb2f5c036479d8d847cd8dc8433c2dd4.nq.gz
│   ├── 04647228f637694972fcec3497a2b2f2581afc0e.nq.gz
│   ├── 0befa1cbbcc6a0d45f23121b1b5caade53160eb3.nq.gz
│   ├── 1dc4a6a2bfac4bfd4c5ed79b3e7836c86711a880.nq.gz
│   ├── 20b6586636c2c60e462df63e08cebfa9f2cfdc21.nq.gz
│   ├── 264ab15b2f8d99744f57cc1619834effbd037fc9.nq.gz
│   ├── 299ca0b73291b055b89ce8bac97d6271d128fb65.nq.gz
│   ├── 2c5cbff5fa1bb51a428d65bb2b187cfd9723892a.nq.gz
│   ├── 2edb9ae3c40bec14bd4693afe5fbd491b63746bd.nq.gz
│   ├── 3f64ce0cbc65522bf19945015f8955114042b8f4.nq.gz
│   ├── 5fa7b72e67a16ba19fd28612fad52a8f75d36464.nq.gz
│   ├── 708af40e94aa23ce9190e230079537153282dd85.nq.gz
│   ├── 787b4806f5c11cc32f47878dc597e192a568566c.nq.gz
│   ├── 96b1ff00452e82a1488a5fe81e3a184370a5cc42.nq.gz
│   ├── 9b4250eac107e4c2aa5243fa382e73fc6a5d7238.nq.gz
│   ├── aacc5847cf74b67bcb7880689041ee14b84ddea5.nq.gz
│   ├── aae6521279b1ec5981a2099331420ebdee27d80c.nq.gz
│   ├── b267d2f1b8e50a6bd284733c0012414ec8733251.nq.gz
│   ├── b98ccb57c840bc36f7cb483871434b2ded97eb93.nq.gz
│   ├── be50fb7d87ca88fb4631aec1ecd64ed5ff82ec67.nq.gz
│   ├── c46c20189865f2c93d497015f84abd2e7ef6c838.nq.gz
│   ├── d1774acab08fcde98f360fbd5efccfe9ed6e0f47.nq.gz
│   ├── d1d74d326451c0b2f211503cf3119e6d7714cbea.nq.gz
│   ├── d645695673349e3947e8e5ae42332d0ac3164cd7.nq.gz
│   ├── e30e401f70171c7ea68471d8648325fb28447eaf.nq.gz
│   ├── eb2eda7e10256f9baaa4d3897232fe61eef3d464.nq.gz
│   ├── f0f4129b0dddc216f56c7f406a6754512a02a20b.nq.gz
│   └── ff4b609a98efc668559b8349d7a08a57813f3345.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── a09204ed6d4b38ae549acce3ba462f5561367556.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 34 files
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

[huggingface/traj2envs](https://github.com/huggingface/traj2envs)

---
*Parsed on 2026-11-07 by [repolex](https://repolex.ai)*
