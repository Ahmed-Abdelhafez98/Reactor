# Reactor — AI Agent Execution Service

**A Python-based AI agent using LangChain and Ollama for local LLM-powered reasoning and tool execution.**

This project provides a structured foundation for building an **AI agent that can reason, decide, and act** using the ReAct (Reasoning + Acting) pattern. The agent processes user inputs, determines appropriate actions, invokes tools when needed, and returns results through a controlled and extensible execution flow.

The goal of this project is to support **clear agent execution logic**, extensibility, and practical experimentation with LLM-powered agents.

---

## What the Agent Can Do

- Accept user prompts and process them through an agent execution loop  
- Perform step-by-step reasoning using the ReAct pattern  
- Invoke external tools or functions based on agent decisions  
- Integrate with a local LLM via **Ollama**  
- Support extensible tool definitions for different use cases  
- Run locally through a command-line interface (CLI)  

---

## Tech Stack

- **Python 3.11+**
- **LangChain** (agent patterns and orchestration)
- **Ollama** (local LLM inference)
- Modular agent and tool-based architecture

---

## Installation & Setup

### 1) Clone the repository
```bash
git clone https://github.com/Ahmed-Abdelhafez98/Reactor.git
cd Reactor
````

### 2) Create a virtual environment and install dependencies

```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
pip install --upgrade pip
pip install -e ".[dev]"
```

### 3) Configure environment variables

Create a `.env` file in the project root:

```env
OLLAMA_BASE_URL=http://localhost:11434
OLLAMA_MODEL=llama3.1:8b
```

Ensure **Ollama** is installed and running locally.

---

## Project Structure

```
src/langchain_agent/
  config.py              # Environment and configuration
  agent/
    planner.py           # Agent reasoning and execution loop
    tools/               # Tool definitions used by the agent
  cli.py                 # Command-line interface
tests/
```

---

## Running the Agent

```bash
make run
# or
langchain-agent --version
```

The CLI acts as the entry point for interacting with the agent and validating the execution flow.

---

## Extending the Agent

* Add new tools under `agent/tools/`
* Register tools inside the agent planner
* Extend the planner logic to support richer reasoning and control flows
* Configure or swap LLM models via Ollama

The architecture is designed to evolve without tightly coupling tools, models, or execution logic.

---

## Resources

* LangChain Documentation: [https://python.langchain.com/](https://python.langchain.com/)
* Ollama Documentation: [https://ollama.ai/](https://ollama.ai/)
* ReAct Paper: [https://arxiv.org/abs/2210.03629](https://arxiv.org/abs/2210.03629)
