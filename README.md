# Agent_SDK_Langchain
Agent_SDK_Langchain
---

## 🎯 Objective

Build a **multi-agent conversational system** using **LangChain**, simulating how ChatGPT agents work:

✅ Quickly respond to simple queries.
🧠 Delegate complex queries to a more intelligent supervisor agent.
🛠️ Call external tools (e.g., search, calculator) when needed.

---

## 🔁 Interaction Flow

```mermaid
sequenceDiagram
    participant User
    participant LangChainAgent as Chat Agent (LangChain)
    participant Supervisor as Supervisor Agent
    participant Tool as Tool

    alt Simple message
        User->>LangChainAgent: Send message
        LangChainAgent->>User: Respond immediately
    else Complex message
        User->>LangChainAgent: Send message
        LangChainAgent->>Supervisor: Forward context
        alt Tool required
            Supervisor->>Tool: Call tool
            Tool->>Supervisor: Return result
        end
        Supervisor->>LangChainAgent: Return answer
        LangChainAgent->>User: Deliver final response
    end
```

---

## 🧩 Components

| Agent             | Role                                               |
| ----------------- | -------------------------------------------------- |
| `ChatAgent`       | Handles simple conversational queries              |
| `SupervisorAgent` | Evaluates query complexity and delegates if needed |
| `Tool`            | Functions/plugins like WebSearch, Calculator, etc. |

---
