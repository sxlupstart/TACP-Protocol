# TACP Protocol (Temporal Alignment & Causal Tracing Protocol)

> *"Solving Context Drift and Temporal Hallucination in LLMs through Lightweight Metadata."*

## 👤 About the Initiator
I am an **AI Interaction Architect** and the initiator of the TACP Protocol. Through extensive, long-term collaboration with advanced LLMs, I identified systemic bottlenecks in context management. Rather than building another heavy vector database, I designed this **protocol specification and engineering workflow** to solve the "forgetting" problem at the application layer. 

## 📌 The Problem
Large Language Models suffer from three critical flaws in long-context or cross-session scenarios:
1. **Context Drift**: Loss of chronological order in retrieved information.
2. **Temporal Hallucination**: Disconnect between AI's internal logic and real-world time.
3. **Causal Loss**: Inability to trace *why* a specific decision or output was generated.

## 💡 The TACP Solution
TACP is a lightweight, metadata-driven protocol that assigns a unique spatiotemporal coordinate to every critical information node:
- **H-Axis (Heartbeat)**: A monotonically increasing logical clock (e.g., `HB-YYYYMMDD-HHMM`) ensuring irreversible chronological order.
- **C-Axis (Carbon Anchor)**: Mandatory physical-world timestamp injection (e.g., UTC+8) to prevent logical time loops.
- **Δ-Axis (Delta)**: Explicit causal linking (Inherit/Refute/Refine) between nodes, transforming implicit chains of thought into a traceable Directed Acyclic Graph (DAG).

## 📂 Documentation
- 📜 [01_Living_3D_Timeline.md](./Whitepaper/01_Living_3D_Timeline.md) - Engineering practice for causal memory management.
- 📜 [02_Causal_Knowledge_Graph.md](./Whitepaper/02_Causal_Knowledge_Graph.md) - Blueprint for self-organizing AI knowledge bases.
- ⚙️ [TACP Protocol Specification](./Specification/TACP_Protocol_Specification.md) - Technical details and validation rules.

## 🚀 Quick Start
Check out [Examples/prompt_template.md](./Examples/prompt_template.md) to learn how to inject the TACP metadata header into your AI clients (Cursor, Cherry Studio, etc.) in seconds.

## 🤝 Call for Collaboration
This is an open protocol. We welcome developers, researchers, and AI enthusiasts to:
- Build plugins or SDKs based on the TACP Specification.
- Share your use cases and contribute to the evolution of this protocol.

---
*© 2026 Dunjun. Licensed under MIT.*
