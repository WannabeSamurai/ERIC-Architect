# ERIC

**Execution, Reasoning, Integration, and Control**

ERIC is a local-first intelligence and control architecture built around replaceable language models rather than around any single model or chatbot.

The model is not the system. ERIC supplies the surrounding structure: persistent identity and state, evidence-aware routing, durable memory and retrieval, governed execution, verification, recovery, diagnostics, first-party interfaces, and controlled development workflows.

**Public status snapshot:** October 5, 2026

This repository is the deliberately sanitized public architecture surface for the private ERIC engineering project. It documents what ERIC is, what has been demonstrated, and where evidence is still incomplete. It does **not** publish the private production source tree, credentials, operator data, machine-specific control details, private development state, or runtime secrets.

## October 8, 2026 — Rebuild Progress (Local Evidence)

The operator's latest private engineering synchronization bundle reports three subsequent local milestones. **These are locally reported production results, not an assertion that the private GitHub remote has been synchronized to the same deployment commits.** This public page intentionally omits machine-specific configuration, private source, and operational artifacts.

- **NOW-1 — Local model environment:** model-store startup alignment corrected; 28 models reported available versus 14 before correction. Model availability does not establish every model's capability qualification.
- **NOW-2 — Evidence lineage:** evidence-basis and claim-lineage convergence implemented and locally promoted; acceptance evidence includes later successful live scenarios, while earlier test failures/timeouts must not be silently erased.
- **NEXT-1 — Conversational execution:** a bounded execution gate locally deployed with approval-bound state-changing operations and anti-replay protections. The synchronization bundle reports 10/10 production API acceptance scenarios passed. A separate operator browser sequence demonstrated reading a file, proposing a write, approving it, and reading back the result.

**Still unresolved:** ERIC has not demonstrated reliable autonomous multi-step engineering investigation from a broad conversational objective. In a follow-up self-inspection test, it did not visibly choose and run the necessary inspections and made an unsupported claim about missing tools. The root cause—tool exposure, capability discovery, intent recognition, or orchestration—is under investigation. These results do not establish full autonomous self-development.

**Publication boundary:** The private repository's GitHub `main` has not yet been independently confirmed to contain the locally reported deployment commit. The public architecture snapshot must not be mistaken for source-code release or current remote-code certification.

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

The earlier proposed **Evidence-Basis and Claim-Lineage Convergence** work is now reported as locally implemented and deployed under NOW-2. Its production acceptance and GitHub source synchronization remain separately evidenced states. The immediate unresolved development question is why the normal chat path can execute explicit governed operations but has not demonstrated autonomous multi-step tool discovery and orchestration. No repair has been authorized solely by this documentation update.

Repository-wide worker admission and durable external-effect receipts follow as structural safety priorities; expanded concurrent mutation remains gated. New functionality is not treated as accepted merely because it exists in code or documentation.

ERIC remains a private engineering project. This repository is an architecture and review surface, not a downloadable release.

## License

ERIC is proprietary software. Publication of this architecture repository does not grant rights to the private ERIC core or unpublished implementation.
