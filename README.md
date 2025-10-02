# AgenticAI (Workflow Project)

A collection of **LangGraph**, **LangChain**, and **Groq-powered AI agent demos** exploring different agentic patterns—from simple chatbots to multi-agent orchestration with human-in-the-loop support and MCP-based tool integration.

>  This repository serves as a **playground** to experiment with **agentic architectures** for building autonomous, semi-autonomous, and supervised AI workflows.

---

## 📂 Project Structure


---

## ✨ Key Features

### 1. **Basic Chatbot**
- Simple **stateful chatbot** built with LangGraph and Groq LLM (`llama-3.1-8b-instant`).
- **Tool-calling support** using:
  - Tavily Search (web search).
  - Custom Python function (`multiply`).
- Adds **memory** via `MemorySaver` for multi-turn context persistence.

📂 File: `BasicChatbot/basicchatbot.ipynb`

---

### 2. **Debugging Agents**
- Minimal agent for **tool routing debugging**.
- Integrated with **LangSmith tracing** for visualizing each node and tool call.
- Example tool: `add(a, b)` for predictable, easy-to-test flows.

📂 Files:
- `Debugging/agent.py` – graph factory for reuse.
- `Debugging/debugging.ipynb` – step-by-step debugging notebook.

---

### 3. **Human-in-the-Loop Workflows**
- Demonstrates **pausing an AI workflow** mid-run to request **human input**.
- Use cases:
  - Approvals for sensitive decisions.
  - Escalation to domain experts.
- Supports **interrupt → resume** pattern using `Command(resume=...)`.

📂 File: `HumanAssistance/humaninLoop.ipynb`

---

### 4. **MCP + LangChain Integration**
- Shows how to connect **LangChain agents to MCP services**.
- Two independent MCP services:
  - **Math Service** → add, multiply.
  - **Weather Service** → mock weather endpoint.
- `MultiServerMCPClient` dynamically discovers tools from both services.
- Built-in **ReAct Agent** (`create_react_agent`) powered by Groq.

📂 Files:
- `MCPLangchain/client.py` – integrates both MCP servers.
- `MCPLangchain/mathserver.py` – math operations.
- `MCPLangchain/weather.py` – weather query endpoint.

---

### 5. **Multi-Agent System with Supervisor**
- Fully orchestrated multi-agent workflow with roles:
  - **Researcher** → gathers information using Tavily search.
  - **Analyst** → interprets research and extracts insights.
  - **Writer** → produces a final structured report.
  - **Supervisor** → decides which agent acts next.
- Produces a **final executive report**




