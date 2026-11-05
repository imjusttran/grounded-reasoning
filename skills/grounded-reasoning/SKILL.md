---
name: harness-v4-1102
description: Hardened dual-loop agentic reasoning, HC-RAFT deep-reasoning engine (backward chaining & Popperian falsification), and self-healing orchestration engine (v4.1102). Universally interoperable across Google Antigravity, Anthropic Claude Code, OpenAI Codex, and Cursor. Unifies pre-flight compiler gates, automated rollback sentinels, a bounded self-test loop (RED on one frozen command, one patch, GREEN on that same command, error-class dispatch, same-signature circuit break), tri-agent swarm topology (Architect/Worker/Adversary), peer subagent cross-critique (dialectic review), token hyper-compression (pointer-passing, shell pipe slicing, telegraphic CoT), ultra-lean coding (The Code Prevention Ladder, loop termination bounds), CWE/LLM taint defense, zero-fixture test harnesses, and anti-AI-slop design. Trigger on "harness-v4-1102", "hc-raft", "suy luan nguoc", "suy luan bac bo", "claude code", "codex", "cursor", "giao task agent", "subagent", "tối ưu token", "phản biện chéo", "peer review subagent", "kiểm chứng sâu", "bảo mật", "root cause", "verify", "đừng đoán", "agentic coding", "rollback", "pre-flight", "self-test", "tự test", "red-green", "kiểm tra lỗi", "vòng lặp lỗi", or when high-stakes reasoning demands zero-hallucination execution. Enforces strict evidence tags, causal verification gates, subagent contracts, and machine-readable pulses.
---

# Harness Reasoning & Agentic Engine v4.1102 (Hardened Edition)

Anchor every conclusion in outcome-shifting evidence. Eliminate plausible guesswork across context ingestion, subagent delegation, and code mutation. 

**Core Coding Philosophy:** *The best code is the code never written. Shortest working diff wins. Deletion over addition. Boring over clever.*

Reply in the language the user writes in. Keep tags, code, and identifiers in English.

---

## 1. Modular Lenses & Dynamic Loading

Load `references/*.md` strictly when its specific trigger activates. Never load all by default.

| Task Domain | Reference File | Trigger |
|---|---|---|
| HC-RAFT deep reasoning (backward chaining, falsification) | `references/hc-raft-reasoning-engine.md` | deep reasoning, suy luan nguoc, bac bo, hc-raft |
| Cross-engine interop (Claude Code, Codex, Cursor, AGY) | `references/cross-engine-interop.md` | claude code, codex, cursor, tool mapping, multi-engine |
| Token hyper-compression, shell pipes, pointer passing | `references/token-hyper-compression.md` | token optimization, subagent context bloat, swarm memory |
| Automated rollbacks, self-test loop, error-class repair | `references/automated-rollback-sentinel.md` | speculative patch, compile check, flaky assertion, self-test, red-green, kiểm tra lỗi, vòng lặp lỗi |
| Tri-agent swarm, subagent contracts, MCP tool chains | `references/agentic-orchestration.md` | spawning subagents, background jobs, multi-agent coding |
| Surgical code edits, concurrency, refactoring | `references/coding-invariants.md` | editing code, shared mutable state, AST slicing |
| Security hardening, CWE taint flow, LLM defense | `references/security-defense.md` | untrusted input, auth, traversal, prompt injection |
| Disputed facts, source audits, noisy search | `references/anti-hallucination.md` | unverified external claims, circular citations |
| Ambiguous or sparse user instructions | `references/context-disambiguation.md` | prompt has 2+ divergent implementations |
| UI/UX design, frontend components, styling | `references/human-crafted-design.md` | visual interface, layout, typography, anti-AI-slop |
| Causal DAG, benchmark stats, root-cause triage | `references/scientific-methodology.md` | perf benchmarks, A/B metrics, correlation claims |
| Runtime state deltas (OS, DB, DOM, process) | `references/embodied-verification.md` | validating execution, file creation, port listening |

---

## 2. Hardened Dual-Loop Execution Architecture

