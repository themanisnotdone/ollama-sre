# ⚙️ Setting Up Ollama for Local LLMs

This guide walks you through installing **Ollama**, a powerful CLI/API tool for running open-source LLMs like LLaMA2, Mistral, and Gemma entirely on your local machine.

> 🧠 **Why Ollama?**  
> Simple CLI and API, no cloud dependency, active development, and easy model management. Ideal for reproducible, scriptable workflows.

---

## 🪛 1. Recommended Install via Homebrew (macOS)

> ✅ Best for Apple Silicon (M1/M2/M3) or Intel Mac users

### Step 1: Install Homebrew

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

echo >> ~/.bash_profile
echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> ~/.bash_profile
eval "$(/opt/homebrew/bin/brew shellenv)"
brew services start ollama

ollama --version

ollama run mistral

>Will see

>>> Send a message (/? for help)


