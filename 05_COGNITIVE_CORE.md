# Block 5: Cognitive Core - Model-Agnostic Intent Translation

This block defines the AI orchestration layer. It translates user intent into system actions and coordinates multi-agent workflows. The layer is defined by its interface, not by a specific model.

---

### 1. Role

| Function | Description |
|---|---|
| Intent parsing | Convert voice, text, or architectural intent into structured actions |
| Tool calling | Emit JSON-structured system commands |
| State tracking | Maintain context across workspace transitions |
| Multi-agent coordination | Route sub-tasks to specialized agents |

---

### 2. Interface Requirements

Any model connected to this layer must satisfy the following.

| Requirement | Specification | Status |
|---|---|---|
| Structured output | JSON schema for tool calls | `[REQUIRED]` |
| Context window | Sufficient for active workspace state | `[REQUIRED]` |
| Latency | < 2 s for first token, interactive use | `[REQUIRED]` |
| Deployment | Local or cloud, interchangeable | `[REQUIRED]` |
| Vendor | None | `[REQUIRED]` |

---

### 3. Deployment Modes

| Mode | Description | Trade-off |
|---|---|---|
| Local | Open-weights model on device NPU/GPU | Privacy, latency, no network dependency |
| Cloud | Remote API | Larger models, higher latency, network dependency |
| Hybrid | Local for routine, cloud for complex | Complexity, routing logic |

The architecture does not prefer one mode. The mode is a configuration parameter.

---

### 4. Intent-to-Action Pipeline
User intent (voice / text)
│
▼
[Intent parser] ──► structured intent object
│
▼
[Policy check] ──► allowed / requires biometric / denied
│
▼
[Tool call generator] ──► JSON action
│
▼
[Sandbox executor]
│
▼
[Result] ──► UI update or next action

text

The policy check is mandatory. The model does not execute directly. It proposes; the Security Gate disposes.

---

### 5. Open Questions

1. Minimum context window for reliable multi-step intent translation is not measured.
2. Latency budget for local vs cloud routing is not defined.
3. Fallback behavior when no model is available is not specified.
4. Multi-agent coordination protocol is not defined.
5. Evaluation benchmark for intent-to-action accuracy does not exist.

---

### 6. Prior Art

| System | Relation |
|---|---|
| OpenInterpreter | NL to code execution, no OS-level isolation |
| Claude Computer Use | General computer control, cloud-only |
| Gemini Agent | Tool calling, vendor-locked |
| Local SLM agents (various) | Local inference, no OS integration |

This block differs from prior work in that it is defined as a **replaceable interface** within an OS, not as a standalone agent.
