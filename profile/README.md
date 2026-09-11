# Firelock

Firelock builds **Kin**, a graph-native code repository for people and AI agents.

Kin helps you and your AI agents understand what a code change might affect
before you make it. AI agents can write a change faster than a team can establish what it touches,
whether it reverses an earlier fix, and how far its blast radius reaches. Git
records files and line history. Kin records the software itself as a graph of
entities, relations, changes, and provenance, then gives humans and agents one
semantic authority to query and review.

Kin is a public alpha. It is pre-1.0, so expect rough edges and breaking changes.

## The stack

Kin is one system with a few clear public surfaces:

| Surface | What it does |
| --- | --- |
| [kin](https://github.com/firelock-ai/kin) | Semantic system of record: CLI, daemon, graph lifecycle, MCP, review, provenance, and Git coexistence. |
| [kin-vfs](https://github.com/firelock-ai/kin-vfs) | Projects graph-owned files through normal filesystem calls so existing tools can keep using files. |
| [kin-editor](https://github.com/firelock-ai/kin-editor) | VS Code access to the entity explorer, semantic search, trace, review, and rename surfaces. |
| [KinLab](https://kinlab.ai) | Hosted collaboration and control plane. |

## Install

On macOS or Linux:

```sh
curl -fsSL https://get.kinlab.dev/install | sh
```

The installer edits your shell profile, so open a new terminal (or run
`exec $SHELL -l`) before the next command. Then wire up your agent:

```sh
kin setup --intent agent
```

Homebrew and npm resolve the same public release channel:

```sh
brew install firelock-ai/kin/kin
# or
npm install -g @kinlab/kin@latest
```

## Supporting libraries

These Apache-2.0 crates are the implementation layers behind Kin, not separate
products a new user needs to assemble:

- [kin-db](https://github.com/firelock-ai/kin-db) - embeddable code graph database: entities, relations, vector and text search, snapshots
- [kin-model](https://github.com/firelock-ai/kin-model) - canonical types and domain models for the semantic graph
- [kin-blobs](https://github.com/firelock-ai/kin-blobs) - content-addressable blob storage
- [kin-search](https://github.com/firelock-ai/kin-search) - lexical search primitives and staged retrieval
- [kin-vector](https://github.com/firelock-ai/kin-vector) - pure-Rust HNSW vector search
- [kin-infer](https://github.com/firelock-ai/kin-infer) - transformer inference and embeddings
- [kin-lsp](https://github.com/firelock-ai/kin-lsp) - language-server enrichment for the graph

## Open core

Kin is open core.

- The core system and its libraries are open source under Apache-2.0: kin, kin-vfs, kin-editor, and the supporting crates above.
- The hosted collaboration and control plane (KinLab) and the internal benchmark runner are proprietary.
- The public benchmark specification and a standalone bundle verifier live in [kin-bench-spec](https://github.com/firelock-ai/kin-bench-spec).

## About Firelock

Firelock is the company behind Kin. When existing tools bottleneck AI-native
software work, we build the missing substrate and open-source the core.

[kinlab.ai](https://kinlab.ai) | [hello@firelock.ai](mailto:hello@firelock.ai)