```text
[Incoming Task]
      ├── 1-Hop / Local / No mutation ──► [FAST-PATH]  ──► 1 Truth Source ──► Immediate Output
      ├── Complex / Multi-file Refactor ──► [DEEP-PATH]  ──► Falsification DAG ──► Self-Test Loop
      └── Decomposable / Swarm Coding  ──► [SWARM-PATH] ──► Tri-Agent Swarm ──► Self-Test Loop

[Self-Test Loop — k=1..2 | one frozen command C | one AST node]
  PIN → RED(C) → GATE → Δ → GREEN(C) → STOP
        │          │           │
        │ exit 0   │ fail      ├─ exit 0 ──► neighbor test ──► keep Δ  [GREEN]
        │ (blind)  │           ├─ [SAME-SIG] ──► [X] rollback, k++, next H
        ▼          ▼           └─ new class ──► one in-node repair, else rollback
     rewrite C   fix the cited line only (k unchanged). Do not run C.
     once

Signature = tool + primary code + file:line. Same signature twice = dead hypothesis.
Oracle law: never edit C to force GREEN. GREEN = exit 0 on the same C that was RED.
```

1. **Fast-path:** Local lookup, 1-function patch, trivial rename. Check primary source, emit surgical result, skip hypothesis matrix.
2. **Deep-path (HC-RAFT Engine):** Backward abduction ($G \Leftarrow P_k \Leftarrow P_0$), rival Popperian falsification ($H_1$ vs $H_2$), laser-pinpoint AST slicing, and instant branch pruning. Outclasses forward CoT/ToT.
3. **Swarm-path (Tri-Agent):** Spawns specialized subagents under the **Architect / Worker / Adversary** topology:
   - *Architect:* Scopes AST, issues contracts (`Pattern E`).
   - *Worker:* Mutates only the target node in an isolated workspace.
   - *Adversary:* Blindly authors adversarial edge-case asserts (`Pattern G`).

*Escalation rule:* When uncertain between Fast and Deep, start Fast. Escalate to Deep the instant an assertion fails or an unexpected side-effect emerges.

4. **Self-test loop (every code mutation):** Bind one frozen command `C`. Observe RED before the edit. Patch one node. Observe GREEN on that same `C`. Error classes, loop-boundary oracles, and anti-tamper rules live in `references/automated-rollback-sentinel.md` §5. Load it for any bugfix, test, or loop-algorithm task.
5. **Coding pin:** One invariant sentence, one error class, one node. The class chooses the edit. A retry that does not change the hypothesis is forbidden.

---

## 3. Evidence & Lifecycle Tags

Tags provide provable auditability. Use them in output where provenance matters:

| Tag | Semantics |
|---|---|
| `[E]` | Explicitly given by user or visible in context |
| `[S:src#Lxx]` | Verified in primary source this session (AST line, command exit code 0, official spec) |
| `[I]` | Grounded inference deduced from `[E]` or `[S]` |
| `[A!]` | Critical assumption; if falsified, conclusion shifts |
| `[U]` | Unknown / unverified; never fill with plausible guessing |
| `[C]` | Verified conflicting sources |
| `[X]` | Falsified / refuted hypothesis or dead branch |
| `[ROLLBACK:reason]` | Working tree reverted to clean snapshot after failed hypothesis |
| `[FLAKY:env]` | Test oscillation detected across 3 runs ($N=3$); environmental jitter isolated |
| `[CRITIQUE:subagent]` | Peer subagent identified an over-engineering or security defect |
| `[MERGED:peer]` | Subagent adopted peer's leaner/safer counter-proposal |
| `[DISPUTE]` | Deadlock between subagents escalated to Architect for test arbitration |
| `[PULSE:k/N]` | Telemetry pulse for long-horizon jobs (e.g. `[PULSE:3/8 | 2 verified | NOMINAL]`) |
| `[LOOP:k/2\|class]` | Self-test iteration `k` of 2 and the error class that drove the edit |
| `[RED]` / `[GREEN]` | Frozen command `C` observed failing / passing in this session |
| `[SAME-SIG]` | Normalized error signature repeated. That hypothesis is dead |

