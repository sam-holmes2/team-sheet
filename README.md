# team-sheet

*Every part of you is on the same team.*

Your mind is made up of **parts**: the Achiever that drives you, the Critic that cuts you down, the Soother that numbs when things get hard. [IFS (Internal Family Systems)](https://ifs-institute.com/) is a widely-used therapeutic framework built on this insight — that inner conflict is not a flaw to fix, but a system of parts to understand. team-sheet maps your inner system as it grows more detailed over time, session by session.

🗺️ **[Try the live demo](https://sam-holmes2.github.io/team-sheet/team-sheet.html)** — no download needed

<img width="2708" height="1258" alt="image" src="https://github.com/user-attachments/assets/82689abe-04d2-4823-b230-b51c6b18b4a7" />

---

**After a few sessions you'll have:**
- A visual map of your parts: named, sized by prominence, connected by relationship edges
- Profiles for each part: what it does, what it wants and fears, when it shows up, what it carries from the past
- A log of Self-led moments, tagged by quality (calm, curiosity, compassion, etc.)
- A timeline showing when each part emerged and how the balance between parts and Self has shifted

---

🔒 **Private by default.** A single `.html` file. No server, no accounts, no telemetry. Your data lives on your device. Nothing leaves unless you send it.

🤖 **AI is optional.** Works fully offline. Use a local model, a cloud AI, or no AI at all.

🚧 **Early work in progress.** Feedback welcome: [open an issue](https://github.com/sam-holmes2/team-sheet/issues) or [start a discussion](https://github.com/sam-holmes2/team-sheet/discussions).

---

## Privacy and security

Your data stays on your device. Nothing is transmitted automatically — you decide what leaves your machine and when.

- **`data.json` is your private diary.** IFS material is deeply personal. Any AI provider you journal with may store or use what you share. Check their privacy settings to opt out.
- **Think before syncing `data.json` to cloud storage.** Uploading to Google Drive, Dropbox, or iCloud means trusting that provider with your inner world. `team-sheet.html` and `instructions.md` are fine to sync.
- **Keep your API key in a password manager** (1Password, Bitwarden, Apple Passwords, etc.) and enable two-factor authentication on your AI provider account.
- **Enable full-disk encryption** on your device (FileVault on Mac, BitLocker on Windows). If your laptop is stolen, disk encryption is the barrier between a thief and your browser storage files.
- **Use [Firefox](https://www.firefox.com/) if possible.** Firefox isolates each local HTML file's storage. In Chrome and Edge, all local files share the same origin.
- **Close Ollama when you are done.** When running a local model, closing the terminal stops Ollama and prevents other browser pages from reaching it.

**Password lock.** The app has an optional password that encrypts all your data in the browser. Given the sensitivity of IFS material, this is strongly recommended. Set it in the Security section (gear icon, top right).

[Full threat model](journalling-threat-model.md) — privacy risks broken down across every journalling approach.

---

## Files in this repo

| File | What it is |
|------|------------|
| **[team-sheet.html](team-sheet.html)** | The app. Download and open in your browser. |
| **[instructions.md](instructions.md)** | Upload to your AI project knowledge (copy-paste workflow). |
| **[ollama-setup.md](ollama-setup.md)** | Ollama install, model selection, and troubleshooting. |
| **[ai-privacy-guide.md](ai-privacy-guide.md)** | Provider-by-provider privacy breakdown. |
| **[journalling-threat-model.md](journalling-threat-model.md)** | Privacy risk breakdown across all journalling approaches. |

---

## Choose your path

No account required for any option. Pick based on how private you want your data to be and how much setup you're willing to do.

| | **A. No AI** | **B. Local AI (Ollama)** | **C. Cloud AI, in-app** | **D. Cloud AI, copy-paste** |
|---|---|---|---|---|
| **Privacy** | Fully offline | Fully offline, nothing leaves your device | Your session data is sent to your AI provider | You control exactly what you share |
| **Cost** | Free | Free | Pay per use | Free tier available |
| **Setup** | Instant | ~10 minutes, one-time | ~5 minutes | ~5 minutes |
| **AI quality** | No AI | Good | Best | Best |

---

### A. No AI

Download and open `team-sheet.html`. Go to the Parts tab and click **+ Add part**. Fill in fields directly in the app.

Export your data regularly with the download button (top right). That's it — the whole app works offline with no AI involved.

---

### B. Local AI with Ollama

IFS sessions involve sensitive personal material. A local model means nothing is sent anywhere.

**1. Download the app**

Go to [team-sheet.html](team-sheet.html) on GitHub, click the download icon (top right of the file view). Open it in your browser.

**2. Install Ollama and download a model**

See [ollama-setup.md](ollama-setup.md) for the full install guide and model recommendations.

Quick start: install Ollama, then run `ollama pull gemma3:4b` in a terminal. `gemma3:4b` works on most computers (8 GB RAM, ~4 GB download).

**3. Start Ollama with browser access**

Browsers cannot reach Ollama by default. Run the command for your OS in a terminal and keep it open while using the app:

| OS | Command |
|----|---------|
| **Mac** | `pkill -f "Ollama.app/Contents/MacOS" 2>/dev/null; pkill -f "ollama serve" 2>/dev/null; sleep 1; OLLAMA_ORIGINS="*" ollama serve` |
| **Linux** | `pkill -f "ollama serve" 2>/dev/null; sleep 1; OLLAMA_ORIGINS="*" ollama serve` |
| **Windows (PowerShell)** | `Stop-Process -Name ollama -Force -ErrorAction SilentlyContinue; Start-Sleep 1; $env:OLLAMA_ORIGINS="*"; ollama serve` |

Close the terminal when you are done to stop Ollama.

**4. Open the app and start chatting**

Click the chat icon, open Chat Settings (gear icon), confirm your model is selected, and start talking.

Having trouble? See [ollama-setup.md](ollama-setup.md#troubleshooting).

---

### C. Cloud AI with an API key (in-app chat)

Use the [live demo](https://sam-holmes2.github.io/team-sheet/team-sheet.html) (requires HTTPS) or your downloaded file.

> Your session data is sent to your AI provider with each message. IFS material is personal — use [Path B](#b-local-ai-with-ollama) if this concerns you. See [ai-privacy-guide.md](ai-privacy-guide.md) for provider details.

1. Create an account at [console.anthropic.com](https://console.anthropic.com) (separate from Claude.ai)
2. Go to **API Keys** and create a new key
3. Store the key in a password manager — it cannot be retrieved from Anthropic after creation
4. Enable two-factor authentication on your Anthropic account
5. In the app: go to **Security** (gear icon, top right) and set a password first — the app won't save an API key without one
6. Open Chat Settings (gear icon in the chat panel), select a Claude model, and paste your key

> Your API key grants access to your Anthropic account. Anyone with it can generate charges. Never paste it into websites you don't trust.

---

### D. Cloud AI via copy-paste (no API key)

Use any AI — Claude, ChatGPT, Gemini — through its normal web interface. No in-app chat or API key needed.

**First session:**
1. Download [team-sheet.html](team-sheet.html) and [instructions.md](instructions.md) — click each link, then the download icon
2. Create an AI project (e.g. [claude.ai](https://claude.ai) → New Project)
3. Upload `instructions.md` to the project knowledge
4. Paste the [quickstart prompt](#quickstart-prompt) and start talking
5. At the end of the session, ask: *"Update my data based on our conversation."*
6. Upload the resulting `data.json` to project knowledge
7. Import into the app: click the upload icon (top right), paste the JSON, Import

> Your session data is sent to your provider with each message. Check their privacy settings if this concerns you.

---

## Quickstart prompt

```
I'm setting up team-sheet, a personal IFS mapping app. I've attached instructions.md which explains the data format and how to work with me.

Start by asking me what's been on my mind lately: what I've been noticing internally, any recurring patterns, tensions, or inner conflicts. Keep it conversational, ask one thing at a time, and follow the thread. Don't introduce IFS language until it becomes useful.

Once you have a reasonable picture, generate my initial data.json using the format in instructions.md. We can fill in the gaps over time.
```

---

## Each session (copy-paste workflow)

1. If you made any changes in the app, export first: click the download icon (top right)
2. Start a new chat in your AI project — check your latest `data.json` is in the project knowledge
3. Journal freely, or name a [session mode](#session-modes) to start with
4. Ask your AI to *"Update my data"*
5. Replace `data.json` in project knowledge: remove the old version, upload the new one
6. Sync the app: click the upload icon, paste the JSON, Apply

---

## Tabs at a glance

| Tab | What it shows |
|-----|---------------|
| **Map** | A visual overview of your parts as nodes, sized by prominence, connected by relationship edges |
| **Parts** | The full roster of your parts: role, overview, wants, fears, skills, and relationships |
| **Self** | The 8 Cs and 5 Ps of Self-energy; a log of Self-led moments |
| **Journal** | Session entries: what was explored, which parts were active, what shifted |
| **Timeline** | A chart showing when each part emerged and how the balance between parts and Self has shifted |

---

## Session modes

Name any mode at the start of a session to direct the conversation.

| Mode | Trigger phrase | Best for |
|------|----------------|----------|
| **First-time setup** | `"let's do first-time setup"` | Building your initial parts map from scratch |
| **History** | `"let's fill in history"` | Exploring when and why a part emerged |
| **Check-in** | `"let's check in on today"` | Which parts were active? How was the day led? |
| **Challenge** | `"let's challenge the map"` | Are parts correctly identified? Should any be merged or split? |
| **Part focus** | `"let's focus on [part name]"` | Deep work with one part, using the 6 Fs sequence |

---

## The 6 Fs: working with a part

When focusing on a specific part, your AI will use the 6 Fs as a loose guide. You don't need to know these in advance — the AI will lead naturally.

1. **Find:** locate the part; where do you feel it in your body?
2. **Focus:** turn attention toward it without trying to change it
3. **Flesh out:** get to know its shape, age, and what it's doing
4. **Feel toward:** what arises in you when you look at it?
5. **Befriend:** what does the part want you to know? What has it been trying to do?
6. **Fear:** what is it afraid would happen if it stopped doing its job?

---

## What is IFS?

[Internal Family Systems (IFS)](https://ifs-institute.com/) is a model of the mind developed by psychologist Richard Schwartz in the 1980s. The core insight is simple but far-reaching: the mind is not a single unified voice. It is a system of **parts**, each with its own perspective, values, needs, emotions, fears, and intentions.

**No prior IFS experience needed.** The quickstart prompt lets you journal freely, and your AI will introduce IFS concepts only when they become useful.

### The three types of part

**Managers** are proactive protectors. They run things before pain has a chance to arrive: planning, achieving, controlling, people-pleasing. A manager's logic is: if I stay on top of everything, nothing bad can happen.

**Firefighters** are reactive protectors. They step in after pain has already been triggered and douse the fire by any means necessary: scrolling, drinking, overeating, rage, withdrawal. Firefighters are not the enemy; they are crisis responders doing the only thing they know how.

**Exiles** carry the original pain: old shame, fear, grief, or wounds from the past. Managers and firefighters exist largely to keep exiles locked away because their pain feels too much to bear.

### Self

**Self** is not a part. It is your natural ground state: the calm, curious, connected presence that remains when parts step back. IFS describes Self through the **8 Cs** (Calm, Curiosity, Clarity, Compassion, Confidence, Courage, Creativity, Connectedness) and the **5 Ps** (Presence, Patience, Perspective, Persistence, Playfulness). The aim of IFS is not to eliminate parts, but to build a relationship with each one from Self.

### IFS and professional therapy

IFS is one of the few approaches recognised by SAMHSA as an evidence-based treatment. **team-sheet is a reflective tool, not a replacement for therapy.** If you are dealing with complex trauma or distressing material, IFS therapy with a qualified practitioner offers depth and safety that self-guided tools cannot.

Find a qualified IFS therapist:
- [IFS Institute Practitioner Directory](https://ifs-institute.com/practitioners)
- [IFS Training UK Therapist Directory](https://directory-uk.internalfamilysystemstraining.co.uk/)

---

## Want to learn more about IFS?

**To listen first:**
- [How (and Why) to Hug Your Inner Dragons](https://open.spotify.com/episode/3St6LBbY32Tuck0XAuQQHE) — interview with Richard Schwartz
- [The Tim Ferriss Show #492 with Richard Schwartz](https://www.youtube.com/watch?v=ebLMeNiuoEo)

**To read:**
- *Introduction to the Internal Family Systems Model* — Richard Schwartz. 140-page overview, the shortest path to understanding the whole model.
- *Self-Therapy* — Jay Earley. Step-by-step guide for doing IFS on yourself.
- *No Bad Parts* — Richard Schwartz. Applies IFS to relationships and broader societal change.

[The IFS Institute](https://ifs-institute.com/) has free articles, videos, and the official practitioner directory.

---

## Customising

team-sheet is free and open source. Both the app and instructions are designed to be modified.

- **Edit `instructions.md`** to change how your AI communicates, which part properties it focuses on, how it phrases questions, or what session modes are available. All changes stay in your own copy.
- **Edit `team-sheet.html`** directly to rename fields, add new part properties, adjust the visual map, or remove sections. It's a single file with no build step.

Contributions welcome: [open a pull request](https://github.com/sam-holmes2/team-sheet/pulls) or share ideas in issues.

---

## Why I built this

IFS gave me a genuinely useful framework for understanding my inner world, but keeping track of this understanding as it grew more complex over time became difficult. Insights from one therapy session were often forgotten by the next. I found it helpful to regularly check in with my parts between sessions, as IFS creator Richard Schwartz recommends, but this became far easier when it contributed to a growing, evolving map.

I also noticed some parts were craving something more external and objective — clear evidence that I was on the right track — to help recognise and appreciate the growth and healing that other skeptical parts tended to dismiss. team-sheet became that place for me, and I hope it can benefit others too.

---

## Support

team-sheet is free and always will be. If it's been useful to you, you can [sponsor the project on GitHub](https://github.com/sponsors/sam-holmes2).

---

*Companion to [character-sheet](https://sam-holmes2.github.io/character-sheet/character-sheet.html), a gamified life dashboard built on the same local-first, AI-optional architecture. If team-sheet is a cozy management game like Animal Crossing for understanding and befriending your inner world, character-sheet is an intense RPG like Skyrim where you are the main character: for accountability, encouragement, and a quest log to help you level up and tackle the external world.*
