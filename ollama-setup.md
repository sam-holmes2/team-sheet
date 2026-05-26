# Ollama setup guide

Everything you need to install, configure, and troubleshoot Ollama for use with team-sheet.

---

## 1. Install Ollama

| OS | How |
|----|-----|
| **Mac** | `brew install ollama` or [download from ollama.com](https://ollama.com/download) |
| **Windows** | [Download the installer from ollama.com](https://ollama.com/download) and run it |
| **Linux** | `curl -fsSL https://ollama.com/install.sh \| sh` |

---

## 2. Choose and download a model

Open a Terminal (Mac/Linux) or PowerShell (Windows) and run the pull command for your model.

Pick the largest model your RAM comfortably fits:

| Your RAM | Recommended model | Pull command |
|----------|-------------------|--------------|
| 8 GB | `gemma3:4b` | `ollama pull gemma3:4b` |
| 16 GB | `qwen2.5:7b` | `ollama pull qwen2.5:7b` |
| 32 GB | `qwen2.5:14b` | `ollama pull qwen2.5:14b` |
| 64 GB+ | `qwen2.5:32b` | `ollama pull qwen2.5:32b` |

Not sure what your hardware can handle? [llmfit](https://github.com/AlexsJones/llmfit) detects your RAM and GPU and scores every model. Mac/Linux: `brew install llmfit` then `llmfit fit`.

**Context window:** your parts map grows as you add more sessions. A model's context window must be large enough to fit your data plus the conversation. Export your JSON (click the download icon), then check the file size. A 50 KB file is roughly 12,000 tokens. Set the Context Window in Chat Settings to at least twice the size of your data.

---

## 3. Start Ollama with browser access

By default, browsers cannot reach Ollama due to CORS restrictions. You need to start it with that restriction lifted. Run the command for your OS in a new terminal window and **keep that window open while using the app**.

**Mac:**
```sh
pkill -f "Ollama.app/Contents/MacOS" 2>/dev/null; pkill -f "ollama serve" 2>/dev/null; sleep 1; OLLAMA_ORIGINS="*" ollama serve
```

**Linux:**
```sh
pkill -f "ollama serve" 2>/dev/null; sleep 1; OLLAMA_ORIGINS="*" ollama serve
```

**Windows (PowerShell):**
```powershell
Stop-Process -Name ollama -Force -ErrorAction SilentlyContinue; Start-Sleep 1; $env:OLLAMA_ORIGINS="*"; ollama serve
```

The app's Chat Settings screen also shows these commands for your OS.

> **Close the terminal when you are done.** This stops Ollama and prevents other browser pages from reaching it while it is not in use.

---

## 4. Connect in the app

Open `team-sheet.html`, click the chat icon, then the gear icon (Chat Settings). Your model should appear in the model list. Select it and start a session.

---

## Troubleshooting

### "Could not connect" or "Ollama not running"

Ollama is either not started, or started without the CORS header the browser requires. Run the stop-and-start command for your OS from step 3 above, then try again.

To verify Ollama is running, open a new browser tab and go to `http://localhost:11434`. You should see `Ollama is running`.

### "Model not found"

The model listed in Chat Settings is not downloaded. Run `ollama pull <model-name>` in a terminal. The in-app error card shows the exact command.

### Ollama starts but the app still cannot connect

You may have started Ollama without `OLLAMA_ORIGINS="*"`, or an old instance is still running. Stop it fully with the kill command above, then restart.

Check what is listening on port 11434:
- Mac / Linux: `lsof -i :11434`
- Windows: `netstat -ano | findstr 11434`

### Slow responses or out-of-memory errors

The model is too large for your available RAM. Switch to a smaller model (e.g. `gemma3:4b`) in Chat Settings, or reduce the Context Window setting.

### Checking Ollama logs

Run with debug output to see what is happening:
- Mac / Linux: `OLLAMA_DEBUG=1 OLLAMA_ORIGINS="*" ollama serve`
- Windows: `$env:OLLAMA_DEBUG=1; $env:OLLAMA_ORIGINS="*"; ollama serve`

### Reinstalling Ollama

If nothing works, uninstall and reinstall:
- **Mac:** drag Ollama out of Applications, then `rm -rf ~/.ollama` to remove all models, then reinstall from [ollama.com/download](https://ollama.com/download)
- **Linux:** `sudo systemctl stop ollama; sudo rm /usr/local/bin/ollama; rm -rf ~/.ollama`
- **Windows:** uninstall via Add/Remove Programs, then delete `%USERPROFILE%\.ollama`
