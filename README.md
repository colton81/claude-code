# Claude Code Source Exposed

<p align="center">
	Large TypeScript CLI + agent runtime with command routing, tool orchestration,
	interactive terminal UI, and model-driven query execution.
</p>

---

## Architecture At A Glance

| Layer | Purpose | Start Here |
|---|---|---|
| Entrypoint | Process startup, feature flags, CLI wiring | `src/main.tsx` |
| Bootstrap | Session initialization, environment setup | `src/setup.ts`, `src/bootstrap/` |
| Commands | User-facing slash/CLI commands | `src/commands.ts`, `src/commands/` |
| Tools | Agent-callable capabilities | `src/tools.ts`, `src/tools/` |
| Query Engine | Model loop, tool execution, token flow | `src/query.ts`, `src/query/` |
| Services | Shared domain integrations and core logic | `src/services/` |

---

## Important Folders

### Runtime Core

- `src/commands/`: Slash and CLI command implementations (review, tasks, config, bridge, auth, maintenance).
- `src/tools/`: Agent tool implementations (file edits, shell, web fetch/search, task controls, MCP resources, planning/worktree).
- `src/query/`: Query loop building blocks for transitions, stop hooks, context/token budget handling.
- `src/services/`: Shared application logic and integrations (API clients, analytics, compacting, MCP, plugins, memory, voice).

### Platform And Session Infrastructure

- `src/bootstrap/`: Early process/session state and initialization plumbing.
- `src/bridge/`: Remote/bridge mode internals (transport, permissions, messaging, bridge UI/status).
- `src/state/`: Session/app state stores and update orchestration.
- `src/server/` and `src/remote/`: Remote session and direct-connect server-side flow.

### UI, Extensibility, And Shared Building Blocks

- `src/components/`, `src/screens/`, `src/ink/`: Terminal UI components, screen orchestration, and rendering primitives.
- `src/plugins/` and `src/skills/`: Built-in plugin and skill registration/loading.
- `src/types/` and `src/schemas/`: Shared contracts and schema definitions.
- `src/utils/`: Cross-cutting helpers (auth, config, git, permissions, logging, model/provider helpers, filesystem/process utilities).

---

## Suggested Reading Path

1. `src/main.tsx` to see full startup and top-level wiring.
2. `src/setup.ts` to understand environment/session initialization.
3. `src/commands.ts` for command registry and command composition.
4. `src/tools.ts` for the complete tool surface exposed to the runtime.
5. `src/query.ts` and `src/query/` for the core request/tool execution loop.
