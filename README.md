# team-sheet

*A map of your inner world 🌍*

---

Most self-help tools treat the mind as a single agent to be optimised. team-sheet treats it as a system of parts, each trying to help, each with its own history, fears, and gifts.

team-sheet is a personal [IFS (Internal Family Systems)](https://ifs-institute.com/) mapping app. Journal with your AI, paste back the JSON, and watch your inner map take shape and grow more detailed over time. No AI? Edit fields directly — it works fully standalone too.

No prior IFS experience needed. The app will introduce the concepts naturally through journalling.

---

🔒 **Private by default.** A single `.html` file and some JSON — no server, no accounts, no telemetry. Your data stays on your machine. If you use an AI to journal, check your provider's privacy settings. Local models like [Ollama](https://ollama.com) work for fully offline journalling.

---

## Setup

1. **Download [`team-sheet.html`](team-sheet.html) and [`instructions.md`](instructions.md):** click each link, then the download icon (top right).
2. **Create (or open) your AI project:** e.g. [claude.ai](https://claude.ai) → New Project.
3. **Upload `instructions.md` to project knowledge:** Project sidebar → Add content → Add files.
4. **Paste the quickstart prompt** below and start talking.
5. **At the end of your session, ask:** `"Update my data.json based on our conversation."`
6. **Add `data.json` to project knowledge:** same as step 3. (If updating: remove the old version first, then upload the new one.)
7. **Import into the app:** open `team-sheet.html`, click `↑` (top right), paste the JSON, Import.

**No AI?** Open the app, edit fields directly, and export your data. The import/export workflow is optional.

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

When focusing on a specific part, the AI will use the 6 Fs as a loose guide. You do not need to know these in advance; the AI will lead the conversation naturally. They describe a direction of inquiry, not a rigid script.

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
| **Parts** | The full roster of your parts: role, overview, wants, fears, skills, and relationships |
| **Self** | The 8 Cs and 5 Ps of Self-energy; a log of Self-led moments |
| **Journal** | Session entries: what was explored, which parts were active, what shifted |
| **Timeline** | A horizontal chart showing when each part emerged, key memories in their history, and how the balance between parts and Self has shifted over time |

---

## What is IFS?

[Internal Family Systems (IFS)](https://ifs-institute.com/) is a model of the mind developed by psychologist Richard Schwartz in the 1980s. It is one of the most widely-used frameworks in contemporary psychotherapy, with a growing evidence base for treating trauma, anxiety, depression, and other conditions. The core insight is simple but far-reaching: the mind is not a single unified voice. It is a system of **parts**, each with its own perspective, values, needs, emotions, fears, and intentions.

You have probably already met some of yours: the part that wants to get things done and the part that just can't start. The part that longs for connection and the part that pushes people away. The voice that says you're not good enough, and the quieter voice that knows that isn't true. IFS is a framework for understanding yourself and your inner conflicts on a deeper level, and for developing a genuine relationship with each of these parts.

### The three types of part

**Managers** are proactive protectors. They run things before pain has a chance to arrive. They plan, achieve, control, optimise, and people-please. A manager's logic is: if I stay on top of everything, nothing bad can happen. Managers are often responsible for your most productive and also your most exhausting traits.

**Firefighters** are reactive protectors. They step in *after* pain has already been triggered, when something has gotten through the managers. Their job is to douse the fire by any means necessary: scrolling, drinking, overeating, rage, withdrawal, numbing. Firefighters are not the enemy; they are crisis responders doing the only thing they know how.

**Exiles** are the parts that carry the original pain: old shame, fear, grief, or wounds from the past. Managers and firefighters exist in large part to keep exiles locked away, because their pain feels too much to bear. IFS therapy involves, carefully and with professional support, getting to know exiles and helping them carry less.

### Self

**Self** is not a part. It is not a voice or an agenda. It is your natural ground state: the calm, curious, connected presence that remains when parts step back. IFS describes Self through the **8 Cs** (Calm, Curiosity, Clarity, Compassion, Confidence, Courage, Creativity, Connectedness) and the **5 Ps** (Presence, Patience, Perspective, Persistence, Playfulness). You cannot lose Self; you can only lose access to it when parts are running things.

The aim of IFS is not to eliminate parts or become "part-free". Parts are protective strategies that formed for good reasons. The aim is to build a relationship with each part from Self, to understand what it has been trying to do, and to help it carry less so it can play a freer role.

### IFS and professional therapy

IFS is widely practised by trained therapists and is one of the few approaches recognised by the US Substance Abuse and Mental Health Services Administration (SAMHSA) as an evidence-based treatment. If you are dealing with complex trauma, significant mental health challenges, or distressing material, IFS therapy with a qualified practitioner offers depth and safety that self-guided tools cannot provide.

**team-sheet is a reflective tool, not a replacement for therapy.** Use it alongside professional support, or as a way of mapping your inner world and preparing for sessions. If you are looking for a qualified IFS therapist:

- [IFS Institute Practitioner Directory](https://ifs-institute.com/practitioners) — the official directory maintained by Richard Schwartz's own organisation
- [IFS Training UK Therapist Directory](https://directory-uk.internalfamilysystemstraining.co.uk/) — for UK-based practitioners

Outside the US and UK, search for "IFS therapist" with your country or city, or filter by "Internal Family Systems" on your national therapist directory, to find trained practitioners.

---

## What the app gives you

- **A parts map:** a visual overview of your parts as nodes, sized by prominence, connected by relationship edges
- **Part profiles:** for each part: role, overview, wants, fears, skills, triggers, body sensations, and relationships to other parts
- **A Self log:** moments of genuine Self-leadership, tagged by quality (curiosity, compassion, calm, etc.)
- **Session journal:** narrative summaries of what was explored each session and which parts were active
- **A timeline:** when each part emerged, key memories in their history, and how the balance between parts and Self has shifted over time

Over sessions, the map is drawn and refined. Parts that were unnamed and tangled become distinct and understood. Relationships between parts become visible. Self-led moments start to outweigh part-driven ones. The app holds what would otherwise be forgotten between sessions.

---

## Do I need to know IFS first?

No. The quickstart prompt is designed to let you journal freely about what's going on, and the AI will introduce IFS concepts only when they become useful. You do not need to read anything before starting.

If you want to go deeper before or alongside using the app, here are good starting points.

**To listen first:**

- **Podcast:** "How (and Why) to Hug Your Inner Dragons" — an interview with Richard Schwartz, the founder of IFS. A good first listen if you prefer audio.
- **Podcast:** The Tim Ferriss Show #492 — "Richard Schwartz: IFS, Psychedelic Experiences Without Drugs, and Finding Inner Peace for Our Many Parts". Wide-ranging and accessible.

**To read first:**

- **Book:** *Introduction to the Internal Family Systems Model* by Richard Schwartz. A friendly 140-page overview with examples — the shortest path to understanding the whole model.
- **Book:** *Self-Therapy* by Jay Earley. A comprehensive step-by-step guide aimed at people doing IFS on themselves or with a friend.
- **Article:** "Introduction to Internal Family Systems Therapy" by Jay Earley — a free shorter overview of the same ground.

**To go further:**

- **Book:** *No Bad Parts* by Richard Schwartz. His newest book, applying IFS not just to personal healing but to relationships and broader societal change.
- **Book:** *You Are the One You've Been Waiting For* by Richard Schwartz. Applies IFS to romantic relationships: how two people's exiles and protectors trigger each other.
- **Book:** *Somatic Internal Family Systems Therapy* by Susan McConnell. Unifies IFS with somatic experiencing — useful if body-based work resonates with you.
- **Book:** *Self-Therapy, Vol. 2* by Jay Earley. Advanced techniques: switching focus between parts, working with polarized parts, and more.

**Online:**

- [The IFS Institute](https://ifs-institute.com/) — free articles, videos, and the official practitioner directory. Richard Schwartz's own organisation.

---

## Privacy and security

- **`data.json` is your private diary.** Nothing leaves your machine unless you send it. Any AI provider you journal with may store or use what you share. Check their privacy settings.
- **Your `data.json` is the sensitive part.** `team-sheet.html` and `instructions.md` are identical for all users and safe to share freely.
- **Think before syncing `data.json` to cloud storage.** Uploading to Google Drive, Dropbox, or iCloud means trusting that provider with your inner world material.
- **AI is optional.** The app works fully offline as a plain tracker. Edit fields directly without any AI involved.
- **Use [Firefox](https://www.firefox.com/) if possible.** It isolates each local HTML file's storage. In Chrome and Edge, all local files share the same origin.

team-sheet is not a replacement for professional mental health support. IFS has a strong evidence base and is practised by trained therapists. If you are working with complex trauma or distressing material, please seek qualified support alongside using this app.

---

## Files

| File | What it is |
|------|------------|
| **[team-sheet.html](team-sheet.html)** | The app. Open in your browser. |
| **[instructions.md](instructions.md)** | Upload to your AI project knowledge. Defines the data format and all session guidance. |
| **[alex-example-data.json](alex-example-data.json)** | Example data so you can see what a mapped system looks like. |

---

## Why I built this

IFS gave me a genuinely useful framework for understanding my inner world, but keeping track of it was hard. Insights from one session were forgotten by the next. Parts I had named would fade back into unnamed patterns. There was nowhere to hold the map.

team-sheet is that place. A single file, no server, no accounts. Your data stays on your machine. Pair it with an AI that has persistent project context and you have a reflective partner that remembers every part you have named, and can help you go deeper each time.

---

*companion to [character-sheet](../README.md), a gamified life dashboard built on the same local-first, AI-optional architecture. If team-sheet is Animal Crossing for understanding and befriending your inner world, character-sheet is Skyrim where you are the main character: for when you need some accountability, encouragement, and a quest log to help you lock in, level up, and solve your problems.*
