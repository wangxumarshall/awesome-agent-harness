# Awesome Agent Harness

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![Last Updated](https://img.shields.io/badge/updated-Mar%202026-green.svg)]()
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)

> A curated GitHub map of projects for building, operating, and governing agent harnesses, while preserving the original Claude Skills catalog from this repository.

An `agent harness` is the control plane around an agent:

- prompt and context scaffolding
- planning, state, checkpoints, and recovery
- tool and protocol integration
- isolated execution environments
- verification, reviewability, and guardrails

This README now has **two layers**:

1. an `Agent Harness` ecosystem map and GitHub project index
2. the original `Claude Skills` catalog, preserved in full

## Scope

This list focuses on **high-signal, open-source GitHub projects** that are directly useful when building an agent harness.

It does **not** attempt a mathematically exhaustive list of every repo in the ecosystem. That is no longer practical, especially for:

- MCP servers
- individual skill packs
- one-off app wrappers around existing agents

For long-tail discovery, this README points to registries and official indexes.

## Search Method

GitHub-wide search terms used in this sweep included:

```text
agent harness
harness engineering
coding agent
agent runtime
stateful agent
model context protocol
mcp server
agent skills
browser agent
agent eval
agent guardrails
secure agent sandbox
```

Notes:

- This sweep was updated on **March 22, 2026**.
- Star counts in the `~100-star` section below are **GitHub API snapshots from March 22, 2026** and will change over time.
- For this README, `~100 stars` means **roughly 80-160 stars**, because exact 100-star filtering is too unstable to be useful in practice.
- As of **March 22, 2026**, `OpenDevin/OpenDevin` has effectively moved to [All-Hands-AI/OpenHands](https://github.com/All-Hands-AI/OpenHands).
- As of **March 22, 2026**, `openclaw/openclaw` resolves to [clawdbot/clawdbot](https://github.com/clawdbot/clawdbot).

## If You Only Read Five Repos

- [openai/codex](https://github.com/openai/codex) - terminal-native coding agent shell
- [langchain-ai/deepagents](https://github.com/langchain-ai/deepagents) - explicit open-source harness with planning, filesystem, subagents, MCP, and HITL
- [modelcontextprotocol/modelcontextprotocol](https://github.com/modelcontextprotocol/modelcontextprotocol) - the protocol layer that now defines most tool integration work
- [github/github-mcp-server](https://github.com/github/github-mcp-server) - the most important MCP server for coding workflows
- [promptfoo/promptfoo](https://github.com/promptfoo/promptfoo) - simple, practical evals and red-teaming for agent outputs

## Ecosystem Map

### Harness-First Runtimes and Coding Agents

| Project | Why it matters for agent harnesses |
| --- | --- |
| [openai/codex](https://github.com/openai/codex) | Lightweight coding agent for the terminal; a strong reference for CLI-native harness design and repo-driven workflows. |
| [langchain-ai/deepagents](https://github.com/langchain-ai/deepagents) | One of the clearest open-source `agent harness` repos: planning, filesystem, shell, subagents, summarization, MCP, and HITL. |
| [anomalyco/opencode](https://github.com/anomalyco/opencode) | Open-source coding agent with built-in `build` and `plan` modes, provider-agnostic design, and strong TUI ergonomics. |
| [All-Hands-AI/OpenHands](https://github.com/All-Hands-AI/OpenHands) | End-to-end software engineering agent platform; useful as a larger harness/control-plane reference. |
| [Aider-AI/aider](https://github.com/Aider-AI/aider) | Terminal pair-programming agent; a mature reference for repo-aware edit/apply/test loops. |
| [continuedev/continue](https://github.com/continuedev/continue) | Open-source CLI and IDE agent system with TUI and headless modes for background workflows. |
| [cline/cline](https://github.com/cline/cline) | IDE-native autonomous coding agent with explicit human approval, browser use, checkpoints, and MCP extension points. |
| [block/goose](https://github.com/block/goose) | Extensible local agent that can install, execute, edit, and test with any LLM; good for MCP-heavy local harness patterns. |
| [SWE-agent/SWE-agent](https://github.com/SWE-agent/SWE-agent) | Research-heavy software engineering agent that stays useful as a harness reference for tool bundles, configs, and benchmarkable runs. |
| [SWE-agent/mini-swe-agent](https://github.com/SWE-agent/mini-swe-agent) | Minimal baseline harness showing how far a simple bash-first loop can go without a giant scaffold. |
| [clawdbot/clawdbot](https://github.com/clawdbot/clawdbot) | OpenClaw's current repo; useful if you care about always-on personal agent control planes, skills, channels, and device actions. |

### Frameworks, Orchestration, and Agent Protocols

| Project | Why it matters for agent harnesses |
| --- | --- |
| [langchain-ai/langgraph](https://github.com/langchain-ai/langgraph) | Low-level orchestration framework for long-running, stateful, controllable agents. |
| [openai/openai-agents-python](https://github.com/openai/openai-agents-python) | Lightweight multi-agent workflow SDK with handoffs, sessions, tracing, and guardrails. |
| [microsoft/autogen](https://github.com/microsoft/autogen) | Mature multi-agent framework with event-driven runtime and a large extension ecosystem. |
| [crewAIInc/crewAI](https://github.com/crewAIInc/crewAI) | Lean role-based multi-agent orchestration framework with a big ecosystem and many examples. |
| [agno-agi/agno](https://github.com/agno-agi/agno) | Full-stack agent system with runtime, control plane, memory, knowledge, MCP, A2A, and eval hooks. |
| [pydantic/pydantic-ai](https://github.com/pydantic/pydantic-ai) | Strong choice for typed, production-grade agent workflows with durable execution and approval hooks. |
| [letta-ai/letta](https://github.com/letta-ai/letta) | Stateful agent platform focused on advanced memory and persistent agent identity over time. |
| [lastmile-ai/mcp-agent](https://github.com/lastmile-ai/mcp-agent) | MCP-native framework that combines simple workflow patterns with durable execution. |
| [a2aproject/A2A](https://github.com/a2aproject/A2A) | Open Agent2Agent protocol for agent interoperability beyond tool calling. |
| [anthropics/claude-agent-sdk-python](https://github.com/anthropics/claude-agent-sdk-python) | SDK for embedding Claude Agent / Claude Code style behavior into programmable workflows. |

### Skills and Reusable Behavior Packs

| Project | Why it matters for agent harnesses |
| --- | --- |
| [anthropics/skills](https://github.com/anthropics/skills) | Official public repo for Claude skills, skill examples, templates, and the skill spec. |
| [openai/skills](https://github.com/openai/skills) | Codex-focused skills catalog; useful for understanding the cross-agent skills pattern. |
| [vercel-labs/skills](https://github.com/vercel-labs/skills) | Cross-agent skills CLI that installs skills into Codex, Claude Code, Cursor, OpenCode, OpenClaw, and more. |
| [obra/superpowers](https://github.com/obra/superpowers) | A full workflow system built from composable skills, plans, subagents, worktrees, and review loops. |
| [trailofbits/skills](https://github.com/trailofbits/skills) | Security-heavy skill marketplace for audits, CodeQL, Semgrep, diff review, and secure dev workflows. |
| [expo/skills](https://github.com/expo/skills) | Official Expo team skill pack for building, deploying, and debugging Expo apps. |

### MCP and Capability Fabric

| Project | Why it matters for agent harnesses |
| --- | --- |
| [modelcontextprotocol/modelcontextprotocol](https://github.com/modelcontextprotocol/modelcontextprotocol) | The MCP spec and docs repo; the foundation for modern tool, resource, and prompt integration. |
| [modelcontextprotocol/servers](https://github.com/modelcontextprotocol/servers) | Official reference servers plus the gateway into the wider MCP registry and ecosystem. |
| [modelcontextprotocol/typescript-sdk](https://github.com/modelcontextprotocol/typescript-sdk) | Official TypeScript SDK for writing MCP clients and servers. |
| [modelcontextprotocol/python-sdk](https://github.com/modelcontextprotocol/python-sdk) | Official Python SDK for MCP clients and servers. |
| [github/github-mcp-server](https://github.com/github/github-mcp-server) | The most important coding-focused MCP server: repos, files, issues, PRs, Actions, security, and more. |
| [microsoft/playwright-mcp](https://github.com/microsoft/playwright-mcp) | Browser automation via MCP using accessibility snapshots instead of pixel-only interaction. |
| [punkpeye/awesome-mcp-servers](https://github.com/punkpeye/awesome-mcp-servers) | Broad community index for MCP servers across every domain. |
| [CodeAlive-AI/codealive-mcp](https://github.com/CodeAlive-AI/codealive-mcp) | A strong example of an MCP-first context engine for large codebases. |

### Memory, State, and Context Systems

| Project | Why it matters for agent harnesses |
| --- | --- |
| [letta-ai/letta](https://github.com/letta-ai/letta) | Best viewed as a memory-first platform for persistent, stateful agents. |
| [mem0ai/mem0](https://github.com/mem0ai/mem0) | Universal memory layer for user, session, and agent state. |
| [getzep/graphiti](https://github.com/getzep/graphiti) | Real-time knowledge graphs for agent memory, retrieval, and historical reasoning; also includes an MCP server. |
| [langchain-ai/langgraph](https://github.com/langchain-ai/langgraph) | Important here for checkpointing, resumability, and explicit state graphs. |
| [CodeAlive-AI/codealive-mcp](https://github.com/CodeAlive-AI/codealive-mcp) | Worth revisiting here as a context-engine layer rather than just an MCP endpoint. |

### Browser, Sandbox, and Execution Substrate

| Project | Why it matters for agent harnesses |
| --- | --- |
| [browser-use/browser-use](https://github.com/browser-use/browser-use) | Makes websites accessible to agents; useful for end-to-end verification and browser action loops. |
| [e2b-dev/E2B](https://github.com/e2b-dev/E2B) | Secure isolated cloud sandboxes for running AI-generated code. |
| [SWE-agent/SWE-ReX](https://github.com/SWE-agent/SWE-ReX) | Runtime interface for sandboxed shell execution, local or remote, with strong parallelization support. |
| [microsoft/playwright-mcp](https://github.com/microsoft/playwright-mcp) | Also belongs here as the cleanest browser substrate for MCP-native agents. |
| [clawdbot/clawdbot](https://github.com/clawdbot/clawdbot) | Interesting if your harness needs channels, device actions, voice, and always-on local control. |

### Observability, Evals, and Guardrails

| Project | Why it matters for agent harnesses |
| --- | --- |
| [langfuse/langfuse](https://github.com/langfuse/langfuse) | Full LLM engineering platform for tracing, evals, prompts, datasets, and production debugging. |
| [Arize-ai/phoenix](https://github.com/Arize-ai/phoenix) | Open-source observability and evaluation platform for tracing and troubleshooting agent runs. |
| [promptfoo/promptfoo](https://github.com/promptfoo/promptfoo) | Practical eval, CI, red-teaming, and vulnerability scanning for prompts, RAG, and agents. |
| [truera/trulens](https://github.com/truera/trulens) | Evaluation and tracking framework for LLM applications and agents. |
| [invariantlabs-ai/invariant](https://github.com/invariantlabs-ai/invariant) | Rule-based guardrails layer that can sit between your app and MCP or LLM providers. |
| [invariantlabs-ai/mcp-scan](https://github.com/invariantlabs-ai/mcp-scan) | MCP-specific security scanner and proxy for inspection, logging, and runtime enforcement. |

## Emerging ~100-Star Harness Projects

These projects were extracted from GitHub searches for AI-related repos with **roughly 80-160 stars** and then filtered for clear relevance to harness layers.

### Prompt Scaffold, Planning, and Workflow Shaping

| Project | Stars | Layer | Why it matters |
| --- | ---: | --- | --- |
| [trevor-nichols/agentrules-architect](https://github.com/trevor-nichols/agentrules-architect) | 109 | Prompt scaffold / planning | Generates `AGENTS.md` / `CLAUDE.md` style rule files plus ExecPlan-oriented harness structure. |
| [Codename-Inc/spectre](https://github.com/Codename-Inc/spectre) | 116 | Workflow scaffold | Encodes `/Scope -> /Plan -> /Execute -> /Clean -> /Test -> /Evaluate` as a reusable coding workflow harness. |
| [sudocode-ai/sudocode](https://github.com/sudocode-ai/sudocode) | 248 | Repo workflow layer | Slightly above the target range, but useful as a repo-local orchestration layer that lives with the codebase itself. |

### Runtime, Orchestration, and Control Plane

| Project | Stars | Layer | Why it matters |
| --- | ---: | --- | --- |
| [SethGammon/Citadel](https://github.com/SethGammon/Citadel) | 125 | Orchestration runtime | Claude Code team harness with routing, worktrees, lifecycle hooks, circuit breakers, and campaign persistence. |
| [go-a2a/adk-go](https://github.com/go-a2a/adk-go) | 99 | Agent runtime / deployment | Go toolkit for building, evaluating, and deploying controlled agent systems. |
| [Mercor-Intelligence/archipelago](https://github.com/Mercor-Intelligence/archipelago) | 134 | Execution harness / eval | Harness for running and evaluating AI agents against RL environments. |
| [jpicklyk/task-orchestrator](https://github.com/jpicklyk/task-orchestrator) | 170 | Task orchestration | Slightly above the target range, but notable for persistent work tracking and context storage across sessions and agents. |

### Memory, State, and Long-Running Context

| Project | Stars | Layer | Why it matters |
| --- | ---: | --- | --- |
| [srikanthbellary/openstinger](https://github.com/srikanthbellary/openstinger) | 114 | Memory harness | Explicitly positions itself as a portable memory harness for agents. |
| [aayoawoyemi/Ori-Mnemos](https://github.com/aayoawoyemi/Ori-Mnemos) | 139 | Persistent memory | Local-first persistent memory system built specifically for agentic workflows. |
| [AGI-is-going-to-arrive/Memory-Palace](https://github.com/AGI-is-going-to-arrive/Memory-Palace) | 211 | Long-term memory OS | Above the target range, but highly relevant as a memory operating system concept for AI agents. |

### Capability Fabric and MCP-Adjacent Layers

| Project | Stars | Layer | Why it matters |
| --- | ---: | --- | --- |
| [Flux159/mcp-chat](https://github.com/Flux159/mcp-chat) | 134 | MCP client / testing | Useful for testing and evaluating MCP servers and agent setups from the client side. |
| [cs50victor/claude-code-teams-mcp](https://github.com/cs50victor/claude-code-teams-mcp) | 219 | MCP orchestration | Above the target range, but a good example of using MCP to expose team orchestration patterns to harnesses. |
| [amxv/mcp-manager](https://github.com/amxv/mcp-manager) | 285 | MCP management UI | Above the target range, but increasingly relevant as harnesses need GUI-level MCP fleet management. |

### Sandbox, Isolation, and Safe Execution

| Project | Stars | Layer | Why it matters |
| --- | ---: | --- | --- |
| [llm-platform-security/SecGPT](https://github.com/llm-platform-security/SecGPT) | 109 | Isolation architecture | Focuses on execution isolation for LLM-based agent systems. |
| [Cloudgeni-ai/infrastructure-agents-guide](https://github.com/Cloudgeni-ai/infrastructure-agents-guide) | 125 | Safe operations | Guide repo centered on architecture, sandboxing, credentials, change control, and observability for infra agents. |
| [PACHAKUTlQ/ClaudeCage](https://github.com/PACHAKUTlQ/ClaudeCage) | 138 | Sandboxed runtime | Portable sandbox wrapper for Claude Code style workflows. |
| [mattolson/agent-sandbox](https://github.com/mattolson/agent-sandbox) | 157 | Local sandbox | Local secure dev environment for agent collaboration. |

### Evals, Reviewability, and Safety Probing

| Project | Stars | Layer | Why it matters |
| --- | ---: | --- | --- |
| [METR/vivaria](https://github.com/METR/vivaria) | 135 | Evaluation harness | METR's evaluation and elicitation research tooling; highly relevant for serious agent evaluation. |
| [scabench-org/scabench](https://github.com/scabench-org/scabench) | 105 | Audit-agent eval | Framework for evaluating AI audit agents on recent real-world data. |
| [philschmid/ai-agent-benchmark-compendium](https://github.com/philschmid/ai-agent-benchmark-compendium) | 112 | Benchmark index | Curated benchmark map for agent evaluation across coding, tool use, reasoning, and computer interaction. |
| [arklexai/arksim](https://github.com/arklexai/arksim) | 112 | Error simulation / eval | Helps surface agent failures before they hit real users. |
| [Mengmeara/agent-safe-probe-x](https://github.com/Mengmeara/agent-safe-probe-x) | 83 | Safety evaluation | Focused framework for automated safety evaluation of intelligent agents. |

### UI, Desktop Shells, and Human-in-the-Loop Surfaces

| Project | Stars | Layer | Why it matters |
| --- | ---: | --- | --- |
| [OpenSource03/harnss](https://github.com/OpenSource03/harnss) | 147 | Desktop harness shell | Desktop UI for Claude Code, Codex, and ACP-compatible agents with terminal, browser, Git, and MCP visualization. |
| [EDEAI/OpenFlux](https://github.com/EDEAI/OpenFlux) | 173 | Desktop agent client | Slightly above the target range, but notable for long-term memory, browser automation, and tool orchestration in a local client. |

## Suggested Build Stacks

### 1. Minimal Coding Harness

- [openai/codex](https://github.com/openai/codex) or [anomalyco/opencode](https://github.com/anomalyco/opencode)
- [github/github-mcp-server](https://github.com/github/github-mcp-server)
- [microsoft/playwright-mcp](https://github.com/microsoft/playwright-mcp)
- [promptfoo/promptfoo](https://github.com/promptfoo/promptfoo)
- [langfuse/langfuse](https://github.com/langfuse/langfuse)

### 2. MCP-Native Harness

- [langchain-ai/deepagents](https://github.com/langchain-ai/deepagents) or [lastmile-ai/mcp-agent](https://github.com/lastmile-ai/mcp-agent)
- [modelcontextprotocol/modelcontextprotocol](https://github.com/modelcontextprotocol/modelcontextprotocol)
- [modelcontextprotocol/servers](https://github.com/modelcontextprotocol/servers)
- [mem0ai/mem0](https://github.com/mem0ai/mem0) or [getzep/graphiti](https://github.com/getzep/graphiti)
- [Arize-ai/phoenix](https://github.com/Arize-ai/phoenix)

### 3. Security-First Harness

- [cline/cline](https://github.com/cline/cline) or [block/goose](https://github.com/block/goose)
- [trailofbits/skills](https://github.com/trailofbits/skills)
- [invariantlabs-ai/invariant](https://github.com/invariantlabs-ai/invariant)
- [invariantlabs-ai/mcp-scan](https://github.com/invariantlabs-ai/mcp-scan)
- [promptfoo/promptfoo](https://github.com/promptfoo/promptfoo)

## Selection Principles

Projects are prioritized when they do one or more of the following:

- implement a full harness runtime
- expose a critical harness subsystem such as MCP, memory, sandboxing, or evals
- act as an official spec, SDK, or registry
- provide patterns that are widely reusable across agent stacks

Projects are deprioritized when they are:

- thin wrappers around proprietary services with little reusable harness value
- abandoned experiments with no clear ecosystem relevance
- one-off MCP servers that are better represented by a registry

## Preserved Claude Skills Catalog

The sections below are intentionally preserved from the original README so that the repository keeps its complete `Skills` catalog instead of dropping it.

## How Skills Work

Skills employ a **progressive disclosure architecture** for efficiency:

1. **Metadata loading** (~100 tokens): Claude scans available Skills to identify relevant matches
2. **Full instructions** (<5k tokens): Load when Claude determines the Skill applies
3. **Bundled resources**: Files and executable code load only as needed

This design allows multiple Skills to remain available without overwhelming Claude's context window.

## 🚀 Getting Started

### Claude.ai Web Interface

1. Go to [Settings > Capabilities](https://claude.ai/settings/capabilities)
2. Enable Skills toggle
3. Browse available skills or upload custom skills
4. **For Team/Enterprise**: Admin must enable Skills organization-wide first

### Claude Code CLI

```bash
# Install skills from marketplace
/plugin marketplace add anthropics/skills

# Or install from local directory
/plugin add /path/to/skill-directory
```

### Claude API

Skills are accessible via the `/v1/skills` API endpoint. See the [Skills API documentation](https://platform.claude.com/docs/en/api/beta/skills) for detailed integration examples.

```python
import anthropic

client = anthropic.Client(api_key="your-api-key")
# See API docs for full implementation details
```

## 🎯 Official Skills

### Document Skills

Skills for working with complex file formats:

- **[docx](https://github.com/anthropics/skills/tree/main/skills/docx)** - Create, edit, and analyze Word documents with support for tracked changes, comments, formatting preservation, and text extraction
- **[pdf](https://github.com/anthropics/skills/tree/main/skills/pdf)** - Comprehensive PDF manipulation toolkit for extracting text and tables, creating new PDFs, merging/splitting documents, and handling forms
- **[pptx](https://github.com/anthropics/skills/tree/main/skills/pptx)** - Create, edit, and analyze PowerPoint presentations with support for layouts, templates, charts, and automated slide generation
- **[xlsx](https://github.com/anthropics/skills/tree/main/skills/xlsx)** - Create, edit, and analyze Excel spreadsheets with support for formulas, formatting, data analysis, and visualization

### Design & Creative

- **[algorithmic-art](https://github.com/anthropics/skills/tree/main/skills/algorithmic-art)** - Create generative art using p5.js with seeded randomness, flow fields, and particle systems
- **[canvas-design](https://github.com/anthropics/skills/tree/main/skills/canvas-design)** - Design beautiful visual art in .png and .pdf formats using design philosophies
- **[slack-gif-creator](https://github.com/anthropics/skills/tree/main/skills/slack-gif-creator)** - Create animated GIFs optimized for Slack's size constraints

### Development

- **[frontend-design](https://github.com/anthropics/skills/blob/main/skills/frontend-design)** - Instructs Claude to avoid "AI slop" or generic aesthetics and to make bold design decisions. Works very well for React & Tailwind.
- **[web-artifacts-builder](https://github.com/anthropics/skills/tree/main/skills/web-artifacts-builder)** - Build complex claude.ai HTML artifacts using React, Tailwind CSS, and shadcn/ui components
- **[mcp-builder](https://github.com/anthropics/skills/tree/main/skills/mcp-builder)** - Guide for creating high-quality MCP servers to integrate external APIs and services
- **[webapp-testing](https://github.com/anthropics/skills/tree/main/skills/webapp-testing)** - Test local web applications using Playwright for UI verification and debugging

### Communication

- **[brand-guidelines](https://github.com/anthropics/skills/tree/main/skills/brand-guidelines)** - Apply Anthropic's official brand colors and typography to artifacts
- **[internal-comms](https://github.com/anthropics/skills/tree/main/skills/internal-comms)** - Write internal communications like status reports, newsletters, and FAQs

### Skill Creation

- **[skill-creator](https://github.com/anthropics/skills/tree/main/skills/skill-creator)** - Interactive skill creation tool that guides you through building new skills with Q&A

## 🌟 Community Skills

> [!Warning]
> Skills can execute arbitrary code in Claude's environment.
>
> See [Security & Best Practices](#-security--best-practices) for more information

### Collections & Libraries

- **[obra/superpowers](https://github.com/obra/superpowers)** - Core skills library for Claude Code with 20+ battle-tested skills including TDD, debugging, and collaboration patterns
  - Features `/brainstorm`, `/write-plan`, `/execute-plan` commands and skills-search tool
  - [superpowers-skills](https://github.com/obra/superpowers-skills) - Community-editable skills repository
  - [Blog: Superpowers](https://blog.fsck.com/2025/10/09/superpowers/) - Author's overview by Jesse Vincent
  - Installation: `/plugin marketplace add obra/superpowers-marketplace`

- **[obra/superpowers-lab](https://github.com/obra/superpowers-lab)** - Experimental skills for `Claude Code Superpowers` (see above)
  - Uses new techniques that are still being refined and tested (i.e. skills here may change over time)
  - [Blog post about its development](https://blog.fsck.com/2025/10/23/naming-claude-plugins/)
  - Install from `superpowers-marketplace` plugin

### Individual Skills

> These will be broken down into categories once there are enough community skills available to list

| Skill | Description |
| --- | --- |
| **[ios-simulator-skill](https://github.com/conorluddy/ios-simulator-skill)** | iOS app building, navigation, and testing through automation |
| **[ffuf-web-fuzzing](https://github.com/jthack/ffuf_claude_skill)** | Expert guidance for ffuf web fuzzing during penetration testing, including authenticated fuzzing with raw requests, auto-calibration, and result analysis |
| **[playwright-skill](https://github.com/lackeyjb/playwright-skill)** | General-purpose browser automation using Playwright |
| **[claude-d3js-skill](https://github.com/chrisvoncsefalvay/claude-d3js-skill)** | Visualizations in d3.js |
| **[claude-scientific-skills](https://github.com/K-Dense-AI/claude-scientific-skills)** | Comprehensive collection of ready-to-use scientific skills, including working with specialized scientific libraries and databases |
| **[web-asset-generator](https://github.com/alonw0/web-asset-generator)** | Generates web assets like favicons, app icons, and social media images |
| **[loki-mode](https://github.com/asklokesh/claudeskill-loki-mode)** | Multi-agent autonomous startup system - orchestrates 37 AI agents across 6 swarms to build, deploy, and operate a complete startup from PRD to revenue |
| **[Trail of Bits Security Skills](https://github.com/trailofbits/skills)** | Security skills for static analysis with CodeQL/Semgrep, variant analysis, code auditing, and vulnerability detection |
| **[frontend-slides](https://github.com/zarazhangrui/frontend-slides)** | Create animation-rich HTML presentations — from scratch or by converting PowerPoint files |
| **[Expo Skills](https://github.com/expo/skills)** | Official skills by the Expo team for developing Expo apps |
| **[shadcn/ui](https://ui.shadcn.com/docs/skills)** | Give Claude Code context on shadcn components as well as pattern enforcement |

_More community skills coming soon! Submit a PR to add your skill._

### Tools

- **[yusufkaraaslan/Skill_Seekers](https://github.com/yusufkaraaslan/Skill_Seekers)** - Convert documentation websites into Claude Skills
- **[claude-hud](https://github.com/jarrodwatts/claude-hud)** - A Claude Code plugin that shows what's happening — context usage, active tools, running agents, and todo progress. Always visible below your input.
- **[Claude-to-IM](https://github.com/op7418/Claude-to-IM-skill)** - Bridge Claude Code / Codex to IM platforms — chat with AI coding agents from Telegram, Discord, Feishu/Lark, or QQ.

### UI

- **[CodePilot](https://github.com/op7418/CodePilot)** - A desktop GUI for Claude Code — chat, code, and manage projects visually. Built with Electron + Next.js.

## ✏️ Creating Your First Skill

<details>
<summary><strong>Step-by-Step Guide</strong></summary>

### Method 1: Use skill-creator (Recommended)

The easiest way to create a skill is to use the built-in `skill-creator`:

1. Enable the skill-creator skill in Claude
2. Ask Claude: "Use the skill-creator to help me build a skill for [your task]"
3. Answer the interactive questions about your workflow
4. Claude generates the complete skill structure for you

### Method 2: Manual Creation

1. **Create folder structure**:

   ```
   my-skill/
   ├── SKILL.md          # Main skill file with frontmatter
   ├── scripts/          # Optional executable scripts
   │   └── helper.py
   └── resources/        # Optional supporting files
       └── template.json
   ```

2. **Create SKILL.md with frontmatter**:

   ```yaml
   ---
   name: my-skill
   description: Brief description for skill discovery (keep concise)
   ---

   # Detailed Instructions

   Claude will read these instructions when the skill is activated.

   ## Usage
   Explain how to use this skill...

   ## Examples
   Provide clear examples...
   ```

3. **Add executable scripts** (optional):

   - Python, JavaScript, or other scripts Claude can execute
   - Reference them in your SKILL.md instructions

4. **Test locally**:

   - Install the skill in Claude Code or Claude Desktop
   - Test with relevant tasks
   - Iterate and refine

5. **Share**:
   - Publish to GitHub
   - Submit to this awesome list via PR
   - Share with your team via git repos or internal distribution

### Best Practices

- **Keep descriptions concise** - The frontmatter description is used for skill discovery
- **Use clear, actionable instructions** - Write instructions as if for a human collaborator
- **Include examples** - Show specific examples in your SKILL.md
- **Version your skills** - Use git tags for version management
- **Document dependencies** - List any prerequisites or required packages
- **Test thoroughly** - Verify your skill works across different scenarios

</details>

## 📚 Official Documentation & Resources

### Getting Started

- [What are Skills?](https://support.claude.com/en/articles/12512176-what-are-skills) - Official support article explaining Claude Skills
- [Using Skills in Claude](https://support.claude.com/en/articles/12512180-using-skills-in-claude) - How to enable and use skills

### Documentation

- [Claude Skills Announcement](https://www.anthropic.com/news/skills) - Official announcement from Anthropic
- [Equipping Agents with Skills](https://www.anthropic.com/engineering/equipping-agents-for-the-real-world-with-agent-skills) - Engineering deep dive on Agent Skills
- [Claude Developer Platform](https://docs.claude.com/) - Official documentation
- [Skills API Endpoint](https://platform.claude.com/docs/en/api/beta/skills) - `/v1/skills` API documentation

### Repositories & Examples

- [anthropics/skills](https://github.com/anthropics/skills) - Official public repository for Skills
- [Claude Cookbooks - Skills](https://github.com/anthropics/claude-cookbooks/tree/main/skills) - Example notebooks and tutorials

---

## 📅 Recent Updates

### November 2025

- **Nov 13**: Anthropic publishes [Skills Explained](https://claude.com/blog/skills-explained) - Comprehensive guide covering progressive disclosure architecture, decision matrices for Skills vs Prompts/Subagents/Projects, and best practices

### October 2025

- **Oct 18**: Major community repositories emerge: [obra/superpowers](https://github.com/obra/superpowers) skills library
- **Oct 17**: Community publishes practical tutorials on DEV.to and Medium
- **Oct 16**: 🎉 **Claude Skills officially announced** - Available across Claude.ai, Code, and API
- **Oct 16**: Initial skills released including docx, pdf, pptx, xlsx, algorithmic-art, canvas-design, and more

## 💡 Skills vs Other Approaches

### Quick Reference: When to Use What

| Tool | Best For |
|------|----------|
| **Skills** | Reusable procedural knowledge across conversations |
| **Prompts** | One-time instructions and immediate context |
| **Projects** | Persistent background knowledge within workspaces |
| **Subagents** | Independent task execution with specific permissions |
| **MCP** | Connecting Claude to external data sources |

**Use Skills when**: Capabilities should be accessible to any Claude instance. They're portable expertise.

**Use Subagents when**: You need self-contained agents designed for specific purposes with independent workflows and restricted tool access.

**Combined approach**: Subagents can leverage Skills for specialized expertise, merging independence with portable knowledge.

**Key insight**: *If you find yourself typing the same prompt repeatedly across multiple conversations, it's time to create a Skill.*

### Skills vs MCP (Model Context Protocol)

| Feature              | Skills                                        | MCP                               |
| -------------------- | --------------------------------------------- | --------------------------------- |
| **Purpose**          | Task-specific expertise and workflows         | External data/API integration     |
| **Portability**      | Same format everywhere (Claude.ai, Code, API) | Requires server configuration     |
| **Code Execution**   | Can include executable scripts                | Provides tools/resources          |
| **Token Efficiency** | 30-50 tokens until loaded                     | Varies by implementation          |
| **Best For**         | Repeatable tasks, document workflows          | Database access, API integrations |

**Use Together**: Skills can create MCP servers! The `mcp-builder` skill helps build high-quality MCP integrations.

#### Skills vs System Prompts

| Feature           | Skills                                              | System Prompts                    |
| ----------------- | --------------------------------------------------- | --------------------------------- |
| **Structure**     | Folder with YAML frontmatter, instructions, scripts | Plain text instructions           |
| **Reusability**   | Version-controlled, shareable, composable           | Copy-paste, conversation-specific |
| **Loading**       | On-demand (only when relevant)                      | Always in context                 |
| **Maintenance**   | Centralized updates                                 | Manual updates per conversation   |
| **Composability** | Multiple skills stack automatically                 | Manual combination                |

## 📖 Tutorials & Guides

### Written Tutorials

- [How to Create Your First Claude Skill](https://skywork.ai/blog/ai-agent/how-to-create-claude-skill-step-by-step-guide/) - Step-by-step tutorial with examples
- [How to Use Skills in Claude Code](https://skywork.ai/blog/how-to-use-skills-in-claude-code-install-path-project-scoping-testing/) - Installation, project scoping, and testing guide

### Video Tutorials

_Video tutorials coming soon! Have a good video about Claude Skills? Submit a PR!_

<details>
<summary>Example topics we'd love to see</summary>

- Getting started with Claude Skills
- Building your first custom skill
- Skills vs MCP comparison
- Enterprise deployment strategies
</details>

## 📰 Articles & Blog Posts

- [Skills Explained](https://claude.com/blog/skills-explained) - Official Anthropic blog post covering progressive disclosure, use cases, and when to use Skills vs other tools
- [Simon Willison: Claude Skills are awesome, maybe a bigger deal than MCP](https://simonwillison.net/2025/Oct/16/claude-skills/) - Technical deep dive and analysis

## 🔒 Security & Best Practices

⚠️ **Important**: Skills can execute arbitrary code in Claude's environment. Only install skills from trusted sources.

<details>
<summary><strong>Security Guidelines & Best Practices</strong></summary>

### Vetting Skills

- **Only install skills from trusted sources**
- **Review SKILL.md and all scripts** before enabling a skill
- **Be cautious of skills** that request sensitive data access
- **Audit carefully** before deploying to production or enterprise environments

### Security Concerns

- **Malicious skills** may introduce vulnerabilities or enable data exfiltration
- **Prompt injection attacks** could be amplified through compromised skills
- **Sandboxing limitations** - Understand the security model before enterprise deployment
- **Security research**: [Weaponizing Claude Code Skills](https://medium.com/@yossifqassim/weaponizing-claude-code-skills-from-5-5-to-remote-shell-a14af2d109c9) - Analysis of potential security risks

### Best Practices

- **Version control** - Track all skills in git with proper version tags
- **Code review** - Peer review custom skills before team distribution
- **Least privilege** - Only grant necessary permissions and access
- **Regular audits** - Periodically review installed skills
- **Documentation** - Maintain clear documentation for custom skills
- **Testing** - Thoroughly test skills in non-production environments first

### Enterprise Considerations

- As of October 2025, Claude.ai does not support centralized admin management for custom skills
- Use version control and internal repositories for team skill distribution
- Establish clear policies for skill vetting and approval
- Monitor skill usage and performance

</details>

## 🛠️ Troubleshooting

<details>
<summary><strong>Known Issues & Common Problems</strong></summary>

### Known Issues

- **Linux path bug (Oct 18, 2025)**: Agent SDK uses hardcoded macOS paths instead of environment home directory

  - [Issue #268](https://github.com/anthropics/claude-agent-sdk-python/issues/268)
  - Workaround: Manually specify skill paths

- **Enterprise distribution**: No centralized admin management yet for custom skills on claude.ai
  - Use git repositories for team distribution
  - API integration provides more control

### Common Problems

**Skills not appearing in Claude**

- Check Settings > Capabilities to ensure Skills are enabled
- For Team/Enterprise: Verify admin has enabled Skills organization-wide
- Restart Claude after installing new skills

**Skills not loading/activating**

- Verify SKILL.md has proper YAML frontmatter format
- Check that `name` and `description` fields are present
- Ensure file structure matches expected format

**Permission errors**

- Review admin settings for Team/Enterprise accounts
- Check file permissions in skill directories
- Verify API key has appropriate permissions

**Skill execution failures**

- Check script dependencies are installed
- Review error logs for specific issues
- Test scripts independently outside of Claude

### Getting Help

- [Official Skills Repository Issues](https://github.com/anthropics/skills/issues)
- [Claude Documentation](https://docs.claude.com/)
- [Community Discussions](https://github.com/anthropics/skills/discussions)

</details>

## ❓ FAQ

<details>
<summary><strong>Common Questions</strong></summary>

**Q: How much do skills impact token usage?**

A: Skills are highly efficient thanks to progressive disclosure. Each skill uses only ~100 tokens during metadata scanning to determine relevance. When activated, the full skill content loads at <5k tokens. Bundled resources only load as needed.

**Q: What's the difference between Claude Skills and Agent Skills?**

A: They are the same thing.

**Q: Can I share skills with my team?**

A: Yes! Skills can be shared via:

- Git repositories (recommended)
- Internal file sharing
- Claude API for programmatic distribution
- Enterprise-wide deployment features (coming soon)

**Q: Do skills work with all Claude models?**

A: Skills are available for Pro, Max, Team, and Enterprise users. Free tier users do not have access to Skills.

**Q: Can skills call external APIs?**

A: Yes, skills can include scripts that call external APIs. For complex API integrations, consider using MCP (Model Context Protocol) alongside skills.

**Q: How does Claude decide which skill to use?**

A: Claude scans all available skills' frontmatter (name and description), evaluates relevance to the current task, then loads the full content of relevant skills. Multiple skills can be loaded and composed together automatically.

**Q: Can I use Skills and MCP together?**

A: Absolutely! They complement each other. Use Skills for task-specific workflows and MCP for external data/API integration. The `mcp-builder` skill can even help you build MCP servers.

**Q: Are there any costs beyond my Claude subscription?**

A: No additional costs for using official skills. Community and custom skills are free to use, though some may require external services (APIs, databases, etc.) that have their own costs.

**Q: Can I monetize custom skills?**

A: Currently, there is no official marketplace for paid skills. Anthropic has mentioned plans for community contributions and a potential marketplace in the future.

**Q: How do I update a skill?**

A: For skills from git repositories, pull the latest changes. For manually installed skills, replace the skill folder with the updated version. Always test updates in a non-production environment first.

</details>

## Related Research in This Repo

- [research/agent-harness-architecture-2026.md](research/agent-harness-architecture-2026.md) - architecture blueprint and implementation guidance
- [research/model-is-not-key-harness-is.md](research/model-is-not-key-harness-is.md) - Chinese synthesis of the 2026 harness engineering shift
- [research/deep-research-report.md](research/deep-research-report.md) - supporting research notes

## Contributing

PRs are welcome. Please prefer:

- official upstream repos over mirrors
- registries over long-tail one-off entries when a category is exploding
- concise descriptions that explain why a repo is harness-related
- exact links to GitHub repos, not marketing pages

If you are submitting a `Skill`, keep the original skill catalog conventions as well.

See [CONTRIBUTING.md](CONTRIBUTING.md) for submission guidance.
