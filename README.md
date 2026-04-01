# The Complete Agent & MCP Course

Personal learning repository for the Udemy course **"AI Engineer Agentic Track: The Complete Agent & MCP Course"** by Edward Donner.

**Course repo:** [github.com/ed-donner/agents](https://github.com/ed-donner/agents)

---

## Overview

A 6-week hands-on course covering autonomous AI agent development across multiple frameworks:

| Week | Topic |
|------|-------|
| 1 | Foundations & Agents SDK |
| 2 | n8n & Workflow Automation |
| 3 | CrewAI |
| 4 | LangGraph |
| 5 | AutoGen |
| 6 | MCP (Model Context Protocol) |

> All LLM inference is handled locally via **Ollama** - no cloud API keys required.

---

## Setup

### Prerequisites

- Python 3.12
- Docker Desktop

### Python environment

```bash
python -m venv venv
source venv/Scripts/activate  # Windows
pip install -r requirements.txt
```

---

## n8n + Ollama

Local workflow automation with n8n and a local LLM via Ollama.

```bash
# Start services
docker compose up -d

# Pull the Ollama model
docker exec -i ollama ollama pull llama3.2:1b
docker exec -i ollama ollama pull deepseek-r1:1.5b
docker exec -i ollama ollama pull qwen3.5:0.8b
```

Then open [http://localhost:5678](http://localhost:5678), set up an account, and import workflows:

```bash
docker exec -i n8n n8n import:workflow --separate --input=//workflows
```

In the Ollama Chat Model node, set the credential URL to `http://ollama:11434`.

---