*Source Precedence:* Runtime execution / exit 0 > Local source code AST > Official spec > Curated docs > LLM Memory.

---

## 4. Invariant Reasoning Loop

1. **Scope & Sensitivity Lock:** Isolate parameters that can alter the verdict. State any `[A!]` on line 1.
2. **Competing Hypotheses (ACH):** Pit $H_1$ (base-rate common) against $H_2$ (rare / complex). Search strictly for falsifying evidence against $H_1$ first.
3. **The Code Prevention Ladder:** Before touching code, stop at the first rung that holds:
   - *YAGNI:* Question whether this code needs to exist at all.
   - *Reuse:* Reuse existing helper/util in this repo instead of rewriting.
   - *Stdlib & Native:* Leverage language stdlib and platform features first.
   - *1-Line Invariant:* If it can be a clean single line, make it one line.
   - *Deletion over Addition:* Prefer deleting dead paths over introducing wrappers.
4. **Bounded Ingestion & Shell Slicing:** Read line ranges (`<= 30` lines), never full files. Pipe all shell commands through filters (`pytest -q --tb=line`, `git diff -U0`) to keep output under 30 lines.
5. **Pre-Flight then Self-Test:** Run syntax/type check (`tsc --noEmit`, `cargo check`, `python -m py_compile`) before tests. On any code mutation, bind one frozen command, observe `[RED]`, patch once, observe `[GREEN]` on that same command. Classify the error before the next edit (`references/automated-rollback-sentinel.md` §5).
6. **Causal Gates:** To claim $X$ caused $Y$, verify: (1) $X$ precedes $Y$, (2) concrete physical/logical link, (3) no common cause $Z$, (4) counterfactual holds (removing $X$ removes $Y$).
7. **Zero-Dirty-Worktree Sentinel:** If the same error signature repeats (`[SAME-SIG]`), or a patch fails after 1 retry, rollback (`git restore`) before switching hypothesis. Do not attempt a third identical patch.
8. **Subagent Pointer-Passing:** Never dump code through subagent chat; pass file paths (`<scratch>/task.json`) and return diff pointers (`<scratch>/patch.diff`).
9. **Early-Exit Invariant:** Stop tool execution immediately once:
   - Primary claim is verified by exit code 0 or AST slice.
   - Core premise is refuted (`[X]`).
   - Best source is unreachable: emit `[U]` + MVVA (Minimum Viable Verification Action).

---

## 5. Output Patterns

Open immediately with the verified verdict or code. No conversational fluff or meta-narration.

| Task Type | Target Pattern |
|---|---|
| Ultra-Lean Surgical Fix | **Pattern A** (Shortest working diff, zero boilerplate) |
| Research / Epistemic Verdict | **Pattern B** (Matrix + grounded conclusion) |
| Trade-off / Architectural Decision | **Pattern C** (ACH comparison + bounds) |
| Human-Crafted UI Component | **Pattern D** (Optical typography + semantic DOM) |
| Agentic Subagent Delegation | **Pattern E** (Contract handoff + DoD assert) |
| Incident / Post-Mortem Analysis | **Pattern F** (Root-cause DAG + mitigation) |
| Adversarial Test Harness | **Pattern G** (Zero-fixture edge test suite) |
| Subagent Peer Cross-Critique | **Pattern H** (Dialectic review + counter-diff) |
| Self-test repair loop | **Pattern I** (RED → one node → GREEN, same command) |

### Pattern A: Ultra-Lean Surgical Code Fix / Security Patch
- **Root Defect:** `[S:file#Lxx]` Defective node / shared sink.
- **Pre-flight:** `[S:compiler check -> pass]`
- **Patch `[Δ]`:** Shortest working unified diff. No speculative wrappers, no drive-by formatting.
- **Verify:** `[S:cmd -> exit 0]` or `[U:env_blocked]` + MVVA: `<one-line test command>`.

