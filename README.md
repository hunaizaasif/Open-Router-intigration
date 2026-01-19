# Open-Router-intigration
# Use Claude Code for Free Using OpenRouter (Free Models)

**January 10, 2026**
⏱️ *2 min read*

## Free Claude Code Setup with OpenRouter (Free Models)

This guide explains **step-by-step** how to run **Claude Code for FREE** using **OpenRouter** and its **free LLM models** via:

* `claude-code`
* `claude-code-router`

No paid Claude subscription required 🚀

---

## 1. Prerequisites

### Verify Node.js Installation

Open **PowerShell** (Windows) or **Terminal** (Linux/macOS) and run:

```
node --version
```

✅ **Node.js 18.x or higher** is required

Download **LTS version** from:
👉 [https://nodejs.org](https://nodejs.org)

---

## 2. Create OpenRouter Account & API Key

1. Visit 👉 [https://openrouter.ai](https://openrouter.ai)
2. Sign up / Login
3. Go to **API Keys**
4. Click **Create Key**
5. Copy your API key:

```
sk-or-v1-xxxxxxxxxxxxxxxxxxxxxxxx
```

---

## 3. Check Free Models on OpenRouter

Recommended **free models**:

* `mistralai/devstral-2512:free`
* `qwen/qwen-2.5-coder-32b-instruct:free`
* `nousresearch/hermes-3-llama-3.1-405b:free`

📌 Full free model list:
👉 [https://openrouter.ai/models?pricing=free](https://openrouter.ai/models?pricing=free)

---

## 4. Install Required CLI Tools

Run the following command:

```
npm install -g @anthropic-ai/claude-code @musistudio/claude-code-router
```

---

## 5. Create Required Directories

### Windows / PowerShell

```
mkdir $HOME/.claude-code-router
mkdir $HOME/.claude
```

### Ubuntu / Linux

```
mkdir -p ~/.claude-code-router ~/.claude
```

---

## 6. Create Router Configuration File

### Windows

```
notepad $HOME/.claude-code-router/config.json
```

Paste the following:

```json
{
  "LOG": true,
  "LOG_LEVEL": "info",
  "HOST": "127.0.0.1",
  "PORT": 3456,
  "API_TIMEOUT_MS": 600000,

  "Providers": [
    {
      "name": "openrouter",
      "api_base_url": "https://openrouter.ai/api/v1/chat/completions",
      "api_key": "$OPENROUTER_API_KEY",
      "models": [
        "mistralai/devstral-2512:free"
      ],
      "transformer": {
        "use": ["openrouter"]
      }
    }
  ],

  "Router": {
    "default": "openrouter,mistralai/devstral-2512:free",
    "background": "openrouter,mistralai/devstral-2512:free",
    "think": "openrouter,mistralai/devstral-2512:free",
    "longContext": "openrouter,mistralai/devstral-2512:free",
    "longContextThreshold": 60000
  }
}
```

---

## 7. Set Environment Variable

### Windows (PowerShell)

```
[System.Environment]::SetEnvironmentVariable(
  'OPENROUTER_API_KEY',
  'YOUR_API_KEY_HERE',
  'User'
)
```

Verify:

```
echo $env:OPENROUTER_API_KEY
```

---

## 8. Start Router

```
ccr start
```

If everything is correct, the router will start on **localhost:3456** ✅

---

## 9. Use Claude Code

Navigate to your project folder:

```
cd your-project-folder
```

Start Claude Code:

```
ccr code
```

Test it:

```
hi
```

---

## Ubuntu / Linux One-Command Config

```
cat > ~/.claude-code-router/config.json << 'EOF'
{
  "LOG": true,
  "LOG_LEVEL": "info",
  "HOST": "127.0.0.1",
  "PORT": 3456,
  "API_TIMEOUT_MS": 600000,

  "Providers": [
    {
      "name": "openrouter",
      "api_base_url": "https://openrouter.ai/api/v1/chat/completions",
      "api_key": "$OPENROUTER_API_KEY",
      "models": [
        "mistralai/devstral-2512:free"
      ],
      "transformer": {
        "use": ["openrouter"]
      }
    }
  ],

  "Router": {
    "default": "openrouter,mistralai/devstral-2512:free",
    "background": "openrouter,mistralai/devstral-2512:free",
    "think": "openrouter,mistralai/devstral-2512:free",
    "longContext": "openrouter,mistralai/devstral-2512:free",
    "longContextThreshold": 60000
  }
}
EOF
```

---

## 🎉 Done!

**Claude Code + OpenRouter (Free Models) is now working!**

You can now:

* Generate code
* Refactor projects
* Debug issues
* Use Claude-style coding workflows
  **100% FREE** 💥

---

💡 *Tip:* If BonsAI or paid APIs fail, OpenRouter free models are the best alternative.

Happy Coding! 🚀
