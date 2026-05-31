---
name: 591-agent-system
description: |
  591 Agent System (五省九部一院) — A general-purpose problem-solving engine from first principles. 15 Agents across 3 layers (5 provinces for decision/coordination, 9 departments for execution, 1 institute for evolution) with 4 execution modes. Use when the user asks for "/591", mentions "591体系", "五省九部一院", or requests complex multi-step analysis/planning/review/execution that benefits from structured agent delegation.
workflow: |
  1.察省(Perceive): Define problem + success criteria + info gaps
  2.策省(Strategize): Generate ≥3 solution paths + assumption matrix
  3.谏省(Critique): Adversarial review — target ≥50% rejection rate
  4.协省(Orchestrate): Decompose → route to 9 departments → track
  5.九部(Execute): Domain-specific execution (parallel where possible)
  6.验省(Verify): Compare results vs success criteria → root cause
  7.进院(Evolve): Performance tracking + knowledge crystallization
enabled: true
---

# 591 Agent System (五省九部一院)

**Type:** Capability — general-purpose problem-solving engine

## Overview

591 is a domain-agnostic agent system that decomposes any problem into 7 irreducible functions, mapped to 15 AI agents organized in 3 layers.

## Architecture

```
天子(Human) → 察省 → 策省 → 谏省 → 协省 → 九部(并行) → 验省 → 协省交付 → 天子
                                                              ↓
                                                           进院(后台进化)
```

### Agent Inventory (15)

| # | Agent | Layer | Role |
|---|-------|-------|------|
| 1 | 察省 | Perception | Define problem + success criteria |
| 2 | 策省 | Strategy | Generate ≥3 solution paths |
| 3 | 谏省 | Critique | Adversarial review (≥50% rejection target) |
| 4 | 协省 | Orchestration | Decompose, route, track, deliver |
| 5 | 验省 | Verification | Compare results vs success criteria |
| 6-14 | 九部 | Execution | 兵/吏/礼/户/刑/工/学/医/创 — 9 domain departments |
| 15 | 进院 | Evolution | Performance tracking + knowledge crystallization |

### Execution Modes

| Mode | Trigger | Skips | Use Case |
|------|---------|-------|----------|
| 标准 (Standard) | `/591` | None | Medium-high complexity |
| 极速 (Fast) | `极速` | 谏省+验省 | Low risk, familiar tasks |
| 严审 (Strict) | `严审` | None + forced rejection | High risk, high impact |
| 诊断 (Diagnose) | `诊断` | — + 医部优先 | Bug/failure diagnosis |

## How to Use

When invoked, Claude Code should:

1. **Load the system**: Read `CLAUDE.md` (master loader in this directory)
2. **Follow the pipeline**: Each phase loads the corresponding agent prompt from `五省/` or `九部/` or `进院/`
3. **Role-switch explicitly**: Mark each phase transition with `━━━ 阶段X: [Agent名] ━━━`
4. **Use agent output formats**: Each agent's `.md` file specifies exact output structures
5. **Obey separation principles**: Generator ≠ Critic, Executor ≠ Verifier

### Agent file locations (relative to this directory)

- 五省 (5 Provinces): `五省/察省.md`, `五省/策省.md`, `五省/谏省.md`, `五省/协省.md`, `五省/验省.md`
- 九部 (9 Departments): `九部/兵部.md` through `九部/创部.md`
- 进院 (Institute): `进院/进院.md`
- Main loader: `CLAUDE.md`

### Task routing

Single-domain tasks → route to the matching 部. Composite tasks → main 部 + collaborating 部. See `CLAUDE.md` Section 3 for the complete routing table.

## First Principles

```
问题 = S_curr → S_desired 的未知路径

Any problem is a transition from current state to desired state.
Solving it requires 7 irreducible functions:
Perceive → Generate → Critique → Coordinate → Execute → Verify → Evolve
```

## Core Principles (Non-negotiable)

1. **Generator ≠ Critic** (策省 and 谏省 must be separate)
2. **Executor ≠ Verifier** (九部 and 验省 must be separate)
3. **Single owner** per task (collaboration allowed, accountability singular)
4. **Evidence chain** (all judgments must have verifiable basis)
5. **3-round max** for revision cycles (then escalate to 协省)

## Docs

- `docs/MIGRATION.md` — Version migration guide
- `docs/CROSS_DEPARTMENT_BOUNDARIES.md` — Department overlap resolution
- `docs/HONEST_CAPABILITY_BOUNDARIES.md` — Honest assessment of limits
- `CHANGELOG.md` — Version history

## Related

- GitHub: https://github.com/weitzu-com/591-agent-system
- cloudflare-optimizer: https://github.com/weitzu-com/cloudflare-optimizer (591-based Cloudflare optimization skill)
