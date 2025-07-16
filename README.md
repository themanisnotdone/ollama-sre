# 🧠 ollama-sre

A structured instructional for running and customizing local large language models (LLMs) using [Ollama](https://ollama.com/) on macOS with M-series silicon.

This project is built for developers, SREs, and engineers who want **full control over their local AI stack**—from installation to prompt design to persistent custom personas.

---

## 🔧 Requirements

- macOS (M1, M2, or later recommended)
- [Homebrew](https://brew.sh/)
- Terminal familiarity (zsh or bash)
- ~10GB free disk space per model

---

## 🚀 Getting Started

### 1. Install Homebrew (if not already)

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

## 📂 Repo Structure
```ai-local-llm-setup/
├── setup/ # Installing tools like Ollama or LM Studio
├── workflows/ # How to interact with models
├── advanced/ # GPU tuning, performance, privacy
└── resources/ # Model comparisons, references```

## 🚀 Getting Started

Head to [`setup/ollama.md`](setup/ollama.md) to install your first local LLM interface.

---

## 📜 License

MIT License. Use, modify, and share freely.

---

> This is a work-in-progress. Feedback and pull requests are welcome.

ollama run mistral            # Run Mistral 7B
ollama pull gemma:2b          # Download Gemma 2B model
ollama list                   # List all models downloaded
ollama create mymodel -f Modelfile   # Custom model (advanced)

Modify modelfile

FROM mistral

SYSTEM "You are a poetic AI assistant. Respond in metaphor and rhythm."
PARAMETER temperature 0.8

Build and run:

ollama create poetic-mistral -f advanced/poetic-mistral/Modelfile
ollama run poetic-mistral


