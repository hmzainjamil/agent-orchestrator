# Agent Orchestrator

Agent Orchestrator (AO) launches and supervises parallel AI coding-agent sessions for configured repositories. It combines a CLI and dashboard with pluggable agent, runtime, workspace, issue-tracker, source-control, notification, and terminal integrations.

Sessions can create working directories or Git worktrees and run local coding tools. Depending on your configuration, AO can also interact with issue trackers, Git hosting, CI, reviews, and notifications. Review the configured tools and credentials before starting sessions: agents may modify files, create branches or pull requests, and send data to external services.

## Repository and provenance

This checkout is `hmzainjamil/agent-orchestrator`. Root package metadata identifies a private pnpm workspace. Workspace package manifests and the MIT license retain ComposioHQ repository URLs and copyright attribution. GitHub does not mark this repository as a fork, so this README does not assert a formal fork relationship.

The repository contains implementation code, setup and architecture documents, plugin packages, examples, and tests. Claims here describe files and configuration in the current source tree; they do not certify production use, security assurance, benchmark results, or passing checks.

## How it is structured

AO uses plugin slots for the parts that vary by environment:

| Slot | Purpose | Examples in this workspace |
|---|---|---|
| Agent | Coding tool that performs work | Claude Code, Codex, Aider, Cursor, OpenCode |
| Runtime | Where an agent process runs | tmux, process |
| Workspace | How repository work is isolated | Git worktree, clone |
| Tracker | Where tasks come from | GitHub, Linear, GitLab |
| SCM | Pull requests, CI, reviews | GitHub, GitLab |
| Notifier | Session and workflow notifications | Desktop, Discord, Slack, webhook, OpenClaw |
| Terminal | Human access to a session | Web, iTerm2 |
| Lifecycle | Session state and reactions | Core services |

The root [AGENTS.md](./AGENTS.md) and [CLAUDE.md](./CLAUDE.md) contain repository contributor context. See [ARCHITECTURE.md](./ARCHITECTURE.md) for design details and caveats.

## Get started

Requirements: Node.js 20+, pnpm 9.15.4, and Git. The default tmux runtime also requires tmux. Other integrations may need their own CLIs and credentials.

For a local source checkout:

```sh
git clone https://github.com/hmzainjamil/agent-orchestrator.git
cd agent-orchestrator
pnpm install
pnpm build
```

The setup guide documents the `ao` CLI installation and first-run flow:

```sh
npm install -g @aoagents/ao
ao --help
ao start
```

Check the package registry and [SETUP.md](./SETUP.md) for current installation details before using a published package. For dashboard development from this checkout, run `pnpm dev`; root package scripts define the available commands.

## Configuration and data

Start from [agent-orchestrator.yaml.example](./agent-orchestrator.yaml.example) or the examples in [examples/](./examples/). Keep real tokens in environment variables or a secret manager. The local configuration file may contain repository paths and service settings; inspect it and keep credentials out of version control.

The project documentation describes runtime session metadata, archives, and worktrees under `~/.agent-orchestrator/`. These files and workspaces can contain issue text, agent output, source code, and other sensitive project data. Set access and retention practices for the machine where AO runs.

## Safety and limits

- An agent session is an action-capable process. It can change files and use whatever tools, filesystem access, and credentials its runtime receives.
- Worktree isolation helps separate repository changes. It is not a security sandbox for the agent process.
- Tracker, SCM, notifier, and adapter plugins can make network requests and transmit configured data.
- Automatic reactions and merge settings can trigger follow-on actions. Review them before enabling.
- Runtime and plugin packages have different isolation properties. Inspect their docs and configuration before use.

Read [SECURITY.md](./SECURITY.md) and [TROUBLESHOOTING.md](./TROUBLESHOOTING.md) before configuring shared or automated use. Do not treat a successful build or test as a security review.

## Repository map

| Path | Purpose |
|---|---|
| `packages/core/` | Types, configuration, session and lifecycle services, plugin registry |
| `packages/cli/` | `ao` command-line package |
| `packages/web/` | Next.js dashboard |
| `packages/ao/` | Global CLI wrapper |
| `packages/plugins/` | Agent, runtime, workspace, tracker, SCM, notifier, and terminal integrations |
| `packages/integration-tests/` | Integration test package |
| `examples/` | Example AO configuration files |
| `docs/design/` | Design research artifacts |
| `ARCHITECTURE.md` | Architecture notes |
| `SETUP.md` | Install and setup guide |
| `TROUBLESHOOTING.md` | Troubleshooting notes |
| `CONTRIBUTING.md` | Contribution guidance |
| `SECURITY.md` | Security policy |

See [docs/README.md](./docs/README.md) for the documentation map and design-artifact status.

## Build and checks

Root scripts provide these commands:

```sh
pnpm build
pnpm typecheck
pnpm test
pnpm --filter @aoagents/ao-web test
pnpm test:integration
pnpm lint
```

The root `pnpm test` excludes the web package; its tests have a separate command. These commands were not run for this README update.

## License

The repository includes the [MIT License](./LICENSE), with copyright attribution to Composio, Inc. Preserve the license and attribution when redistributing covered code.
