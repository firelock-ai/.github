# Firelock

**AI-first engineering. We build high-performance infrastructure and ship open-source tools for AI-native teams.**

---

### Kin — Semantic Version Control

> Git stores text history. **Kin understands code.**

[**Kin**](https://github.com/firelock-ai/kin) is a local-first semantic version control system built in Rust. It replaces file-based version control with a graph of semantic entities and relationships, then serves precise context to AI agents and developers under token budgets.

```
$ kin trace AuthService --compact
→ AuthService (class) @ src/auth/service.ts
  ├─ depends: TokenValidator, UserRepository, SessionStore
  ├─ callers: LoginHandler, OAuthCallback, APIGateway
  └─ contracts: POST /auth/login, POST /auth/refresh

$ kin context AuthService --budget 4k
✓ Context pack: 3,847 tokens (12 entities, 4 signatures)
```

**Why Kin?**
- Semantic graph replaces file diffs — code stored as entities and relationships
- Token-budgeted context packs for AI assistants via Model Context Protocol (MCP)
- Identity tracking survives renames, moves, and refactoring
- Semantic review and impact analysis — not line-level diffs
- Git interop — import/export, but Git is not required

**Status:** Public Alpha | **License:** Apache 2.0 | **Language:** Rust

[View Repository](https://github.com/firelock-ai/kin) | [firelock.ai](https://firelock.ai)

---

### About Firelock

Firelock is a professional consulting firm specializing in AI, software engineering, IT infrastructure, and marketing. We deliver high-performance solutions for the modern enterprise — from AI agent architectures to mission-critical infrastructure.

When existing tools bottleneck our velocity, we build our own and open-source them.

[firelock.ai](https://firelock.ai) | [hello@firelock.ai](mailto:hello@firelock.ai)
