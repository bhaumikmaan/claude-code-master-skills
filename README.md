<h1 align="center"> <img src="assets/claude-icon.svg" width="35"/> CLAUDE CODE MASTER SKILLS <img src="assets/claude-icon.svg" width="35"/></h1>

<div align="center">

A suite of 15 reusable skills derived from Claude Code's prompt engineering patterns. Each skill encodes production-grade workflows for code verification, multi-agent orchestration, security classification, and autonomous operation, distilled into standalone, composable skills for Claude code and/or any agentic coding environment (Cursor, Windsurf, Copilot, etc.).

[![bhaumikmaan - claude-code-master-skills](https://img.shields.io/static/v1?label=bhaumikmaan&message=claude-code-master-skills&color=D97757&logo=github)](https://github.com/bhaumikmaan/claude-code-master-skills "Go to GitHub repo")
&nbsp; [![stars - claude-code-master-skills](https://img.shields.io/github/stars/bhaumikmaan/claude-code-master-skills?style=social)](https://github.com/bhaumikmaan/claude-code-master-skills)
&nbsp; [![forks - claude-code-master-skills](https://img.shields.io/github/forks/bhaumikmaan/claude-code-master-skills?style=social)](https://github.com/bhaumikmaan/claude-code-master-skills)
&nbsp; [![License](https://img.shields.io/badge/License-MIT-D97757)](#license)
<br/>

<a href="https://github.com/bhaumikmaan/claude-code-master-skills#skill-catalog" target="_blank">
<img src="https://img.shields.io/badge/Browse-Skill%20Catalog-D97757?style=for-the-badge&logo=bookstack&logoColor=white" alt="Browse Skill Catalog"/>
</a>
&nbsp;
<a href="https://github.com/bhaumikmaan/claude-code-master-skills#installation" target="_blank">
<img src="https://img.shields.io/badge/Get%20Started-Installation-D97757?style=for-the-badge&logo=rocket&logoColor=white" alt="Installation Guide"/>
</a>
&nbsp;
<a href="https://github.com/bhaumikmaan/claude-code-master-skills/stargazers" target="_blank">
<img src="https://img.shields.io/badge/Star-This%20Repo-yellow?style=for-the-badge&logo=github" alt="Star this repo"/>
</a>
</div>

---

These aren't generic coding tips. They're tested behavioral patterns for tool selection, context management, failure modes, and multi-step task coordination and finetuned for Claude Code to get the best outcomes.

## Why Skills?

Claude Code is powerful out of the box, but it has well-known failure modes: verification avoidance, context exhaustion, gold-plating, and token waste. These skills encode precise countermeasures  built into Claude Code's prompt architecture:

- **Token efficiency** — Every skill enforces the `Glob → Grep → Read` cost hierarchy (near-zero → lightweight → heavy tokens). Your sessions stay lean instead of reading entire files unnecessarily.
- **Context preservation** — Skills like `context-summarization` and `session-handoff` produce structured summaries that survive compaction, so you don't lose work when the context window fills up.
- **Failure-mode inoculation** — Skills name the specific ways the model tends to fail and instruct the opposite. `code-verification` lists the exact rationalizations the model uses to skip checks. `disciplined-coding` blocks the gold-plating reflex.
- **Parallel execution** — `task-orchestration` and `code-review` spawn parallel subagents for independent work, cutting wall-clock time on complex tasks.
- **Safety guardrails** — `safe-autonomous-mode` and `security-review` encode the allow/deny classification patterns that prevent destructive actions in autonomous workflows.

## How It Works

Each skill is a self-contained `SKILL.md` with YAML frontmatter that Claude Code / Cursor discovers automatically. Drop the `skills/` directory into your project or `~/.claude/skills/` and they're available immediately.

```
skills/
  skill-name/
    SKILL.md          # Core skill (the behavioral instructions)
    user-config.md    # Your project-specific overrides (you own this)
```

**Invocation**: Skills with `user-invocable: true` can be triggered with `/skill-name`. Skills without `disable-model-invocation` can also auto-trigger when the model detects a matching context.

**Customization**: Every skill reads an optional `user-config.md` companion file. Your overrides survive skill updates since they're in a separate file. Fill in the HTML comment placeholders with your project's specifics.

## Skill Catalog

### Core Development Loop

These skills form the inner loop: explore code, write disciplined changes, verify they work.

| # | Skill | What It Does | Key Pattern |
|---|-------|-------------|-------------|
| 01 | [disciplined-coding](disciplined-coding/SKILL.md) | Enforces scoped, minimal, correct code changes. Blocks gold-plating, speculative abstractions, and unsolicited refactoring. | Negative constraint lists, anti-pattern enumeration, scope fencing |
| 02 | [code-verification](code-verification/SKILL.md) | Adversarial verification — tries to break implementations rather than confirm they work. Produces structured PASS/FAIL/PARTIAL verdicts. | Rationalization inventory, strategy-by-change-type matrix, adversarial probes |
| 03 | [codebase-exploration](codebase-exploration/SKILL.md) | Efficient read-only search and analysis. Finds files, searches content, answers architecture questions without modifying anything. | Tool cost hierarchy, thoroughness levels (quick/medium/thorough), parallel search |

### Coordination & Synthesis

Break down complex tasks, coordinate parallel work, and preserve context across sessions.

| # | Skill | What It Does | Key Pattern |
|---|-------|-------------|-------------|
| 04 | [task-orchestration](task-orchestration/SKILL.md) | Coordinates multi-step tasks across parallel workers. Handles research → synthesis → implementation → verification phases. | Worker prompt templates, continue-vs-spawn decision table, synthesis mandate |
| 05 | [context-summarization](context-summarization/SKILL.md) | Produces structured session summaries that survive context compaction. Two-phase output: private analysis + structured artifact. | No-tools sandwich, 9-section schema, verbatim quote anchoring |

### Planning & Review

Analyze before you build. Review after you ship.

| # | Skill | What It Does | Key Pattern |
|---|-------|-------------|-------------|
| 06 | [architectural-planning](architectural-planning/SKILL.md) | Read-only codebase analysis and implementation planning. Produces plans with tradeoff analysis and critical file lists. | ALL-CAPS read-only contract, 4-phase workflow, required output sections |
| 07 | [code-review](code-review/SKILL.md) | Three-pass parallel review: reuse, quality, and efficiency. Starts from git diff, not the whole codebase. | Diff-anchored scope, parallel subagent passes, consolidation with false-positive triage |
| 08 | [effective-tool-use](effective-tool-use/SKILL.md) | Optimal tool selection, parallelism, and safety. IDE tools over shell equivalents, parallel vs sequential execution, git safety. | Tool preference matrix, token cost hierarchy, HEREDOC commit messages |

### Specialized Domains

Security, debugging, and knowledge management — each with domain-specific patterns.

| # | Skill | What It Does | Key Pattern |
|---|-------|-------------|-------------|
| 09 | [security-review](security-review/SKILL.md) | Classifies activities as permitted, forbidden, or requiring authorization. Covers OWASP risks and boundary validation. | Permitted/forbidden/context-required triad, boundary analysis framework |
| 10 | [systematic-debugging](systematic-debugging/SKILL.md) | Structured diagnosis: maps symptoms to hypotheses, bounded log reading, two-part bug reports. | Symptom-to-hypothesis table, bounded I/O, diagnostic-only safety |
| 11 | [knowledge-management](knowledge-management/SKILL.md) | Classifies, stores, recalls, and maintains knowledge across sessions. Four memory types with recall verification. | Memory taxonomy (user/feedback/project/reference), propose-then-approve, drift caveat |

### Session & Automation

Browser testing, session continuity, autonomous operation, and meta-skill creation.

| # | Skill | What It Does | Key Pattern |
|---|-------|-------------|-------------|
| 12 | [browser-testing](browser-testing/SKILL.md) | Browser automation for testing web apps. Tab management, console monitoring, failure escalation. | Snapshot-before-interact, 2-3 failure escalation threshold, tab-per-session hygiene |
| 13 | [session-handoff](session-handoff/SKILL.md) | Structured session notes with fixed template, token budgets, and immutable section headers. | Template preservation, 2000 token/section budget, sentence-case titles (3-7 words) |
| 14 | [safe-autonomous-mode](safe-autonomous-mode/SKILL.md) | Safe autonomous operation with allow/deny rules, risk classification, pacing, and focus-aware behavior. | Conservative default (block on ambiguity), tick-based pacing, focus-state matrix |
| 15 | [prompt-engineering](prompt-engineering/SKILL.md) | Create new skills and agent configurations through structured interview and template generation. | 4-round interview, SKILL.md template with per-step success criteria, agent persona design |

## Skill Interdependency Graph

Skills are standalone but chain naturally. Each references related skills with lightweight cross-pointers — not "go read that skill" but "apply X pattern here."

```
architectural-planning
  |-- uses --> codebase-exploration (research phase)
  |-- outputs feed into --> task-orchestration (implementation plan)

task-orchestration
  |-- delegates to --> codebase-exploration (research workers)
  |-- delegates to --> code-verification (verification workers)
  |-- uses --> context-summarization (synthesis phase)

code-review
  |-- can trigger --> code-verification (deeper checks)

code-verification
  |-- uses --> codebase-exploration (gather evidence)
  |-- uses --> effective-tool-use (run tests safely)

systematic-debugging
  |-- uses --> codebase-exploration + effective-tool-use

context-summarization
  |-- feeds into --> knowledge-management
  |-- feeds into --> session-handoff

knowledge-management
  |-- recalled by --> session-handoff

prompt-engineering
  |-- can produce --> any other skill (meta-skill)
```

## Key Prompt Engineering Patterns

These cross-cutting techniques are consistently applied across all skills:

| Pattern | What It Does | Example |
|---------|-------------|---------|
| **Token cost hierarchy** | Glob (paths only, ~0 tokens) → Grep with `-C 3` (matched lines, lightweight) → Read (full file, heavy). Always narrow before you read. | Every skill involving code search enforces this ordering |
| **Sandwich reinforcement** | Critical constraint stated at the top AND repeated at the bottom of the skill | `code-verification`: "Reading code is not verification" at top, "If all your checks are returns 200, go back and break something" at bottom |
| **Failure-mode inoculation** | Name the specific failure mode the model tends toward, then instruct the opposite | `code-verification` lists 6 rationalizations for skipping checks |
| **Subagent delegation** | When research spans >5 files, spawn a subagent to research in isolated context | Prevents context exhaustion in the main session |
| **Negative instruction + positive example** | "Don't do X" immediately followed by "Instead, do Y" | `disciplined-coding`: "Don't add comments explaining WHAT" → "Only add WHY comments" |
| **Decision matrices over prose** | Compact tables that encode workflows in ~30 lines vs 200+ lines of explanation | `code-review` calibration table, `task-orchestration` continue-vs-spawn table |
| **Evidence-based completion** | Never claim "done" without verifiable evidence | `code-verification`: every check requires exact command + actual output |
| **Structured output contracts** | XML tags, JSON schemas, or markdown templates for machine-parseable responses | `context-summarization`: `<analysis>` + `<summary>` two-phase output |

## Project Customization

Every skill includes a `user-config.md` with HTML comment placeholders. Fill these in for your project:

```markdown
# Project Overrides — Code Verification

## Verification Commands
- Build: pnpm build
- Test: pnpm test
- Typecheck: pnpm tsc --noEmit
- Lint: pnpm lint

## Domain-Specific Probes
- Auth: always test with expired tokens and missing roles
- Payments: test zero-amount and currency mismatch

## Risk Thresholds
- HIGH: any change touching auth/ or payments/
```

Your overrides take precedence over skill defaults. They survive skill updates because they're in a separate file.

### Hardening Read-Only Skills

For skills like `architectural-planning` and `codebase-exploration` that should never modify files:

- Run with `--permission-mode plan` to enforce read-only at the system level
- Add `Edit(*)` and `Write(*)` to deny rules in `.claude/settings.json`

## Installation

### Per-Project (Recommended)

Copy the `skills/` directory into your project root. Skills apply to this project only.

```bash
cp -r skills/ your-project/skills/
```

### Global (All Projects)

Copy to your Claude config directory. Skills apply across all projects.

```bash
cp -r skills/ ~/.claude/skills/
```

### Cherry-Pick

Only want specific skills? Copy individual directories:

```bash
mkdir -p your-project/skills
cp -r skills/code-verification your-project/skills/
cp -r skills/disciplined-coding your-project/skills/
```

## Repository Structure

```
skills/
├── architectural-planning/
│   ├── SKILL.md                       # Read-only planning with tradeoff analysis
│   └── user-config.md                 # Architecture constraints, review gates
├── browser-testing/
│   ├── SKILL.md                       # Browser automation and verification
│   └── user-config.md                 # Dev server, auth steps, key pages
├── code-review/
│   ├── SKILL.md                       # Three-pass parallel review
│   └── user-config.md                 # Code smells, style guide, exclusions
├── code-verification/
│   ├── SKILL.md                       # Adversarial verification with verdicts
│   └── user-config.md                 # Test commands, probes, risk thresholds
├── codebase-exploration/
│   ├── SKILL.md                       # Efficient read-only search
│   └── user-config.md                 # Project structure, entry points, naming
├── context-summarization/
│   ├── SKILL.md                       # Structured session summaries
│   └── user-config.md                 # Focus areas, extra sections, length
├── disciplined-coding/
│   ├── SKILL.md                       # Scoped, minimal, correct changes
│   └── user-config.md                 # Standards, comment policy, off-limits
├── effective-tool-use/
│   ├── SKILL.md                       # Tool selection, parallelism, git safety
│   └── user-config.md                 # Shell commands, git conventions, sandbox
├── knowledge-management/
│   ├── SKILL.md                       # Memory taxonomy and recall verification
│   └── user-config.md                 # Knowledge destinations, retention policies
├── prompt-engineering/
│   ├── SKILL.md                       # Skill and agent creation workflow
│   └── user-config.md                 # Skill conventions, default permissions
├── safe-autonomous-mode/
│   ├── SKILL.md                       # Allow/deny rules, pacing, focus behavior
│   └── user-config.md                 # Custom allow/deny rules, pacing prefs
├── security-review/
│   ├── SKILL.md                       # Security classification and boundary analysis
│   └── user-config.md                 # Compliance, trust boundaries, threat model
├── session-handoff/
│   ├── SKILL.md                       # Fixed-template session notes
│   └── user-config.md                 # Template overrides, token budgets, title format
├── systematic-debugging/
│   ├── SKILL.md                       # Symptom-to-hypothesis diagnosis
│   └── user-config.md                 # Log locations, failure modes, diagnostics
└── task-orchestration/
    ├── SKILL.md                       # Multi-worker coordination
    └── user-config.md                 # Workflow phases, branch conventions, limits
```

## Design Principles

Every line in a SKILL.md earns its place by changing model behavior. These principles guided the entire suite:

- **Bullet lists over prose** — Faster to parse, lower token cost, harder to skim past
- **Negative constraints over positive examples** when the constraint is sufficient (~10 tokens vs ~50+)
- **Decision matrices over lengthy explanations** — 6 workflows in ~30 lines vs 200+ lines of prose
- **No "about this skill" introductions** — The frontmatter `description` handles discovery
- **No explaining what the model already knows** — File reading, grep, git basics are assumed
- **No generic advice** — "Write clean code" doesn't change behavior. "Only add comments when the WHY is non-obvious" does.

## What This Project Is

A collection of production-grade prompt engineering skills for agentic coding assistants, observed and distilled to give the best efficiency. The skills encode:

- How to assemble dynamic tool-selection hierarchies that minimize token waste
- How to coordinate parallel sub-agents with self-contained worker prompts
- How to classify and gate autonomous actions with composable allow/deny rules
- How to manage context windows through structured summarization and token budgets
- How to inoculate against specific model failure modes (verification avoidance, scope creep, context exhaustion)

## What This Project Is Not

This is **not** a copy of any proprietary system prompt. These skills are original documents that encode best practices distilled from studying how production agentic coding assistants handle common development workflows. The patterns are applicable to any LLM-powered coding environment.

## License

MIT
