# Repolex Knowledge Graph of myusuf3/delorean

RDF knowledge graph data for [myusuf3/delorean](https://github.com/myusuf3/delorean), parsed by [repolex](https://repolex.ai).

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
rlex download myusuf3/delorean
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── eea5ccaf3c25c2939fbe372c35e27c4ef5941b0b
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── eea5ccaf3c25c2939fbe372c35e27c4ef5941b0b
│           └── chunk-001.nq.gz
├── blob
│   ├── 08eb45c3a63f75975f522bafcd75f49403c31d97.nq.gz
│   ├── 108496a50ce2a181f04cf4adf9208ccc72f10af7.nq.gz
│   ├── 12669d702ee9a2bf4c2a87d12a39db5e47ca03e9.nq.gz
│   ├── 1c45b1b917c39f6311219306e25cf8a4c26d3ac7.nq.gz
│   ├── 1c6df309edc8fd9c5aaa21d4a7fb867dd73ba8ec.nq.gz
│   ├── 21008c95d12e08f80598bd6fcff15ebe0456f5b4.nq.gz
│   ├── 253b6163d556dee6572761857fec665f8816da2c.nq.gz
│   ├── 2eb99cadf0ed17c9a9e7d3dd28311b30c9edf230.nq.gz
│   ├── 307a1f0d658343ab2579dffd080f035a94a7e87f.nq.gz
│   ├── 31d14d25f81db2e0471eb5291324c83d8d120922.nq.gz
│   ├── 33f47449c11d241e36c83d7f95d819bbe56e2c8f.nq.gz
│   ├── 3bf23ae7cde8920596785df7767a94d3b7a2fdb5.nq.gz
│   ├── 42c2f6ff2d9b5dd0cef25cd14aa6b4dcc9b24068.nq.gz
│   ├── 487b34b8ab3effff2e580719b6c832633c702135.nq.gz
│   ├── 4dc00ba79cf344bef684e9e5037d927b2ce03813.nq.gz
│   ├── 542b462515db7875ea5813c33181870ae06edff7.nq.gz
│   ├── 5ab5061e3a20606e6e97ac07a49e607042e1369c.nq.gz
│   ├── 5ac813318d62c785529266d54345560c783b18ee.nq.gz
│   ├── 5b6df9a7d182224f2064e9ca24450ab1fb1d2599.nq.gz
│   ├── 6609c09c2669456cfe68e6087d89c53f0b8c33c7.nq.gz
│   ├── 66b6e4c2f3b55b25afd9716f9d3c5afb47b15d4e.nq.gz
│   ├── 6e31097e7928e101b9a95b8ef8169563418a0d18.nq.gz
│   ├── 81f4d30592d3b4270b2f52a135769c1b3df2c36b.nq.gz
│   ├── 8a26b5bd75c2c2bd206ef1e04b9ab1edeabcc5ee.nq.gz
│   ├── 8a8fd8b574f67068cfae88603a307e12ddab399d.nq.gz
│   ├── 93d064a9ffc8bc5c9e92e57eec4d0c0c1590f4a7.nq.gz
│   ├── 94eba1375b27ea02d164422817eb8aef49ad7858.nq.gz
│   ├── b5035432fb46abd9271487567f29d202e3ce2c1f.nq.gz
│   ├── b7c8bad52a6a88b61cf57be6014c4085dc974ed3.nq.gz
│   ├── bae426f877c812829866a009fce05adac5e1c8dc.nq.gz
│   ├── c23afabaf39c46607ba461127fd4fda8bd0218a5.nq.gz
│   ├── d94514208fc5742d96e44041698a738b1cac6b02.nq.gz
│   ├── d9e113ec685b92b018297dd2f200341d1fba01f9.nq.gz
│   ├── f3b82441884a5382a4dc1560dbef499f2d35f1b0.nq.gz
│   ├── f577b5905ce305f6f3b6d7c62ea3e15c57071e0d.nq.gz
│   ├── f74d1fc8bf47b759a70397d253231f017846ec73.nq.gz
│   └── fe2141c565e6976b6a2a5b73f318ad7c6dc3d58b.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── eea5ccaf3c25c2939fbe372c35e27c4ef5941b0b.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 45 files
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

[myusuf3/delorean](https://github.com/myusuf3/delorean)

---
*Parsed on 2026-10-18 by [repolex](https://repolex.ai)*
