# 🛠️ Chat with a Local Model (Using Ollama)

This guide shows how to interact with a locally hosted LLM using **Ollama**, both through its terminal interface and via API calls.

> 🧠 Works with any model you've downloaded (e.g., `mistral`, `gemma:2b`, `llama2`)

---

## 🖥️ 1. Interactive Terminal Mode

Launch a model directly:

```bash
ollama run mistral

>>> Send a message (/? for help)

What are three uses for volcanic ash in agriculture?

One-Off Responses (Non-Interactive):
echo "Summarize the plot of Dune." | ollama run mistral

By default, Ollama runs a REST API on:
http://localhost:11434

Example curl Request:
curl http://localhost:11434/api/generate \
  -d '{
    "model": "mistral",
    "prompt": "Explain the concept of entropy in one paragraph.",
    "stream": false
  }'

Response format:
{
  "model": "mistral",
  "created_at": "...",
  "response": "Entropy measures the disorder or randomness in a system...",
  "done": true
}

Tip: Use jq for Cleaner Output
curl -s http://localhost:11434/api/generate \
  -d '{"model":"mistral","prompt":"What is Kubernetes?","stream":false}' \
  | jq -r .response

Automate It: Simple Bash Function

Add this to your ~/.bash_profile:
askollama() {
  curl -s http://localhost:11434/api/generate \
    -d "{\"model\":\"mistral\",\"prompt\":\"$*\",\"stream\":false}" \
    | jq -r .response
}

Run CLI:

askollama What's a good name for a CLI LLM assistant?
(Good function)
