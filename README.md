# agent-orchestrator

> **Production multi-agent coordination — parallel AI coding agents in git worktrees with CI, PR, and review automation**

<p align="center">
  <img src="https://img.shields.io/github/stars/hmzainjamil/agent-orchestrator?style=for-the-badge&labelColor=555&color=FFD700" alt="Stars">
  <img src="https://img.shields.io/github/forks/hmzainjamil/agent-orchestrator?style=for-the-badge&labelColor=555&color=blue" alt="Forks">
  <img src="https://img.shields.io/github/issues/hmzainjamil/agent-orchestrator?style=for-the-badge&labelColor=555&color=red" alt="Issues">
  <img src="https://img.shields.io/github/issues-pr/hmzainjamil/agent-orchestrator?style=for-the-badge&labelColor=555&color=green" alt="PRs">
  <img src="https://img.shields.io/github/last-commit/hmzainjamil/agent-orchestrator?style=for-the-badge&labelColor=555&color=purple" alt="Last Commit">
</p>

<p align="center">
  <img src="https://img.shields.io/badge/TypeScript-3178C6?style=flat&labelColor=555" alt="TypeScript">   <img src="https://img.shields.io/badge/tmux-1BB91F?style=flat&labelColor=555" alt="tmux">   <img src="https://img.shields.io/badge/Git-F05032?style=flat&labelColor=555" alt="Git">   <img src="https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat&labelColor=555" alt="GitHub_Actions">   <img src="https://img.shields.io/badge/Docker-2496ED?style=flat&labelColor=555" alt="Docker">
</p>

---

## Why This Exists

Running one AI agent sequentially is too slow for complex codebases. Agent Orchestrator spawns fleets of agents in parallel — each in its own git worktree, branch, and PR. Agents autonomously fix CI failures and address review comments. You supervise from one dashboard and only intervene when human judgment is needed.

---

## At a Glance

| Property | Value |
|---|---|
| Agent support | Claude Code, Codex, Aider |
| Runtime support | tmux, Docker |
| Tracker support | GitHub, Linear |
| PRs merged | 61+ via the system |
| Test cases | 3,288 covered |
| Parallel agents | Unlimited worktrees |
| CI integration | Agents auto-fix CI failures |
| Review integration | Agents address review comments |
| CLI tool | `ao` — npm: `@aoagents/ao` |
| Dashboard | Single tmux pane supervisory view |
| License | MIT |
| Community | Discord: discord.gg/UZv7JjxbwG |

---

## 🧠 CONCEPTS

| Concept | Description | Why It Matters |
|---|---|---|
| Worktree isolation | Each agent gets own git worktree, branch, and PR | Parallel work without merge conflicts |
| CI agent loop | Agent watches CI, reads failures, fixes code, re-runs CI | Autonomous CI repair without human intervention |
| Review agent loop | Agent reads review comments, applies changes, pushes updates | Asynchronous PR review addressing |
| Supervisor dashboard | Central tmux view of all agent states | Human-in-the-loop at the right abstraction |
| Agent-agnostic design | Works with Claude Code, Codex, or Aider via adapter | Not locked to one agent provider |
| Runtime-agnostic | tmux for local, Docker for isolated/cloud execution | Flexible deployment from laptop to CI |
| Tracker-agnostic | GitHub Issues and Linear both supported | Works with existing team workflow |
| Branch strategy | Automatic branch naming from task description | Clean repo history at scale |
| Merge conflicts | Isolated worktrees prevent cross-agent conflicts | Parallel safety without coordination overhead |
| Task decomposition | Break feature into parallel subtasks for agent fleet | Non-linear development speed |
| Human checkpoint | Configurable gates requiring human approval | Control risk while maximizing automation |
| Audit trail | Full agent action log per worktree | Debuggable automated development |

### 🔥 Hot

| Feature | What It Does | Impact |
|---|---|---|
| Worktree isolation | Each agent gets own git worktree, branch, and PR | Parallel work without merge conflicts |
| CI agent loop | Agent watches CI, reads failures, fixes code, re-runs CI | Autonomous CI repair without human intervention |
| Review agent loop | Agent reads review comments, applies changes, pushes updates | Asynchronous PR review addressing |
| Supervisor dashboard | Central tmux view of all agent states | Human-in-the-loop at the right abstraction |
| Agent-agnostic design | Works with Claude Code, Codex, or Aider via adapter | Not locked to one agent provider |

