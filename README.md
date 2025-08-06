# 🧠 Code Generation using RAG (Retrieval-Augmented Generation)

This project implements a modular, smart, and interactive code generation pipeline using **Retrieval-Augmented Generation (RAG)** with LLMs. It integrates document embedding, vector retrieval, prompt engineering, LangGraph-based control flows, and performance evaluation using BERTScore and test cases (MBPP).

---

## 🚀 Features

- **Dataset Support**: HumanEval and MBPP datasets for real-world code problems.
- **Embeddings**: High-quality semantic embeddings using `BAAI/bge-large-en-v1.5`.
- **Vector Store**: Fast similarity search using **ChromaDB**.
- **LLM Integration**: Code generation and explanation using `deepseek-chat-v3` from [OpenRouter](https://openrouter.ai).
- **Modular RAG Pipeline**: Supports generation, explanation, and smart routing.
- **LangGraph Workflows**:
  - Manual, tool-based, and automatic flows.
  - Smart task routing using history.
  - Resume support for long conversations.
- **UI Deployment**: Gradio chatbot interface for interaction.
- **Evaluation**:
  - BERTScore for text similarity.
  - MBPP test case execution to assess functional correctness.

---


🧠 RAG Pipeline

The RAG workflow includes:

Prompt Embedding
→ Embed code prompts using BAAI/bge-large-en-v1.5.

Context Retrieval
→ Retrieve relevant samples from ChromaDB.

Code Generation
→ Generate Python code using LLM with retrieved examples as context.

Evaluation
→ Compare generated vs ground truth using:

BERTScore

MBPP test case execution

💡 LangGraph Workflows

Multiple LangGraph structures are implemented:

Structure	Description
Basic	Simple if-else routing with code/explanation
Tool-based	Manual invocation of tools
LLM-based	ChatOpenAI auto-invokes tools using bind_tools
Resume support	Continues conversations using context history
SmartRouter	Determines task (generate / explain / resume) via LLM

Each structure is modular and can be tested independently.

✅ MBPP Functional Testing
Generates Python functions

Executes test cases from MBPP

Detects pass/fail with feedback

💻 Gradio UI

A browser interface will open to chat with the code assistant in natural language.

📊 Smart Routing

The system can:

Identify task from user message

Resume conversations naturally

Support human-AI interleaving

Classify prompts as:

generate code

explain code

resume conversation
