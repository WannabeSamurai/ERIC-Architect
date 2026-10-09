# ERIC

**Execution, Reasoning, Integration, and Control**

ERIC is a local-first intelligence and control architecture built around replaceable language models rather than around any single model or chatbot.

The model is not the system. ERIC supplies the surrounding structure: persistent identity and state, evidence-aware routing, durable memory and retrieval, governed execution, verification, recovery, diagnostics, first-party interfaces, and controlled development workflows.

**Public status snapshot:** October 9, 2026

This repository is the deliberately sanitized public architecture surface for the private ERIC engineering project. It documents what ERIC is, what has been demonstrated, and where evidence is still incomplete. It does **not** publish the private production source tree, credentials, operator data, machine-specific control details, private development state, or runtime secrets.

## October 9, 2026 — Verified Production Architecture & Control-Plane Repair

The private production repository (`WannabeSamurai/ERIC`) has been synchronized and verified on `main` following the completion and live acceptance of the October engineering milestones. This public architecture record reflects the verified structural state:

- **Local Model Serving & Lineage Convergence (NOW-1 & NOW-2):** Canonical model store aligned with local Ollama runtime; IBM Granite 4.2 (`granite4.2:8b`, Q4_K_M, 10.6 GB VRAM, 32k context) established as resident general-purpose model. Evidence lineage tracking distinguishes machine observations from model proposals via structured evidence envelopes (`EvidenceEnvelope`).
- **Conversational Execution Gate (NEXT-1):** Bounded execution gate intercepting tool intent in ordinary chat; enforces explicit operator approval for state-changing operations, SHA-256 parameter tamper protection, TTL expiration, anti-replay, and machine-verified execution receipts.
- **Governed Multi-Step Tool Orchestration:** Resolves the previously open multi-step investigation gap. GovernedToolOrchestrator enables the model to perform bounded multi-step read-only investigations (up to 5 steps, 90s deadline) using allowlisted safe tools (`fs.read_file`, `fs.list_dir`). Consequential operations convert to formal approval proposals.
- **Governed Engineering Execution:** GovernedEngineeringWorkflow enforces a complete engineering repair lifecycle: autonomous inspection → operator proposal → explicit approval → verified mutation → postcondition verification → automated rollback on failure.
- **Behavioral Control-Plane Repair:** Restored operator profile subordinate context injection; eliminated prompt tampering to preserve operator inputs verbatim; repaired dual-key request-trace observability (`trace_id`/`request_id`); enforced conversational discipline without moralizing or rule preamble; decoupled internal Core services from external hardware; challenged destructive deletion constructively while retaining execution gate controls.
- **Full Engineering Regression Coverage:** **86 / 86 PASSED (100% pass rate in 20.53s)** across 9 test suites covering operator profile context, prompt preservation, trace observability, orchestrator, UI API, governed engineering execution, conversational chat API, execution gate, and evidence lineage.
- **Production Baseline:** Active on port 3210 (`overall_state: READY`, `status: ok`). Canonical Behavior Contract v2.2.0 hash-verified and unchanged. Certified rollback procedure tested in an isolated clone with physical receipt preserved.

### Verified Architecture vs Gated Work

- **VERIFIED:** Core operational with `granite4.2:8b`, Evidence authority, Conversational Execution Gate, Governed Tool Orchestration (bounded read inspection), Governed Engineering Execution, Operator Profile context injection, Trace Observability, 86/86 passing tests, and unchanged Canonical Behavior Contract v2.2.0.
- **IN DEVELOPMENT / GATED:** Bounded read-only tools allowlist; development workbench continuity ownership remains task-scoped.
- **PLANNED / PROHIBITED:** General-purpose autonomous self-development without operator gating remains **unaccepted and explicitly prohibited**.


## What ERIC Is

ERIC separates intelligence from authority.

Language models can propose answers, plans, code, and actions. ERIC's architecture determines what evidence is required, which capabilities are actually qualified, what context is authoritative, what execution is permitted, whether an action really succeeded, and how interrupted work resumes.

Core design rule:

> A model may propose. Evidence and governed runtime state decide what ERIC can claim or do.

## Demonstrated Architecture and Capabilities

The private engineering baseline has demonstrated the following classes of capability through implementation and bounded acceptance work:

- **Persistent ERIC Core** with a canonical native dashboard and durable conversation/runtime state.
- **Local-model integration** through Ollama, with capability-oriented routing architecture and evidence tracking.
- **Evidence authority** that distinguishes supplied/local evidence, runtime evidence, current external evidence, and unsupported model claims.
- **Current-external retrieval and claim grounding** with fail-closed behavior when retrieved evidence does not support a generated current-fact claim.
- **Persistent memory and knowledge retrieval**, including structural large-document chunking and a SQLite/FTS5 retrieval store.
- **Governed execution boundaries** that separate model reasoning from authority to perform actions and require observable postconditions for controlled execution.
- **Durable objective execution** with persisted lifecycle state, approval/cancellation paths, and restart-aware continuation.
- **Self-inspection and bounded self-repair architecture** using controlled filesystem authority and isolated repair workspaces rather than unrestricted model access to the host.
- **Native Android integration**, including operator-authorized persistent Storage Access Framework grants and a governed local phone-file bridge into ERIC's evidence pipeline.
- **External development workbench architecture** that separates production runtime from development-agent coordination and preserves evidence about development work. Current continuity ownership is task-scoped; repository-wide worker exclusion remains unresolved.
- **Response-authority hardening** for local-file routing, embedded untrusted instructions, measurable claims, and bounded claim-level repair instead of blindly accepting or discarding an entire generated answer.