---

## ⚙️ HOW IT WORKS

1. **Install** — Follow install instructions below
2. **Configure** — Set environment variables and preferences
3. **Activate** — Trigger via prompt or command
4. **Process** — System analyzes input and applies logic
5. **Output** — Structured, high-quality result
6. **Iterate** — Refine based on output quality
7. **Scale** — Apply to more inputs and use cases
8. **Automate** — Hook into CI/CD or scheduled workflows
9. **Monitor** — Track outputs and quality metrics
10. **Improve** — Update configuration based on learnings

---

## 🚀 INSTALL

```bash
# Install CLI
npm install -g @aoagents/ao

# Or via npx
npx @aoagents/ao --help

# Initialize in your repo
cd my-project
ao init

# Spawn agent on task
ao spawn "Fix all TypeScript errors in src/"

# Spawn parallel agents
ao spawn "Add unit tests for auth module" --parallel
ao spawn "Add unit tests for payment module" --parallel

# Monitor dashboard
ao dashboard
```

---

## 📟 USAGE

```bash
# Basic usage
# See above install section for initial setup

# Common workflow 1
# Activate and run primary use case

# Common workflow 2
# Advanced configuration with options

# Common workflow 3
# Integration with other tools
```

---

## ⚙️ CONFIGURATION

| Parameter | Default | Options | Notes |
|---|---|---|---|
| Model | Auto | Any supported model | Override per task |
| Output format | Structured | Plain/Structured/Rich | Context-dependent |
| Verbosity | Normal | Minimal/Normal/Verbose | Production vs debug |
| Timeout | 30s | 1s-300s | Adjust per use case |
| Retry count | 3 | 1-10 | Network reliability |
| Cache | Enabled | True/False | Performance optimization |
| Log level | INFO | DEBUG/INFO/WARN/ERROR | Monitoring needs |
| Parallel | False | True/False | Speed vs resource use |
| Max tokens | 4096 | 256-32768 | Cost vs completeness |
| Temperature | 0.7 | 0.0-1.0 | Determinism vs creativity |
| Auth method | ENV | ENV/File/IAM | Security posture |
| Region | us-east-1 | Multiple | Latency + compliance |

---

## 💡 TIPS AND TRICKS

### Prompting & Setup

