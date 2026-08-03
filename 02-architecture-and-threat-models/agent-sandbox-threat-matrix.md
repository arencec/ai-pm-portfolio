# Agent Sandbox & Trust Boundary Threat Matrix

When architecting autonomous agent platforms, traditional API security models fall short because LLMs interpret untrusted data as instructions (prompt injection). Below is the core threat matrix utilized to evaluate trust boundaries and failure modes in agentic control planes.

| Threat Vector | Component Affected | Risk Level | Mitigation Strategy |
|---|---|---|---|
| **Indirect Prompt Injection** | 3P Tool-Use / RAG Retrieval | High | Isolate retrieved external data into sandboxed context windows; enforce strict instruction-data separation. |
| **Privilege Escalation** | Task-Level Credentials | Critical | Implement scoped, ephemeral tokens bound to explicit task IDs rather than broad user sessions. |
| **Data Exfiltration via Tool Chaining** | Multi-Agent Orchestration | High | Require explicit user confirmation checkpoints for high-risk outbound network or write operations. |
| **Denial of Service (Infinite Loops)** | Agent Execution Engine | Medium | Set hard execution step-limits and token budgets per task session. |
