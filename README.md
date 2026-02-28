<p align="center">
  <img src="assets/logo.png" alt="0shot logo" width="120" />
</p>

<h1 align="center">0shot</h1>

<p align="center">
  <strong>One-shot any backend. The open-source Lovable & Bolt killer.</strong><br/>
  A multi-agent AI framework that decomposes, isolates, and ships entire backends — with minimal hallucination.
</p>

<p align="center">
  <a href="#quickstart">Quickstart</a> •
  <a href="#how-it-works">How It Works</a> •
  <a href="#contributing">Contributing</a> •
  <a href="#community">Community</a> •
  <a href="docs/ARCHITECTURE.md">Architecture</a>
</p>

<p align="center">
  <a href="https://github.com/nicolas-palermo/0shot/stargazers"><img src="https://img.shields.io/github/stars/your-org/0shot" alt="Stars" /></a>
  <a href="https://github.com/nicolas-palermo/0shot/blob/main/LICENSE"><img src="https://img.shields.io/github/license/your-org/0shot" alt="License" /></a>
  <a href="https://discord.gg/WjUHAKvY6B"><img src="https://img.shields.io/discord/1477416404448968897?label=Discord" alt="Discord" /></a>
  <a href="https://github.com/nicolas-palermo/0shot/issues"><img src="https://img.shields.io/github/issues/your-org/0shot" alt="Issues" /></a>
</p>

---

## The Problem

Tools like Lovable, Bolt, and v0 dump your entire project into a single AI context. The result? Massive token windows, cascading hallucinations, and code that breaks the moment it gets complex.

**You shouldn't need to babysit an AI through 47 iterations to get a working backend.**

## The 0shot Approach

0shot takes a fundamentally different approach: **divide, isolate, conquer**.

Instead of one overwhelmed AI context, 0shot breaks your request into a DAG of small, isolated tasks — each handled by a dedicated agent in its own sandbox. Every function is tested, reviewed, and validated *before* integration. The result is a backend that works on the first try.

```
You describe what you want
    → AI plans + you approve
        → N tasks spawn N isolated agents (in parallel)
            → each writes, tests, and reviews code independently
                → integration tests validate the full system
                    → you get a working backend + live dashboard
```

## How It Works

**1. Plan & Agree** — The UI Agent takes your request, produces a plan, I/O schemas, and an execution graph (DAG). You review and approve before any code is written.

**2. Isolate & Implement** — Each node in the DAG spawns a Code Implementer agent in its own sandbox. Agents only see their task + the I/O schema contracts — no bloated context.

**3. Test & Review** — Every isolated function is automatically tested against its schema, linted, and reviewed by a Code Reviewer agent. Failures loop back to the implementer until passing.

**4. Integrate & Validate** — An E2E Alignment Tester assembles all functions, runs integration tests against the original plan, and re-enters the fix loop if anything breaks.

**5. Ship & Observe** — The final system is wrapped in a stateful DAG executor with a real-time dashboard so you can see exactly what's running.

> 📖 For the full technical deep-dive, see [`docs/ARCHITECTURE.md`](docs/ARCHITECTURE.md).

## Quickstart

> ⚠️ **0shot is in early development.** We're building in public and moving fast. Expect rough edges.

```bash
# Clone the repo
git clone https://github.com/your-org/0shot.git
cd 0shot

# Install dependencies
pnpm install  # or npm install

# Start the development server
pnpm dev
```

<!-- TODO: update once CLI and setup are finalized -->

## Project Status

We're in the **early architecture & MVP phase**. Here's where things stand:

| Component | Status |
|---|---|
| UI Agent (Planner) | 🟡 In progress |
| I/O Schema System | 🟡 In progress |
| Execution Graph / DAG | 🔴 Not started |
| Code Implementer Agent | 🔴 Not started |
| Sandbox Environments | 🔴 Not started |
| Code Tester / Reviewer | 🔴 Not started |
| E2E Alignment Tester | 🔴 Not started |
| Graph Executor + Observer | 🔴 Not started |
| Dashboard UI | 🔴 Not started |

Want to own a component? Check [**Contributing**](#contributing) below.

## Contributing

We're building 0shot as a community-first project. Whether you're an AI engineer, a backend dev, or a founder who wants to dogfood this — there's a place for you.

### Ways to Contribute

- **🐛 Report bugs** — Open an [issue](https://github.com/your-org/0shot/issues) with reproduction steps.
- **💡 Propose features** — Start a [discussion](https://github.com/your-org/0shot/discussions) or open an RFC issue.
- **🔧 Pick up an issue** — Look for [`good first issue`](https://github.com/your-org/0shot/labels/good%20first%20issue) or [`help wanted`](https://github.com/your-org/0shot/labels/help%20wanted) labels.
- **📖 Improve docs** — Docs are never done. PRs welcome.
- **🧪 Write tests** — More coverage = more confidence.

### Getting Started

```bash
# Fork and clone
git clone https://github.com/YOUR_USERNAME/0shot.git
cd 0shot

# Create a branch
git checkout -b feat/my-feature

# Make your changes, then submit a PR
```

Please read [`CONTRIBUTING.md`](CONTRIBUTING.md) for coding standards, commit conventions, and PR guidelines.

### Development Principles

- **Small PRs over big PRs.** Keep it reviewable.
- **Tests are not optional.** If it's not tested, it doesn't ship.
- **Schema-first thinking.** Define the contract before the implementation.
- **Document as you go.** Future you (and the community) will thank you.

## Community

This project is built by and for the community. Come hang out:

- 💬 [**Discord**](https://discord.gg/YOUR_INVITE) — Real-time chat, questions, and collaboration
- 🗣️ [**GitHub Discussions**](https://github.com/your-org/0shot/discussions) — Longer-form ideas, RFCs, and show-and-tell
- 🐦 [**Twitter/X**](https://twitter.com/0shot_ai) — Updates and announcements

### Community Guidelines

We're building something ambitious and we want everyone to feel welcome doing it. Be kind, be constructive, and assume good intent. See our [Code of Conduct](CODE_OF_CONDUCT.md).

## Why Open Source?

The AI coding space is dominated by closed-source tools that charge $20/month to hallucinate at you. We believe the architecture for reliable AI-generated code should be open, auditable, and community-driven. If you're a founder who ships fast, you deserve tools that ship fast too — without vendor lock-in.

## Roadmap

- [x] Architecture design & documentation
- [ ] MVP: UI Agent + Plan generation
- [ ] I/O Schema contract system
- [ ] Execution DAG engine
- [ ] Sandboxed Code Implementer agents
- [ ] Code Tester + Reviewer loop
- [ ] E2E Alignment Tester
- [ ] Graph Executor + Dashboard
- [ ] Plugin system for custom agents
- [ ] Self-hosted deployment guide

## License

[Apache 2.0](LICENSE) — Use it, fork it, ship with it.

---

<p align="center">
  <strong>Built for founders who ship fast.</strong><br/>
  <sub>If 0shot saves you time, give us a ⭐ — it helps more than you think.</sub>
</p>
