# team-sheet

*A map of your inner world.*

---

Most self-help tools treat the mind as a single agent to be optimised. team-sheet treats it as a system of parts — each trying to help, each with its own history, fears, and gifts.

team-sheet is a personal IFS (Internal Family Systems) mapping app. Journal with your AI, paste back the JSON, and watch your inner map fill in over time. No AI? Edit fields directly — it works fully standalone too.

---

## What is IFS?

Internal Family Systems is a model of the mind developed by psychologist Richard Schwartz. It proposes that the psyche is made up of distinct **parts** — each with its own perspective, emotions, and intentions — and a core **Self** that can witness and relate to those parts from a place of calm, curiosity, and compassion.

Parts are not problems. They are protective strategies that made sense at the time they formed. The aim of IFS is not to eliminate parts, but to understand them, build trust with them, and help them carry less.

There are three types of protective part:
- **Managers** — proactive protectors that keep order before things go wrong. They plan, achieve, control, and please.
- **Firefighters** — reactive protectors that step in when pain has already been triggered. They distract, numb, and douse the fire.
- **Exiles** — parts that carry old pain, shame, or fear. They have been pushed away by protectors to keep the system stable.

**Self** is not a part. It is your natural ground state — the quality of presence that remains when parts step back. IFS describes Self through the 8 Cs (Calm, Curiosity, Clarity, Compassion, Confidence, Courage, Creativity, Connectedness) and the 5 Ps (Presence, Patience, Perspective, Persistence, Playfulness).

team-sheet is not a replacement for IFS therapy. It is a reflective tool for mapping your system, tracking what you notice, and building a relationship with your parts over time.

---

## Setup

1. **Download [`team-sheet.html`](team-sheet.html) and [`instructions.md`](instructions.md):** click each link, then the download icon (top right).
2. **Create (or open) your AI project:** e.g. [claude.ai](https://claude.ai) → New Project.
3. **Upload `instructions.md` to project knowledge:** Project sidebar → Add content → Add files.
4. **Paste the quickstart prompt** below and start talking.
5. **At the end of your session, ask:** `"Update my data.json based on our conversation."`
6. **Add `data.json` to project knowledge:** same as step 3. (If updating: remove the old version first, then upload the new one.)
7. **Import into the app:** open `team-sheet.html`, click `↑` (top right), paste the JSON, Import.

---

## Quickstart prompt

```
I'm setting up team-sheet, a personal IFS mapping app. I've attached instructions.md which explains the data format and how to work with me.

Start by asking me what's been on my mind lately — what I've been noticing internally, any recurring patterns, tensions, or inner conflicts. Keep it conversational, ask one thing at a time, and follow the thread. Don't introduce IFS language until it becomes useful.

Once you have a reasonable picture, generate my initial data.json using the format in instructions.md. We can fill in the gaps over time.
```

---

## Each session

1. **Start a new chat** in your AI project. The AI already has your context from project knowledge.
2. **Journal:** brain dump freely, or name a mode (see below).
3. **End the session:** ask your AI to *"Update my data.json."*
4. **Replace `data.json` in project knowledge:** remove the old version, upload the new one.
5. **Sync the app:** click `↑`, paste the JSON, Import.

---

## Session modes

Name any mode at the start of a session to direct the conversation.

| Mode | Trigger phrase | Best for |
|------|----------------|----------|
| **First-time setup** | `"let's do first-time setup"` | Building your initial parts map from scratch |
| **History** | `"let's fill in history"` | Exploring when and why a part emerged; adding key events to the timeline |
| **Check-in** | `"let's check in on today"` | Which parts were active? How was the day led? |
| **Challenge** | `"let's challenge the map"` | Are parts correctly identified? Should any be merged or split? |
| **Part focus** | `"let's focus on [part name]"` | Deep work with one part, using the 6 Fs sequence |

---

## The 6 Fs: working with a part

When focusing on a specific part, the AI will use the 6 Fs as a loose guide:

1. **Find** — locate the part; where do you feel it in your body?
2. **Focus** — turn attention toward it without trying to change it
3. **Flesh out** — get to know its shape, age, and what it's doing
4. **Feel toward** — what arises in you when you look at it?
5. **Befriend** — what does the part want you to know? What has it been trying to do?
6. **Fear** — what is it afraid would happen if it stopped doing its job?

---

## Tabs at a glance

| Tab | What it shows |
|-----|---------------|
| **Map** | A visual overview of your parts as nodes, sized by prominence, connected by relationship edges |
| **Parts** | The full roster of your parts: role, overview, wants, fears, gifts, and relationships |
| **Self** | The 8 Cs and 5 Ps of Self-energy; a log of Self-led moments |
| **Journal** | Session entries: what was explored, which parts were active, what shifted |
| **Timeline** | A horizontal chart showing when each part emerged and key events in its history |

---

## Privacy and security

- **`data.json` is your private diary.** Nothing leaves your machine unless you send it. Any AI provider you journal with may store or use what you share. Check their privacy settings.
- **Your `data.json` is the sensitive part.** `team-sheet.html` and `instructions.md` are identical for all users and safe to share freely.
- **Think before syncing `data.json` to cloud storage.** Uploading to Google Drive, Dropbox, or iCloud means trusting that provider with your inner world material.
- **AI is optional.** The app works fully offline as a plain tracker. Edit fields directly without any AI involved.
- **Use [Firefox](https://www.firefox.com/) if possible.** It isolates each local HTML file's storage. In Chrome and Edge, all local files share the same origin.

team-sheet is not a replacement for professional mental health support. IFS has a strong evidence base and is practised by trained therapists — if you're working with complex trauma or distressing material, please seek qualified support alongside using this app.

---

## Files

| File | What it is |
|------|------------|
| **[team-sheet.html](team-sheet.html)** | The app. Open in your browser. |
| **[instructions.md](instructions.md)** | Upload to your AI project knowledge. Defines the data format and all session guidance. |
| **[alex-example-data.json](alex-example-data.json)** | Example data so you can see what a mapped system looks like. |

---

## Why I built this

IFS gave me a genuinely useful framework for understanding my inner world — but keeping track of it was hard. Insights from one session were forgotten by the next. Parts I'd named would fade back into unnamed patterns. There was nowhere to hold the map.

team-sheet is that place. A single file, no server, no accounts. Your data stays on your machine. Pair it with an AI that has persistent project context and you have a reflective partner that remembers every part you've named — and can help you go deeper each time.

---

*companion to [character-sheet](../README.md) — a gamified life dashboard built on the same local-first, AI-optional architecture.*