## Evidence Discipline

ERIC does not treat the following as equivalent:

- installed;
- configured;
- implemented;
- unit-tested;
- integration-tested;
- observed running;
- accepted in production;
- currently healthy.

A historical passing test does not prove present runtime health. A configured model does not prove that model is currently callable. A model-generated statement does not prove that an external action occurred.

When evidence conflicts, current observable evidence outranks narrative documentation.

## Current Runtime Caveat

ERIC's architecture and substantial portions of its capability surface have been implemented and tested, but the project is **not represented here as universally production-complete**.

Late-September runtime/model incidents remain historical evidence. On October 5, a narrow Core startup, health/readiness checks, and one ordinary chat request passed using a served local model without fallback. Database integrity checks passed and recorded objective/execution states were preserved. This is bounded current operational proof, not a repeat of every capability's acceptance tests.

The accepted historical baseline remains **Python: 1863 passed, 3 skipped; Android: 167 passed**. Neither full suite was rerun. Historical acceptance is retained unless stronger later evidence contradicts it; missing current model inventory does not itself revoke historical qualification. Stage 5 remains **SHADOW / non-authoritative**.

A synthetic normal-path behavioral evaluation ran **15 cases / 18 turns**: **6 clean passes and 9 rubric failures**. Twelve case targets succeeded, but unsupported additions or withheld useful answers prevented clean acceptance in several cases. One pressure case has material test-design ambiguity. These findings are not nine proven implementation bugs, a demonstrated security bypass, or blanket invalidation of earlier accepted work. Evaluation was by the task agent as an operator proxy, not an independent model judge.

The development relay has one proven primary inference path, with remaining request/fallback translation defects. Development-worker reliability and repository-wide admission are separate from Core product runtime authority.

This public repository therefore avoids publishing a single blanket "complete" or "fully operational" claim.

## High-Level Architecture

```text
Operator
   |
   v
ERIC Interfaces
   |
   v
ERIC Core
   |---- Evidence / Context Authority
   |---- Memory / Knowledge Retrieval
   |---- Capability & Model Routing
   |---- Objective Runtime
   |---- Governed Execution
   |---- Verification / Recovery
   |
   +---- Replaceable Local Models
   +---- Authorized Tools / Devices / Services
```

The interfaces and models are replaceable surfaces. ERIC Core is the authority boundary.

## Design Invariants

1. **The model is not ERIC.**
2. **Installation is not qualification.**
3. **Generation is not execution.**
4. **A claimed side effect is not a verified side effect.**
5. **Runtime evidence outranks model consensus.**
6. **Interrupted work must verify existing state before repeating an action.**
7. **Memory and retrieved evidence retain provenance.**
8. **Corrupt, missing, or insufficient authority fails closed rather than being silently promoted to truth.**
9. **Development automation does not automatically inherit production execution authority.**
10. **Current status must be re-established from current evidence.**
11. **Historical acceptance is not revoked merely because it was not retested today.**

## Public / Private Boundary

### Public here

- system purpose and architecture;
- evidence and authority principles;
- sanitized capability descriptions;
- current high-level status;
- contribution path for outside review.

### Private

- production source code;
- credentials and provider secrets;
- operator records and conversations;
- private runtime databases and traces;
- machine-specific paths and security configuration;
- device pairing material;
- development-agent coordination state;
- detailed control-plane implementation that would unnecessarily expose the private host.

## Outside Review and Contributions

Outside review starts with **no access to the private ERIC repository or host**.

A reviewer can inspect this public architecture surface, open an issue with a question or critique, or propose a change to this public repository through a fork and pull request. Access to private implementation, runtime systems, development infrastructure, or write authority is granted separately and only when explicitly authorized.

See [CONTRIBUTING.md](CONTRIBUTING.md).

## Project Direction

With Evidence-Basis and Claim-Lineage Convergence, Conversational Execution Gate, Governed Tool Orchestration, Governed Engineering Execution, and Behavioral Control-Plane Repair now fully promoted and verified, the primary operational focus transitions to:

1. Real-world operator research and controlled domain troubleshooting workflows.
2. Hardening mobile-bridge reliability across long-lived background sessions.
3. Gradual evaluation of Stage 5 capability-based model routing (currently in passive SHADOW observation).

Repository-wide worker admission and durable external-effect receipts remain structural safety priorities; expanded un-gated concurrent mutation remains strictly prohibited. New functionality is not treated as accepted merely because it exists in code or documentation.

ERIC remains a private engineering project. This repository is an architecture and review surface, not a downloadable release.

## License

ERIC is proprietary software. Publication of this architecture repository does not grant rights to the private ERIC core or unpublished implementation.