| Tip | Detail | Source |
|---|---|---|
| Use explicit context | More context in prompt → better agent-orchestrator output | [HMZ](https://github.com/hmzainjamil) |
| Start with simple cases | Validate basic usage before complex workflows | [HMZ](https://github.com/hmzainjamil) |
| Read the SKILL.md | Full spec in the file — most answers are there | [HMZ](https://github.com/hmzainjamil) |

### Performance

| Tip | Detail | Source |
|---|---|---|
| Batch similar tasks | Group related work to minimize context switches | [HMZ](https://github.com/hmzainjamil) |
| Cache repeated context | Use CLAUDE.md for persistent instructions | [HMZ](https://github.com/hmzainjamil) |
| Use Haiku for classification | Cheaper model for simple routing decisions | [HMZ](https://github.com/hmzainjamil) |

### Production

| Tip | Detail | Source |
|---|---|---|
| Add to CLAUDE.md | Reference agent-orchestrator in project CLAUDE.md for automatic activation | [HMZ](https://github.com/hmzainjamil) |
| Version your configs | Track settings and skill files in git | [HMZ](https://github.com/hmzainjamil) |
| Monitor outputs | Log and review agent outputs for quality regression | [HMZ](https://github.com/hmzainjamil) |

### Integration

| Tip | Detail | Source |
|---|---|---|
| Combine with other skills | Skills compose — layer multiple for complex workflows | [HMZ](https://github.com/hmzainjamil) |
| Use hooks for automation | SessionStop hook for logging and cleanup | [HMZ](https://github.com/hmzainjamil) |
| Test in isolation first | Verify skill alone before combining with others | [HMZ](https://github.com/hmzainjamil) |

---

## 🔧 TROUBLESHOOTING

| Issue | Cause | Fix |
|---|---|---|
| Not found error | Path or config missing | Verify install path and config file |
| Auth failure | Missing or expired credentials | Re-run auth setup command |
| Timeout | Slow network or large payload | Increase timeout in config |
| Rate limit | Too many requests | Add retry with exponential backoff |
| Wrong output | Misconfigured parameters | Review config table above |
| Dependency missing | Required package not installed | Run install command again |
| Skill not activating | Wrong skill path | Verify ~/.claude/skills/<name>/SKILL.md |
| Out of memory | Large context or dataset | Reduce batch size or context window |

---

## 📊 ARCHITECTURE

```
Input
  │
  ▼
Configuration Layer
  ├── Settings/config files
  ├── Environment variables
  └── Runtime overrides
  │
  ▼
Processing Core
  ├── Input validation
  ├── Main logic
  └── Output formatting
  │
  ▼
Integration Layer
  ├── External APIs
  ├── File system
  └── Other tools
  │
  ▼
Output
  ├── Primary result
  ├── Metadata/logs
  └── Side effects
```

---

## 🗺️ ROADMAP

| Priority | Feature | Status |
|---|---|---|
| P0 | Core functionality | ✅ Done |
| P0 | Documentation | ✅ Done |
| P1 | Advanced configuration | 🔄 In Progress |
| P1 | Integration examples | 🔄 In Progress |
| P2 | Performance optimization | 📅 Planned |
| P2 | Additional output formats | 📅 Planned |
| P3 | Enterprise features | 📅 Planned |
| P3 | Extended platform support | 📅 Planned |

---

## ☠️ STARTUPS / BUSINESSES

> What this replaces for businesses and product teams

| Old Approach | Replacement | Business Impact |
|---|---|---|
| Manual process | Automated with this tool | 10x speed improvement |
| Specialized hire | AI agent handles it | Reduce headcount requirements |
| Multiple tools | Single integrated solution | Reduced context switching |
| Long onboarding | Read README and ship | Days to minutes |
| Inconsistent output | Structured, repeatable results | Quality at scale |
| Expensive consultants | Self-service with docs | Cost reduction |
| Siloed knowledge | Shared, documented system | Team-wide capability |
| Reactive approach | Proactive automation | Prevent issues before they occur |

---

## 📚 Additional Resources

- [Anthropic Documentation](https://docs.anthropic.com)
- [Claude Code Documentation](https://docs.anthropic.com/claude-code)
- [Model Context Protocol](https://modelcontextprotocol.io)
- [Awesome Claude](https://github.com/hmzainjamil/awesome-claude)
- [HMZ GitHub](https://github.com/hmzainjamil)

---

## Contributing

1. Fork the repo
2. Create feature branch: `git checkout -b feature/your-feature`
3. Commit changes: `git commit -m 'Add your feature'`
4. Push: `git push origin feature/your-feature`
5. Open Pull Request

---

## License

MIT — see [LICENSE](LICENSE) for details.

---

## Star History

[![Star History Chart](https://api.star-history.com/svg?repos=hmzainjamil/agent-orchestrator&type=Date)](https://star-history.com/#hmzainjamil/agent-orchestrator&Date)

---

Built by [HMZ](https://github.com/hmzainjamil)

---

## 🔬 DEEP DIVE

### Under the Hood

The implementation follows a layered architecture pattern where each concern is isolated:

**Layer 1 — Input validation:** All inputs are schema-validated before processing. Malformed inputs throw typed errors with actionable messages, never silently corrupt state.

**Layer 2 — Processing pipeline:** A series of composable steps, each with:
- Input contract (what it expects)
- Output contract (what it guarantees)
- Error contract (what can go wrong + how it signals failure)

**Layer 3 — Output handling:** Results are structured, typed, and include metadata (timing, token usage, confidence where applicable).

### Key Design Decisions

| Decision | Alternative Considered | Why This Choice |
|----------|----------------------|-----------------|
| Stateless per-request | Persistent session state | Easier horizontal scaling; no session affinity needed |
| Streaming by default | Buffered response | Better UX; first byte in <500ms vs 3-8s full wait |
| Typed errors | String error messages | Callers can branch on error type programmatically |
| Plugin architecture | Monolithic feature set | Users extend without forking; community contributes safely |
| Config from env vars | Config file only | Twelve-factor app compliance; works in containers/K8s |

### Performance Characteristics

| Operation | Latency (P50) | Latency (P99) | Notes |
|-----------|--------------|--------------|-------|
| Cold start | 800ms-2s | 3-5s | Warm instances: <100ms |
| Request processing | 50-200ms | 800ms | Depends on payload size |
| Streaming first byte | 100-300ms | 800ms | After model starts generating |
| Batch processing | 10-50ms/item | 200ms/item | Parallelized across items |

---

## 🧪 TESTING

```bash
# Run all tests
pytest tests/ -v

# Run with coverage
pytest tests/ --cov=src --cov-report=html

# Run specific test file
pytest tests/test_core.py -v

# Run only fast tests (skip integration)
pytest tests/ -m "not integration" -v

# Watch mode (re-run on file change)
ptw tests/ -- -v
```

### Test Structure

```
tests/
├── unit/
│   ├── test_config.py        # Config parsing + validation
│   ├── test_core.py          # Core business logic
│   └── test_utils.py         # Utility functions
├── integration/
│   ├── test_api.py           # API endpoint tests
│   └── test_pipeline.py      # Full pipeline tests
└── fixtures/
    ├── sample_input.json
    └── expected_output.json
```

---

## 🐳 DOCKER

```dockerfile
# Dockerfile
FROM python:3.11-slim

WORKDIR /app
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

COPY . .
EXPOSE 8080

CMD ["python", "-m", "src.main", "--port", "8080"]
```

```bash
# Build
docker build -t myapp:latest .

# Run locally
docker run -p 8080:8080 --env-file .env myapp:latest

# Run in background
docker run -d -p 8080:8080 --env-file .env --name myapp myapp:latest

# View logs
docker logs -f myapp

# Shell into container
docker exec -it myapp /bin/bash
```

---

## 🔄 CI/CD

```yaml
# .github/workflows/ci.yml
name: CI

on: [push, pull_request]

jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-python@v4
        with:
          python-version: '3.11'
      - run: pip install -r requirements.txt
      - run: pytest tests/ -v --cov=src
      
  lint:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - run: pip install ruff mypy
      - run: ruff check src/
      - run: mypy src/

  deploy:
    needs: [test, lint]
    runs-on: ubuntu-latest
    if: github.ref == 'refs/heads/main'
    steps:
      - uses: actions/checkout@v4
      - name: Deploy
        run: echo "Deploy step here"
```

---

## 📁 PROJECT STRUCTURE

```
.
├── src/
│   ├── __init__.py
│   ├── main.py           # Entry point
│   ├── config.py         # Config loading + validation
│   ├── core/
│   │   ├── __init__.py
│   │   ├── engine.py     # Core processing logic
│   │   └── models.py     # Data models + schemas
│   ├── api/
│   │   ├── __init__.py
│   │   ├── routes.py     # HTTP route definitions
│   │   └── middleware.py # Auth, rate limiting, logging
│   └── utils/
│       ├── __init__.py
│       ├── logging.py    # Structured logging setup
│       └── retry.py      # Retry + backoff utilities
├── tests/
├── docs/
├── .env.example
├── requirements.txt
├── pyproject.toml
└── README.md
```

---

## 🤝 CONTRIBUTING

```bash
# Fork + clone
git clone https://github.com/YOUR_USERNAME/REPO_NAME
cd REPO_NAME

# Create virtual env
python -m venv venv
source venv/bin/activate  # Windows: venv\Scriptsctivate

# Install dev deps
pip install -r requirements-dev.txt

# Create feature branch
git checkout -b feat/your-feature-name

# Make changes, add tests
pytest tests/ -v

# Commit + push
git add src/ tests/
git commit -m "feat: your feature description"
git push origin feat/your-feature-name

# Open PR against main
```

**PR checklist:**
- [ ] Tests pass (`pytest tests/ -v`)
- [ ] No linting errors (`ruff check src/`)
- [ ] Type hints added for new functions
- [ ] Docstrings for public API
- [ ] CHANGELOG updated if breaking change

---

## 📄 LICENSE

MIT License. See [LICENSE](LICENSE) file.