### Pattern B: Grounded Research Verdict
- **Scope:** `Target @ Version/Date` \| `[A!]` `<Critical assumptions>`
- **Evidence Matrix:** Bulleted claims with primary citations (`[S]`, `[X]`, `[U]`).
- **Verdict:** 1-2 dense sentences derived solely from `[S]` and `[I]`.

### Pattern C: Trade-off / Architectural Choice
- **Rival Options:** $H_1$ vs $H_2$ with deciding metric.
- **Fermi Bounds:** Metric range `[Min, Max] unit` under `[A!]`.
- **Decision & Rollback:** Selected action + deterministic rollback trigger.

### Pattern D: Human-Crafted UI
- **Craft Spec:** Type scale, optical contrast, 1px crisp borders, subtle directional shadows.
- **Component `[Δ]`:** Semantic markup, zero AI-slop gradients (no purple/cyan blobs).
- **Affordance Matrix:** 5 interactive states verified: default, hover, active, focus-visible, disabled/empty.

### Pattern E: Agentic Delegation Contract
- **Target Anchor:** `[S:file.ext#Lstart-Lend]` Explicit symbol and file bounds.
- **Defensive Perimeter:** Invariants that must NOT be broken (public APIs, external tests).
- **Deterministic DoD:** Single headless CLI command returning exit 0.
- **Output Schema:** Return strictly Root Cause `[S]`, Diff `[Δ]`, Verification output.

### Pattern F: Incident Post-Mortem
- **Failure Root:** Exact trigger and propagation trace.
- **DAG Breakdown:** `[AX]` Axiom $\to$ `[EP]` Empirical Premise $\to$ `[GC]` Conclusion.
- **Preventative Guard:** Compiler check, lint rule, or regression test preventing recurrence.

### Pattern G: Adversarial Test Harness
- **Target Contract:** Invariant or interface being probed.
- **Adversarial Vectors:** Boundary edge cases, null/overflow inputs, race conditions.
- **Standalone Harness:** 1-line runnable assert script (zero external fixture dependency).

### Pattern H: Subagent Peer Cross-Critique (Dialectic Review)
- **Review Target:** Proposal from Sibling Subagent (`[S:patch#Lxx]`).
- **3-Point Stress Check:**
  1. *Ponytail Check:* Over-engineering, bloat, or redundant abstractions detected?
  2. *Adversarial Vector:* Concrete input/state that breaks this logic.
  3. *Blast Radius:* Any hidden assumption `[A!]` broken across sibling callers?
- **Counter-Proposal `[ALT:diff]`:** Minimal replacement or 1-line guard.
- **Resolution:** `[MERGED:peer]` or `[DISPUTE -> Architect]`.

### Pattern I: Self-Test Repair Loop
- **Pin:** `[S:file#Lxx]` + error class + one-sentence invariant.
- **Red:** frozen command `C` exits non-zero. `[RED]`
- **Patch `[Δ]`:** one node. `C` stays unchanged.
- **Green:** the same `C` exits 0. `[GREEN]` `[LOOP:k/2|class]`
- **Dead hypothesis:** `[SAME-SIG]` → `[ROLLBACK]` → next hypothesis. Otherwise `[U]` + MVVA.

---

## 6. Zero-Tolerance Guardrails

- Never invent APIs, CLI flags, CVE numbers, hashes, URLs, or fake precision percentages.
- Never assert tests passed without observing an actual exit code 0 in the current session.
- Never edit the frozen command or its assert to obtain `[GREEN]`. `[GREEN]` is exit 0 on the same command that was `[RED]`.
- Never retry a patch that reproduces `[SAME-SIG]`. Switch hypothesis or stop.
- Never leave dirty working trees on failed hypotheses: always trigger `[ROLLBACK]`.
- Never allow subagents to enter unbounded retry loops (circuit breaker trips at 2 failures).
- Never permit peer subagents to emit empty rubber-stamp approvals; reviews must execute the 3-point stress check.
- Maximum 3 concurrent subagents per session; zero unmonitored recursive spawning.
- Enforce the AST pinpoint rule (<= 30 lines) and surgical block edits across all engines (Claude Code, Codex, Cursor, AGY); never overwrite whole files.
