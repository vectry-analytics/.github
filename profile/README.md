Vectry Analytics
======

**Causal Data Infrastructure Layer for structured event modeling and tracing — enabling explainable, queryable, and AI-native systems.**

* * *

What is Vectry?
------------------

**Vectry is a Causal Data Infrastructure Layer** — a platform designed to capture, structure, and connect raw events across systems, services, and actors using causal relationships.
Unlike traditional observability or analytics tools, Vectry focuses on _why_ something happened — not just _what_ or _when_.
It introduces traceable primitives like `Event`, `Trace`, `CausalThread`, and `EventExplanation`, allowing you to reconstruct decision flows, audit processes, and power AI models with context-rich event histories.
Vectry is queryable, auditable, and AI-ready. It's not a dashboard. It's a data layer for understanding cause, consequence, and complexity across distributed systems.

* * *

Why this matters
-------------------

Modern systems are distributed, asynchronous, and often driven by complex flows involving human decisions, automation, and AI.
Yet most teams are still debugging failures, inconsistencies, or decisions by mentally reconstructing what happened — across multiple logs, systems, and microservices.
**Vectry introduces causal semantics into the data layer**:
*   Making relationships between actions explicit (cause-effect, trigger-response)
    
*   Structuring events in a graph-like topology that can be traversed, queried, and explained
    
*   Supporting real-time and historical reconstruction of what happened, by whom, and why
    
This model has deep roots in scientific and data principles:
*   Inspired by **causal inference** in statistics, where understanding relationships matters more than correlation
    
*   Aligns with **provenance theory** in data governance, where knowing the origin of a decision or state is essential
    
*   Provides a foundation for **explainable AI (XAI)**, which requires contextual understanding of how inputs and outputs evolve over time
    

### Why Causal Graphs Matter

In Vectry, events are not isolated records — they form a **causal graph**: a directed acyclic graph (DAG) where nodes represent individual events and edges represent causal relationships (e.g., "this event caused that one").
This structure allows systems and AI models to **understand sequences of events with semantic meaning**, and opens the door to automation, explanation, and root-cause analysis across complex environments.

#### What is a causal graph?

A causal graph is a formal structure used in statistics and machine learning to represent how different variables (or events) influence one another. In Vectry:
*   Each **event** is a node.
    
*   Each **caused_by** or **triggered_by** relationship is a directed edge.
    
*   A **trace** becomes a linear sub-path in this graph.
    
*   A **causal thread** is a larger connected component grouping multiple traces across systems.
    

#### Why it matters for AI

For machine learning models — especially in explainable AI (XAI), reinforcement learning, or anomaly detection — understanding the causal history of a decision or outcome is essential.
*   Instead of static feature vectors, models can learn from **sequences of causally linked actions**.
    
*   Explanations (via `EventExplanation`) can be generated **from subgraphs**, identifying the minimal set of contributing events.
    
*   Anomalies are no longer detected in isolation — they are analyzed **within their causal context**, improving accuracy.
    

#### How Vectry enables this

*   Vectry provides an **API-friendly representation** of the causal graph (via `event`, `trace`, and `causal_thread` entities).
    
*   AI engines (like **Sommatic**) can traverse these graphs and:
    *   Autonomously generate `EventExplanation` entities
        
    *   Propose `CausalThreads` where none were explicitly declared
        
    *   Detect pattern deviations and raise `Anomaly` entities
        
This causal structure allows machines to explain themselves, compare behaviors across systems, and become collaborators in debugging, auditing, and improving decision-making.
In short, **Vectry is not just a data logger — it's an inference-ready, explainability-first event infrastructure.**
Vectry models the event ecosystem as a **causal graph** — a directed acyclic graph (DAG) where nodes are events and edges represent causal links. This structure is central to enabling:
*   **Causal navigation**: Traversing backward and forward through chains of causality, across microservices, users, or subsystems.
    
*   **Graph-based reasoning**: AI models can operate not just on event lists, but on structured causal chains — enhancing interpretability and learning.
    
*   **Multi-actor attribution**: Identifying how human actions, automated triggers, and system policies jointly led to an outcome.
    
*   **Precision debugging**: Instead of filtering logs, teams can inspect subgraphs of interest (e.g. all events that caused a payment failure).
    
This isn't just useful for observability — it's foundational for building systems where accountability, fairness, and reliability are critical.

* * *

### Scientific and Technical Benefits

*   **Improves root-cause accuracy** by linking events across domains (UI, backend, external systems)
    
*   **Enables time-aware pattern recognition** via structured sequences (`Trace`) and lifecycles (`CausalThread`)
    
*   **Bridges operational and analytical worlds** — capturing operational telemetry that's directly usable for analytical and ML/AI use cases
    
*   **Prepares data for AI reasoning** without complex feature engineering or fragmented pipelines
    

### Comparison to Existing Tools

| Feature | Vectry | Traditional Observability | Event Analytics (e.g. Mixpanel) | Data Warehouses |
| --- | --- | --- | --- | --- |
| Focus | Causality & Explainability | Errors, logs, metrics | Funnels, user behavior | Historical snapshots |
| Cross-system flow linking | ✅ Native via `Trace` & `CausalThread` | ⚠️ Manual or span-limited | ❌ Unrelated events | ❌ Not event-driven |
| Queryable for AI | ✅ Yes, graph and context-rich | ❌ Limited | ❌ Very limited context | ⚠️ Requires ETL |
| Root-cause modeling | ✅ Built-in | ❌ Often manual | ❌ Not supported | ⚠️ Only via BI logic |
| Event explanation support | ✅ `EventExplanation` entity | ❌ No | ❌ No | ❌ No |
| Temporal causality tracking | ✅ First-class support | ⚠️ Partial (traces only) | ❌ No | ❌ No |

* * *

Core Primitives
------------------

*   **Event** – A single action, state change or signal in the system.
    
*   **Trace** – A sequence of related events that represent a logical execution flow.
    
*   **CausalThread** – A group of traces that span across systems but relate to a common purpose or outcome.
    
*   **EventExplanation** – A human-readable or AI-generated explanation describing the causal path leading to a specific event.
    
*   **Anomaly** – A detected deviation from an expected pattern, potentially linked to explanations or outcomes.
    

* * *

Packages
-----------

*   `vectry-js` – Core JavaScript SDK for capturing events across web and server apps
    
*   `vectry-node` – Node.js SDK focused on backend and service instrumentation
    
*   `vectry-react` – Thin React layer for client-side integrations
    

> More libraries and integrations coming soon.

* * *

Status
---------

Vectry is under active development and currently in private preview.
If you're building distributed systems, explainable AI, or high-integrity workflows — we'd love to hear from you.

* * *

📫 Contact & Community
----------------------

Coming soon.
