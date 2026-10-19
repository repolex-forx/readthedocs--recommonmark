# Repolex Knowledge Graph of readthedocs/recommonmark

RDF knowledge graph data for [readthedocs/recommonmark](https://github.com/readthedocs/recommonmark), parsed by [repolex](https://repolex.ai).

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
rlex download readthedocs/recommonmark
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 0df398dbca128ce9d6f48f960bb40b9242642a5f
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 0df398dbca128ce9d6f48f960bb40b9242642a5f
│           └── chunk-001.nq.gz
├── blob
│   ├── 0c7ae20da9cd0463936560f9a3dd9656f2e332e7.nq.gz
│   ├── 0f8bf6088090caad76f3a3ec93ba20ab8bff3043.nq.gz
│   ├── 2fc75d535749421c0ff90c220a13951dbbf13921.nq.gz
│   ├── 32d46ee883b58d6a383eed06eb98f33aa6530ded.nq.gz
│   ├── 32fd11811a2536f2d8493c66cebf233cfc5285be.nq.gz
│   ├── 3d9dcbeeaf2549aa5fd103515a33dc31a6ea2cd4.nq.gz
│   ├── 409f176a627baedde24d59dce01f94b953470bda.nq.gz
│   ├── 443a026c744c5193e6ebaada5893073e70eeb084.nq.gz
│   ├── 45c26dfb10f0edfa8f9d79d16cd31d92f9018987.nq.gz
│   ├── 4b13dd89187d93daafe9ab95d54cfc65b389bc08.nq.gz
│   ├── 59fc8362229c87ef67e535f3bcf1032acc37f9d6.nq.gz
│   ├── 5a9f7a92f4c49dc9221c6d3024bc890100fe215b.nq.gz
│   ├── 649035a6132fcc209fd3ad7d99d984ccec65e20f.nq.gz
│   ├── 649e8c0117282c07067173f55ccd61881ac0e331.nq.gz
│   ├── 66eb4e73b7539464020eec718b0944e0e33acd27.nq.gz
│   ├── 6ac9d526f105deb05dff1878feb571230599d0cb.nq.gz
│   ├── 6b0140e8259bca7279d25e9624a10db5a6f2715b.nq.gz
│   ├── 73efff991f2c2eb2d1cd9a0ba1bd04f38edacef8.nq.gz
│   ├── 74f83cf8a490d5934032530081f1809dee29257e.nq.gz
│   ├── 7977449f37bc24d59ec8e092af767a91a4da915e.nq.gz
│   ├── 8565b3595714564c47d3cd4569a6c9416336168b.nq.gz
│   ├── 9bfccf2dd719433f71ed7601405aa0b2ad54daa5.nq.gz
│   ├── 9d0a2a9e70db26218b71c922916d62c440ed964a.nq.gz
│   ├── 9dd39755fd54387d7d4fa9740e223f504daea394.nq.gz
│   ├── a67cc99e6e642604a61dfe5d68febfc6f9087c4e.nq.gz
│   ├── a6fbfc2504223d0de36b6914705cb34179cd9368.nq.gz
│   ├── ae1cf55c0e4fd071e791df5482da0635922f2335.nq.gz
│   ├── b29157b09b1e9b58b35b009e727098d23c60d2c5.nq.gz
│   ├── b90fcf4ff5f4cb0a7134224309f43d430dd4460f.nq.gz
│   ├── e2beb4d0aed8e92511a8f09a9439da509755c5dc.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── f10edb6f0d575a658c7f1f0162ee41833e82cbe1.nq.gz
│   ├── f4410713f051814462e646c933703217a842147f.nq.gz
│   └── f6008f4be3deb8a37fd7dcf8641ebcc470786128.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 0df398dbca128ce9d6f48f960bb40b9242642a5f.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 42 files
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

[readthedocs/recommonmark](https://github.com/readthedocs/recommonmark)

---
*Parsed on 2026-10-19 by [repolex](https://repolex.ai)*
