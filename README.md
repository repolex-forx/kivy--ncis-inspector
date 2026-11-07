# Repolex Knowledge Graph of kivy/ncis-inspector

RDF knowledge graph data for [kivy/ncis-inspector](https://github.com/kivy/ncis-inspector), parsed by [repolex](https://repolex.ai).

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
rlex download kivy/ncis-inspector
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 61a0182a0e6011335c265980b13095af2eaa4dd9
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 61a0182a0e6011335c265980b13095af2eaa4dd9
│           └── chunk-001.nq.gz
├── blob
│   ├── 02799d5b6a27afded57e7d7637b51372d1caab4d.nq.gz
│   ├── 099d51859fa02cc51d28969207240bca01570482.nq.gz
│   ├── 107510557ed844f89fe84ea610f4b736ed089900.nq.gz
│   ├── 1344f1f7faee1bd288f6b06ef25101fc8ca3b3f0.nq.gz
│   ├── 19d625974076a0857b808efb04e0ebeb00ee976f.nq.gz
│   ├── 1e5fb455a280c1ed87fe3c6fd3d52841ae388ba4.nq.gz
│   ├── 1e8f78f7214dcc023d6b0bb4f1f6524e30b57628.nq.gz
│   ├── 20c43bac540e5c0004cc75d6b76d73989351af50.nq.gz
│   ├── 46777732a06b1c860ca756880375f78ddffb926f.nq.gz
│   ├── 4d27e16dc5d7a0260c3b3f63c28626b42a544bec.nq.gz
│   ├── 531d3eaed8ccf7f51a1f09bf2de4b2e963e5dfdc.nq.gz
│   ├── 545bf1adae9eae62988ef6f3e60ff90a2458c527.nq.gz
│   ├── 59928f88405c7c70db6181f72d3a65902efef814.nq.gz
│   ├── 62412cdc17edffc105351c6316dfb615d0196fad.nq.gz
│   ├── 6ecb013b4434585eef667ce48c97f55265eddeec.nq.gz
│   ├── 6f07a9c419601501df3c4249f7f19f632dcfba8b.nq.gz
│   ├── 70def5168c9d6f347eebabaadef269f3322cfe18.nq.gz
│   ├── 785d1ed302bcb3587624364c70d2a91a506bf128.nq.gz
│   ├── 7e91a47d0ee8d28d10c3ae3704a2d07895a0581a.nq.gz
│   ├── 84eae066ad5b482eab4b781a36ea879979504f37.nq.gz
│   ├── 86ccde634fee671eff103f756aab9c55b01451dd.nq.gz
│   ├── 8c7c75b54ab81b8cf46cbff18386391904c13264.nq.gz
│   ├── 918ea2302f517eff8e684b34b7eb00bd82e4dd11.nq.gz
│   ├── 924abeb0c887754ca1a4da94110446c0fed131f6.nq.gz
│   ├── 9ac8b25f85e18d3493e1da3d16e9a5c5740063f0.nq.gz
│   ├── 9b3869390d5e042e7f6274f42318fc80567ac83c.nq.gz
│   ├── a066236750c9db8e648c0c65094216c0d2d5350e.nq.gz
│   ├── ac5a9562fbd637637048f00b8a8eb86e6dbb4f88.nq.gz
│   ├── adf13212574de60178e3c879788515ef4321c212.nq.gz
│   ├── beaab3366f0de9c53ee27b2255b6687eaeac444f.nq.gz
│   ├── bf250b5f066df2d8311d399dd960d86faea75465.nq.gz
│   ├── d1bef47ccbef3ab9855d1e4472ebf363bd54446a.nq.gz
│   ├── d55b08363e0c8a266d39b24d184936bbbbe1da58.nq.gz
│   ├── d5c70d1e253ab3bf4e867dd5a014d4237bae2c65.nq.gz
│   ├── dec3cc3ec76566d210228b7baa0bfcd5ddad0aac.nq.gz
│   ├── ec98f9b10b04a4dae5c026bcfddd7886c451dee4.nq.gz
│   ├── f39c6aa84961939cd08396923d6a5e94d4594196.nq.gz
│   ├── fbb7b523a874f67d50f64c8b9e0d6333a3460368.nq.gz
│   └── fd693deba397ccdfc919d640f2e45ec4a092854a.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 61a0182a0e6011335c265980b13095af2eaa4dd9.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 45 files
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

[kivy/ncis-inspector](https://github.com/kivy/ncis-inspector)

---
*Parsed on 2026-11-07 by [repolex](https://repolex.ai)*
