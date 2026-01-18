# SkillsMP Skills Recommendations for PAI

> **Purpose:** Catalog of best-in-class skills from [SkillsMP](https://skillsmp.com/) that align with PAI's architecture, planned features, and objectives.
>
> **Last Updated:** January 2026
>
> **Usage:** Reference this document when building out new PAI capabilities. Each section maps to a PAI system or planned feature.

---

## Table of Contents

1. [Executive Summary](#executive-summary)
2. [PAI Existing vs SkillsMP Comparison](#pai-existing-vs-skillsmp-comparison)
3. [Memory System Skills](#memory-system-skills)
4. [Agent Orchestration Skills](#agent-orchestration-skills)
5. [Algorithm Phase Skills](#algorithm-phase-skills)
6. [Planned Feature Skills](#planned-feature-skills)
7. [Hook & Automation Skills](#hook--automation-skills)
8. [Browser & Research Skills](#browser--research-skills)
9. [Security & Quality Skills](#security--quality-skills)
10. [Documentation & Knowledge Skills](#documentation--knowledge-skills)
11. [Skill Development Skills](#skill-development-skills)
12. [Installation Guide](#installation-guide)
13. [Integration Recommendations](#integration-recommendations)

---

## Executive Summary

SkillsMP hosts **63,000+ agent skills** using the open SKILL.md standard, compatible with Claude Code. After analyzing PAI's 8 existing skills, planned features, and The Algorithm's 7 phases, the following categories have the highest potential value:

| Priority | Category | PAI Gap | Top SkillsMP Candidate |
|----------|----------|---------|------------------------|
| **P0** | Local Model Support | Planned, not built | [ollama](https://skillsmp.com/skills/rawveg-skillsforge-marketplace-ollama-skill-md) |
| **P0** | Multi-Agent Swarm | Basic in pai-agents | [swarm-orchestration](https://skillsmp.com/skills/ruvnet-claude-flow-claude-skills-swarm-orchestration-skill-md) |
| **P1** | Deep Research | Not in PAI | [run-deep-research](https://skillsmp.com/skills/monarch-initiative-deep-research-client-claude-skills-run-deep-research-skill-md) |
| **P1** | Persistent Memory | MEMORY system exists | [quantum-memory](https://skillsmp.com/zh/skills/expressedai-cli-claude-skills-quantum-memory-skill-md) |
| **P1** | Notifications | Planned, partial | [social-media](https://skillsmp.com/skills/sgcarstrends-sgcarstrends-claude-skills-social-media-skill-md) |
| **P2** | TDD Enforcement | Manual via Algorithm | [tdd](https://skillsmp.com/skills/lucastamoios-celeiro-claude-skills-tdd-skill-md) |
| **P2** | Code Review | Not specialized | [code-review-excellence](https://skillsmp.com/skills/wshobson-agents-plugins-developer-essentials-skills-code-review-excellence-skill-md) |
| **P2** | Security Scanning | Basic in SECURITY | [security-scanner](https://skillsmp.com/skills/matteocervelli-llms-claude-skills-security-scanner-skill-md) |

---

## PAI Existing vs SkillsMP Comparison

### Current PAI Skills (8 Total)

| PAI Skill | Purpose | SkillsMP Alternative | Recommendation |
|-----------|---------|---------------------|----------------|
| **CORE** | Identity, personality, preferences | No direct equivalent | **Keep** - PAI-specific |
| **THEALGORITHM** | 7-phase execution engine | No equivalent | **Keep** - Unique to PAI |
| **Agents** | Dynamic agent composition | [flow-coach](https://skillsmp.com/skills/cgbarlow-skills-flow-coach-skill-md), [swarm-orchestration](https://skillsmp.com/skills/ruvnet-claude-flow-claude-skills-swarm-orchestration-skill-md) | **Enhance** - Add swarm topologies |
| **Prompting** | Template-based prompts | [skill-factory](https://skillsmp.com/skills/tenequm-claude-plugins-skill-factory-skill-skill-md) | **Keep** - Well-suited for PAI |
| **Browser** | Playwright automation | [planning-architect](https://skillsmp.com/skills/amo-tech-ai-medellin-spark-claude-skills-planning-architect-skill-md), [peekaboo](https://skillsmp.com/skills/steipete-clawdis-skills-peekaboo-skill-md) | **Enhance** - Add accessibility testing |
| **Art** | Excalidraw image generation | [plantuml](https://skillsmp.com/skills/spillwavesolutions-plantuml-skill-md) | **Enhance** - Add technical diagrams |
| **Upgrades** | Monitor Anthropic releases | No equivalent | **Keep** - Unique to PAI |
| **CreateSkill** | Skill authoring | [skill-factory](https://skillsmp.com/skills/tenequm-claude-plugins-skill-factory-skill-skill-md), [skill-builder](https://skillsmp.com/skills/metaskills-skill-builder-skill-md) | **Compare** - May be superior |

---

## Memory System Skills

PAI's three-tier MEMORY system (CAPTURE → SYNTHESIS → APPLICATION) can be enhanced with specialized skills.

### Best-in-Class Recommendations

#### 1. [quantum-memory](https://skillsmp.com/zh/skills/expressedai-cli-claude-skills-quantum-memory-skill-md) by ExpressedAi
**Rating: Highly Recommended**

- **What it does:** Transforms ephemeral chat into persistent intelligence
- **Memory categories:** patterns, insights, learnings, strategies, neuron activation, wormhole paths
- **Why for PAI:** Aligns with SYNTHESIS tier's signal categorization
- **Integration point:** Extend `MEMORY/Signals/` with quantum-memory categories

#### 2. [session-memory](https://skillsmp.com/skills/anortham-goldfish-claude-plugin-skills-session-memory-skill-md) by anortham
**Rating: Recommended**

- **What it does:** Restores full working context at session start
- **Why for PAI:** Complements SessionStart hook for context restoration
- **Integration point:** Enhance `LoadContext.hook.ts`

#### 3. [project-memory-store](https://skillsmp.com/skills/hungson175-cio-rag-chatbot-claude-skills-project-memory-store-skill-md) by hungson175
**Rating: Consider**

- **What it does:** Compact project-specific memory (3-5 sentences max)
- **Why for PAI:** Prevents memory bloat in CAPTURE tier
- **Integration point:** Use for per-task `Work/[Task-Name]/` summaries

#### 4. [agent-memory](https://skillsmp.com/skills/yamadashy-repomix-claude-skills-agent-memory-skill-md) by yamadashy
**Rating: Consider**

- **What it does:** Persistent memory space organized into category folders
- **Triggers:** "remember this", "save this", "what did we discuss about..."
- **Why for PAI:** Natural language memory interface

#### 5. [pattern-learning](https://skillsmp.com/skills/bejranonda-llm-autonomous-agent-plugin-for-claude-skills-pattern-learning-skill-md) by bejranonda
**Rating: Highly Recommended**

- **What it does:** Autonomous pattern learning and recognition
- **Why for PAI:** Directly supports LEARN phase and `patterns.jsonl` signals
- **Integration point:** Feed patterns to `MEMORY/Signals/patterns.jsonl`

---

## Agent Orchestration Skills

PAI's hybrid agent model (Named + Dynamic) with 28 traits can be extended with advanced orchestration patterns.

### Best-in-Class Recommendations

#### 1. [swarm-orchestration](https://skillsmp.com/skills/ruvnet-claude-flow-claude-skills-swarm-orchestration-skill-md) by ruvnet
**Rating: Highly Recommended**

- **What it does:** Multi-agent swarms with parallel task execution
- **Features:**
  - Parallel task execution
  - Sequential pipelines with dependencies
  - Adaptive topology (auto-switches based on task)
  - Auto-orchestration (swarm decides strategy)
- **Why for PAI:** Extends EXECUTE phase parallel capabilities
- **Integration point:** Use for THOROUGH/DETERMINED effort levels

#### 2. [flow-coach](https://skillsmp.com/skills/cgbarlow-skills-flow-coach-skill-md) by cgbarlow
**Rating: Highly Recommended**

- **What it does:** Task assessment with orchestration mode recommendation
- **Swarm Topologies:**
  - MESH (fully connected, high collaboration)
  - HIERARCHICAL (queen coordinator + workers)
  - RING (circular/pipeline processing)
  - STAR (central coordinator hub-and-spoke)
- **8 Swarm Coordination Agents:** hierarchical-coordinator, mesh-coordinator, adaptive-coordinator, queen-coordinator, worker-specialist, scout-explorer, swarm-memory-manager, collective-intelligence
- **Why for PAI:** Superior to current AgentFactory orchestration
- **Integration point:** Replace/extend `THEDELEGATIONSYSTEM.md`

#### 3. [flow-nexus-swarm](https://skillsmp.com/skills/ruvnet-claude-flow-claude-skills-flow-nexus-swarm-skill-md) by ruvnet
**Rating: Recommended**

- **What it does:** Cloud-based multi-topology orchestration
- **Features:** Event-driven workflows, template library, real-time monitoring
- **Priority levels:** low, medium, high, critical
- **Why for PAI:** Adds priority-based routing

#### 4. [orchestrating-tmux-claudes](https://skillsmp.com/skills/dbmcco-claude-agent-toolkit-skills-orchestrating-tmux-claudes-skill-md) by dbmcco
**Rating: Consider**

- **What it does:** Multi-AI orchestration in tmux panes
- **Features:** Self-discovering coordinator, mandatory verification, zero hallucination via imperative commands
- **Why for PAI:** Alternative approach for local multi-agent work

#### 5. [create-agent-skills](https://skillsmp.com/skills/everyinc-compound-engineering-plugin-plugins-compound-engineering-skills-create-agent-skills-skill-md) by EveryInc
**Rating: Recommended**

- **What it does:** Imports multi-agent coordination patterns
- **Imports:** orchestrating-multi-agent-systems, multi-agent-coordination, planner, swarm
- **Why for PAI:** Reference implementation for agent creation

---

## Algorithm Phase Skills

Skills organized by THE ALGORITHM's 7 phases.

### OBSERVE Phase (Create ISC rows)

| Skill | Author | Purpose | Link |
|-------|--------|---------|------|
| **deep-research** | cameronsjo | Thorough investigation triggers | [Link](https://skillsmp.com/skills/cameronsjo-claude-marketplace-plugins-deep-research-skills-deep-research-skill-md) |
| **run-deep-research** | monarch-initiative | Multi-provider research with citations | [Link](https://skillsmp.com/skills/monarch-initiative-deep-research-client-claude-skills-run-deep-research-skill-md) |

**run-deep-research Details:**
- Providers: OpenAI Deep Research, FutureHouse Falcon, Perplexity AI, Consensus AI
- Features: Markdown reports with citations, YAML frontmatter, file caching, templates
- **Integration:** Use for OBSERVE phase when effort ≥ THOROUGH

### THINK Phase (Complete ISC rows)

| Skill | Author | Purpose | Link |
|-------|--------|---------|------|
| **codex-peer-review** | leegonzales | Cross-validation between Claude & Codex | [Link](https://skillsmp.com/skills/leegonzales-aiskills-codexpeerreview-codex-peer-review-skill-md) |

**codex-peer-review Details:**
- Architecture validation and critique
- Design decision cross-validation
- Alternative approach generation
- **Integration:** Use for THINK phase devil's advocacy

### PLAN Phase (Order ISC rows)

| Skill | Author | Purpose | Link |
|-------|--------|---------|------|
| **task-orchestration** | jpicklyk | Task decomposition & parallel routing | [Link](https://skillsmp.com/skills/jpicklyk-task-orchestrator-claude-plugins-task-orchestrator-skills-task-orchestration-skill-md) |
| **planning-architect** | amo-tech-ai | Comprehensive planning with E2E tests | [Link](https://skillsmp.com/skills/amo-tech-ai-medellin-spark-claude-skills-planning-architect-skill-md) |
| **prp-workflow** | petyosi | Product Requirements Prompt workflow | [Link](https://skillsmp.com/skills/petyosi-rc-claude-skills-prp-workflow-skill-md) |
| **workflow-generator** | bradleygolden | Generates /research, /plan, /implement, /qa | [Link](https://skillsmp.com/skills/bradleygolden-claude-marketplace-elixir-plugins-meta-skills-workflow-generator-skill-md) |

**task-orchestration Details:**
- Task decomposition with parallel vs sequential logic
- Dependency-aware execution with automatic specialist routing
- Progress monitoring and cascading completion
- **Integration:** Enhance PLAN phase dependency mapping

### BUILD Phase (Refine ISC rows for testability)

| Skill | Author | Purpose | Link |
|-------|--------|---------|------|
| **tdd** | lucastamoios | RED-GREEN-REFACTOR enforcement | [Link](https://skillsmp.com/skills/lucastamoios-celeiro-claude-skills-tdd-skill-md) |
| **preflight-checks** | charlesjones-dev | Type checking, linting, tests | [Link](https://skillsmp.com/skills/charlesjones-dev-claude-code-plugins-dev-plugins-ai-workflow-skills-preflight-checks-skill-md) |

**tdd Details:**
- Proactively enforces TDD when implementing features
- Guides RED-GREEN-REFACTOR cycle
- **Integration:** Use for BUILD phase success criteria definition

### EXECUTE Phase (Do the work)

| Skill | Author | Purpose | Link |
|-------|--------|---------|------|
| **code-cleanup** | krmcbride | Batch refactoring without design decisions | [Link](https://skillsmp.com/skills/krmcbride-claude-plugins-essentials-skills-code-cleanup-skill-md) |
| **review-implementing** | LEEI1337 | Implements changes from code review feedback | [Link](https://skillsmp.com/skills/leei1337-phantom-neural-cortex-claude-skills-review-implementing-skill-md) |

### VERIFY Phase (Check each ISC row)

| Skill | Author | Purpose | Link |
|-------|--------|---------|------|
| **validation-gate** | krzemienski | ALL tests must pass, visual verification | [Link](https://skillsmp.com/skills/krzemienski-claude-mobile-expo-claude-skills-claude-mobile-validation-gate-skill-md) |
| **thoroughness** | pr-pm | Comprehensive verification checklists | [Link](https://skillsmp.com/skills/pr-pm-prpm-claude-skills-thoroughness-skill-md) |
| **accessibility-testing** | aj-geddes | axe-playwright for a11y testing | [Link](https://skillsmp.com/skills/aj-geddes-useful-ai-prompts-skills-accessibility-testing-skill-md) |
| **python-quality-checker** | matteocervelli | Black, mypy, flake8, bandit, complexity | [Link](https://skillsmp.com/skills/matteocervelli-llms-claude-skills-python-quality-checker-skill-md) |

**validation-gate Details:**
- Core principle: ALL tests must pass
- Uses expo-mcp for visual verification
- Stops immediately if any tests fail
- **Integration:** Direct match for VERIFY phase skeptical verification

### LEARN Phase (Output results)

| Skill | Author | Purpose | Link |
|-------|--------|---------|------|
| **pattern-learning** | bejranonda | Autonomous pattern recognition | [Link](https://skillsmp.com/skills/bejranonda-llm-autonomous-agent-plugin-for-claude-skills-pattern-learning-skill-md) |
| **smart-docs** | sopaco | Architecture analysis & documentation | [Link](https://skillsmp.com/skills/sopaco-deepwiki-rs-skills-smart-docs-skill-md) |

---

## Planned Feature Skills

Skills for PAI's roadmap features.

### Local Model Support (Planned)

#### [ollama](https://skillsmp.com/skills/rawveg-skillsforge-marketplace-ollama-skill-md) by rawveg
**Rating: Essential**

- **Coverage:**
  - All API endpoints (`/api/generate`, `/api/chat`, `/api/embed`)
  - Authentication methods
  - OpenAI compatibility layer (`base_url='http://localhost:11434/v1/'`)
  - Environment variables (`OLLAMA_ORIGINS`, `HTTPS_PROXY`)
- **Integration:** Foundation for Local Model Support feature
- **Resources:** [docs.ollama.com](https://docs.ollama.com), [ollama.com/models](https://ollama.com/models)

### External Notifications (Planned)

#### [social-media](https://skillsmp.com/skills/sgcarstrends-sgcarstrends-claude-skills-social-media-skill-md) by sgcarstrends
**Rating: Recommended**

- **Integrations:**
  - Discord (webhook-based)
  - Telegram (Bot API)
  - LinkedIn (OAuth API)
  - Twitter (API v2)
- **Features:** Message templates, webhook URLs, API credentials
- **Missing:** Slack, Email, ntfy.sh (PAI's current targets)
- **Integration:** Partial coverage - combine with PAI's `THENOTIFICATIONSYSTEM.md`

### Voice/TTS (pai-voice-system exists)

#### [elevenlabs-voice-cloning](https://skillsmp.com/skills/onesmartguy-next-level-real-estate-claude-skills-ai-voice-audio-skills-elevenlabs-voice-cloning-skill-md) by onesmartguy
**Rating: Consider**

- **Coverage:** Voice cloning techniques, audio quality, training optimization
- **Features:** Emotion variety, speaking styles, pace variations
- **Integration:** Extend pai-voice-system with voice cloning for named agents

### Remote Access (Planned)

*No directly relevant skills found. Consider:*
- API scaffolding skills
- Webhook/REST endpoint skills
- Authentication patterns

### Outbound Phone Calling (Planned)

*No directly relevant skills found. This is a specialized capability.*

---

## Hook & Automation Skills

Skills for PAI's 8 hook event types.

### Best-in-Class Recommendations

#### 1. [Hook Development](https://skillsmp.com/skills/anthropics-claude-code-plugins-plugin-dev-skills-hook-development-skill-md) - Official Anthropic
**Rating: Essential Reference**

- **What it does:** Official hook development guidance
- **Events covered:** PreToolUse, PostToolUse, Stop, SubagentStop, SessionStart, SessionEnd, UserPromptSubmit, PreCompact, Notification
- **Why for PAI:** Authoritative reference for hook patterns

#### 2. [hooks-manager](https://skillsmp.com/skills/resolve-io-prism-skills-hooks-manager-skill-md) by resolve-io
**Rating: Recommended**

- **What it does:** Create, configure, test, debug hooks
- **Coverage:** All hook events with examples and best practices
- **Integration:** Use as development aid for new PAI hooks

#### 3. [hooks](https://skillsmp.com/skills/reggiechan74-claude-plugins-plugins-claude-code-metaskill-skills-hooks-skill-md) by reggiechan74
**Rating: Recommended**

- **Matchers:** Task, Bash, Glob, Grep, Read, Edit, Write, WebFetch, WebSearch
- **Event details:** SessionStart for loading context, installing deps, setting env vars
- **Integration:** Reference for matcher patterns

#### 4. [workflow-automation](https://skillsmp.com/skills/dnyoussef-ai-chrome-extension-claude-skills-github-integration-when-automating-github-actions-use-workflow-automation-skill-md) by dnyoussef
**Rating: Consider**

- **What it does:** GitHub Actions CI/CD optimization
- **Features:** Pipeline generation, security hardening, performance optimization
- **Integration:** Use for CI/CD hook automation

---

## Browser & Research Skills

Skills to enhance pai-browser-skill and add research capabilities.

### Browser Automation

#### 1. [planning-architect](https://skillsmp.com/skills/amo-tech-ai-medellin-spark-claude-skills-planning-architect-skill-md) by amo-tech-ai
**Rating: Recommended**

- **Playwright MCP tools:** Navigate, Snapshot, Click, Assert (wait_for)
- **Chrome DevTools:** Screenshot capability
- **E2E testing:** User journey implementation
- **Integration:** Add structured E2E test generation to Browser skill

#### 2. [peekaboo](https://skillsmp.com/skills/steipete-clawdis-skills-peekaboo-skill-md) by steipete
**Rating: Consider (macOS only)**

- **What it does:** Full macOS UI automation CLI
- **Features:** Capture/inspect screens, target UI elements, drive input, manage windows
- **Requirements:** Screen Recording + Accessibility permissions
- **Integration:** Alternative to Playwright for macOS desktop automation

#### 3. [accessibility-testing](https://skillsmp.com/skills/aj-geddes-useful-ai-prompts-skills-accessibility-testing-skill-md) by aj-geddes
**Rating: Highly Recommended**

- **What it does:** axe-playwright integration for accessibility
- **Integration:** Add to VERIFY phase for a11y validation

### Research Skills

#### 1. [run-deep-research](https://skillsmp.com/skills/monarch-initiative-deep-research-client-claude-skills-run-deep-research-skill-md) by monarch-initiative
**Rating: Highly Recommended**

- **Providers:** OpenAI Deep Research, FutureHouse Falcon, Perplexity AI, Consensus AI
- **Output:** Markdown reports with citations, YAML frontmatter
- **Features:** File caching, provider auto-detection, templates
- **Integration:** Add as research capability for OBSERVE phase

#### 2. [deep-research](https://skillsmp.com/skills/cameronsjo-claude-marketplace-plugins-deep-research-skills-deep-research-skill-md) by cameronsjo
**Rating: Recommended**

- **Triggers:** "deep dive", "dig deep", "thorough investigation", "comprehensive analysis"
- **Actions:** WebSearch extensively, spawn Explore agents, synthesize sources, provide citations
- **Integration:** UserPromptSubmit hook enhancement

---

## Security & Quality Skills

### Security Scanning

#### [security-scanner](https://skillsmp.com/skills/matteocervelli-llms-claude-skills-security-scanner-skill-md) by matteocervelli
**Rating: Highly Recommended**

- **Tools:**
  - Gitleaks (secret detection)
  - pip-audit (dependency checking)
  - Bandit (static analysis)
  - Semgrep, Trivy, Trufflehog
- **Output:** Reports by severity (Critical, High, Medium, Low, Informational)
- **Integration:** Enhance SECURITY.md enforcement in VERIFY phase

### Code Review

#### 1. [code-review-excellence](https://skillsmp.com/skills/wshobson-agents-plugins-developer-essentials-skills-code-review-excellence-skill-md) by wshobson
**Rating: Highly Recommended**

- **Checklists:**
  - Architecture: Does solution fit problem? Simpler approaches?
  - Logic: Edge cases, off-by-one, null checks, race conditions
  - Security: Input validation, SQL parameterization, authentication
  - Performance: N+1 queries, pagination, caching
  - Testing: Happy path, edge cases, error cases
- **Large features:** Request design doc first, review in stages
- **Integration:** Add as code review phase for Agent Engineer/Architect

#### 2. [codex-peer-review](https://skillsmp.com/skills/leegonzales-aiskills-codexpeerreview-codex-peer-review-skill-md) by leegonzales
**Rating: Recommended**

- **What it does:** Claude + Codex cross-validation
- **Use when:** High-stakes architecture, security-critical code, complex refactoring
- **Don't use:** Simple implementations, confident approach, time-sensitive fixes
- **Integration:** Use for THOROUGH+ effort reviews

#### 3. [code-cleanup](https://skillsmp.com/skills/krmcbride-claude-plugins-essentials-skills-code-cleanup-skill-md) by krmcbride
**Rating: Recommended**

- **Use for:** Bulk lint fixes, variable renaming, import updates, formatting
- **Integration:** Batch refactoring in EXECUTE phase

### Quality Assurance

#### [python-quality-checker](https://skillsmp.com/skills/matteocervelli-llms-claude-skills-python-quality-checker-skill-md) by matteocervelli
**Rating: Recommended (Python projects)**

- **Tools:** Black (formatting), mypy (types), flake8/ruff (linting), bandit (security), complexity analysis
- **Integration:** VERIFY phase for Python codebases

---

## Documentation & Knowledge Skills

### Technical Documentation

#### [smart-docs](https://skillsmp.com/skills/sopaco-deepwiki-rs-skills-smart-docs-skill-md) by sopaco
**Rating: Highly Recommended**

- **What it does:** Analyzes project structure, identifies patterns, creates C4 diagrams
- **Output:** Professional technical documentation
- **Use for:** Document codebases, understand architecture, create specs, generate guides
- **Integration:** Use for LEARN phase documentation output

### Diagram Generation

#### [plantuml](https://skillsmp.com/skills/spillwavesolutions-plantuml-skill-md) by SpillwaveSolutions
**Rating: Recommended**

- **UML types:** sequence, class, activity, state, component, deployment, use case, object, timing
- **Non-UML:** ER diagrams, Gantt charts, JSON/YAML visualization, mindmaps, WBS, network diagrams, wireframes
- **Integration:** Complement pai-art-skill for technical diagrams

---

## Skill Development Skills

Skills to enhance pai-core-install's CreateSkill capability.

### Best-in-Class Recommendations

#### 1. [skill-factory](https://skillsmp.com/skills/tenequm-claude-plugins-skill-factory-skill-skill-md) by tenequm
**Rating: Highly Recommended**

- **What it does:** Autonomous skill creation agent
- **Methods:** Documentation scraping, manual TDD construction, hybrid
- **Quality:** Ensures score ≥ 8.0/10 using Anthropic best practices
- **Integration:** May replace/enhance CreateSkill

#### 2. [skill-builder](https://skillsmp.com/skills/metaskills-skill-builder-skill-md) by metaskills
**Rating: Recommended**

- **What it does:** Expert Claude Code Skills architect
- **Features:** Interactive skill creation, conversion, maintenance
- **Integration:** Reference for skill authoring patterns

#### 3. [skill-development](https://skillsmp.com/skills/anthropics-claude-code-plugins-plugin-dev-skills-skill-development-skill-md) - Official Anthropic
**Rating: Essential Reference**

- **What it does:** Official guidance for effective skills
- **Key insight:** Skills transform Claude from general-purpose to specialized agent
- **Integration:** Authoritative reference for CreateSkill

---

## Installation Guide

### Installing Skills from SkillsMP

```bash
# Personal skills (all projects)
mkdir -p ~/.claude/skills/
cd ~/.claude/skills/

# Clone skill repository
git clone <skill-repo-url> <skill-name>

# Or copy SKILL.md directly
curl -o <skill-name>/SKILL.md <raw-skill-url>
```

### Project-Specific Skills

```bash
# Project skills (this project only)
mkdir -p .claude/skills/
cd .claude/skills/

# Clone skill
git clone <skill-repo-url> <skill-name>
```

### Skill Structure

```
skill-name/
├── SKILL.md          # Required - main instructions
├── scripts/          # Optional - executable code
├── references/       # Optional - documentation for context
└── assets/           # Optional - templates, icons, etc.
```

---

## Integration Recommendations

### Phase 1: Immediate Wins (No code changes)

| Skill | Install Location | Why |
|-------|-----------------|-----|
| [ollama](https://skillsmp.com/skills/rawveg-skillsforge-marketplace-ollama-skill-md) | `~/.claude/skills/ollama/` | Prepares for Local Model Support |
| [run-deep-research](https://skillsmp.com/skills/monarch-initiative-deep-research-client-claude-skills-run-deep-research-skill-md) | `~/.claude/skills/deep-research/` | Enhances OBSERVE phase immediately |
| [tdd](https://skillsmp.com/skills/lucastamoios-celeiro-claude-skills-tdd-skill-md) | `~/.claude/skills/tdd/` | Enforces BUILD phase testability |
| [code-review-excellence](https://skillsmp.com/skills/wshobson-agents-plugins-developer-essentials-skills-code-review-excellence-skill-md) | `~/.claude/skills/code-review/` | Enhances VERIFY phase |

### Phase 2: Agent Enhancement

| Skill | Integration Point | Why |
|-------|------------------|-----|
| [swarm-orchestration](https://skillsmp.com/skills/ruvnet-claude-flow-claude-skills-swarm-orchestration-skill-md) | Extend pai-agents-skill | Add swarm topologies (MESH, HIERARCHICAL, RING, STAR) |
| [flow-coach](https://skillsmp.com/skills/cgbarlow-skills-flow-coach-skill-md) | Replace THEDELEGATIONSYSTEM | Superior orchestration patterns |

### Phase 3: Memory & Learning

| Skill | Integration Point | Why |
|-------|------------------|-----|
| [quantum-memory](https://skillsmp.com/zh/skills/expressedai-cli-claude-skills-quantum-memory-skill-md) | Extend MEMORY system | Add pattern/insight categorization |
| [pattern-learning](https://skillsmp.com/skills/bejranonda-llm-autonomous-agent-plugin-for-claude-skills-pattern-learning-skill-md) | Enhance LEARN phase | Autonomous pattern recognition |

### Phase 4: Planned Features

| Planned Feature | Skill | Notes |
|-----------------|-------|-------|
| Local Model Support | [ollama](https://skillsmp.com/skills/rawveg-skillsforge-marketplace-ollama-skill-md) | Foundation complete |
| External Notifications | [social-media](https://skillsmp.com/skills/sgcarstrends-sgcarstrends-claude-skills-social-media-skill-md) | Partial - needs Slack/Email |
| Voice Cloning | [elevenlabs-voice-cloning](https://skillsmp.com/skills/onesmartguy-next-level-real-estate-claude-skills-ai-voice-audio-skills-elevenlabs-voice-cloning-skill-md) | Named agent voice identity |

---

## Sources

- [SkillsMP - Agent Skills Marketplace](https://skillsmp.com/)
- [Browse by Category](https://skillsmp.com/categories)
- [About SkillsMP](https://skillsmp.com/about)
- [AI & Machine Learning Skills](https://skillsmp.com/categories/ai-ml)
- [Knowledge Base Skills](https://skillsmp.com/categories/knowledge-base)
- [Documentation Skills](https://skillsmp.com/categories/documentation)
- [Anthropic Skills Repository](https://github.com/anthropics/skills)

---

*Document generated by analyzing 63,000+ SkillsMP skills against PAI v2.1.1 architecture.*
