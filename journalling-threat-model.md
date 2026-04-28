# Session Threat Model

How private is your inner map, really? This document breaks down the trust and risk involved at each level of journalling, from pen and paper to frontier AI, and shows how team-sheet can fit into any of them.

---

## The levels

| Level | Method | Your data lives... | Who can read it | Risks | Controls | team-sheet fit |
|-------|--------|-------------------|-----------------|-------|----------|----------------|
| **0** | Pen and paper | On the physical page | Anyone who finds it | Loss, theft, physical discovery, no search/sync | Lock it away, hide it, destroy entries you don't want found | Use as inspiration for your sessions; the app structure can guide what to reflect on and track manually |
| **1** | Local digital (no AI) | On your device only | Anyone with device access | Device theft, no backups by default, loss if device fails | Full-disk encryption, strong login password, local backups | Store `team-sheet.html` locally; edit fields directly; import/export JSON manually; no internet required |
| **2** | Cloud storage (no AI) | On your device + provider servers | Provider (Google, iCloud, Dropbox...) + anyone who compromises your account | Provider access, account breach, government requests, terms-of-service changes | Strong password + 2FA, review provider privacy policy, end-to-end encrypted options (e.g. Cryptomator) | Store `team-sheet.html` in Google Drive or iCloud; syncs across devices while data stays in localStorage |
| **3** | AI-assisted (local model) | On your device only | Anyone with device access | Model capability limits (smaller parameter counts = less nuanced reflection), higher technical setup bar | Same as level 1; model weights stay local | Journal with a local LLM (e.g. [Ollama](https://ollama.com), LM Studio); paste AI output into team-sheet manually |
| **4** | AI-assisted (frontier model) | On your device + AI provider's servers | AI provider (Anthropic, OpenAI...) + anyone who compromises your account | Provider data retention, potential training data use, account breach, jurisdiction-dependent legal access | Opt out of training data in provider settings, review retention policy, use a pseudonym, keep entries vague | The default setup: journal with an AI using `instructions.md`; `data.json` lives in project knowledge |
| **5** | AI-assisted (frontier model + 3rd-party wrapper) | On your device + AI provider + 3rd-party app's servers | All of the above, plus the wrapper company | All level-4 risks, plus the wrapper storing your data independently, narrower control over how it's used | Read the wrapper's privacy policy carefully; prefer providers that are explicit about not storing journal content | Third-party apps built on frontier model APIs; team-sheet avoids this layer entirely |

---

## Notes on each level

### Level 0: Pen and paper
The gold standard for privacy by default: no network, no server, no account. The risk is entirely physical. A locked box, a fireproof safe, or simply being choosy about where you keep it covers most of the threat surface. The downside is massive friction to usage, no search, no AI reflection, no long-term pattern tracking.

### Level 1: Local digital, no AI
A plain text file, an offline app, or team-sheet with no AI connected. Full-disk encryption (FileVault on Mac, BitLocker on Windows) is the most important control. If someone steals your laptop, encryption is what stands between them and your inner map. Backups matter here: a local-only map lost to a hard drive failure is gone. For an extra layer, team-sheet's built-in password protection (Settings) encrypts all local data with AES-256-GCM so it is unreadable without your password even if someone has device access.

### Level 2: Cloud storage, no AI
Adds device sync and automatic backup at the cost of storing data on a provider's infrastructure. Google, Apple, and Dropbox all have privacy policies that grant them broad rights. End-to-end encrypted alternatives (Proton Drive, Cryptomator layer on top of any provider) close most of this gap. Government legal requests are a theoretical but real risk in some jurisdictions.

### Level 3: Local AI (e.g. Ollama, LM Studio)
Running a model locally means no data leaves your machine. The practical tradeoff is capability: models that run on consumer hardware (7B-34B parameters) are less nuanced than frontier models at deep reflection tasks, though the gap is narrowing quickly. Setup is more technical. This is the highest-privacy option that still gives you AI assistance.

### Level 4: Frontier AI (Claude, GPT-4, Gemini)
The most capable reflection partner available. The cost is trust: your session content travels to the provider's servers and is subject to their data retention and privacy policies. Most providers offer a way to opt out of using your data for model training. Find and enable this setting if it matters to you. Note that opting out of training doesn't necessarily mean your data isn't stored at all; the retention period and legal access policies are separate questions.

**What Anthropic says:** Claude has an opt-out for model training, but stored conversations are still retained according to their standard policy. Check [Anthropic's privacy policy](https://www.anthropic.com/privacy) for current details.

### Level 5: Frontier AI via 3rd-party apps
Apps that use frontier model APIs under the hood. You're trusting the AI provider *and* the app company. The app often stores your journal content in its own database for features like search and history. Check whether it does. team-sheet deliberately avoids this layer: it talks to no server, stores nothing remotely, and the only third party in the chain is the AI provider you choose.

---

## How team-sheet fits at each level

| Level | How to use it |
|-------|--------------|
| **0** | Browse Alex's demo, use the Map and Parts tab structure as inspiration for what to reflect on, journal on paper using the same categories |
| **1** | Download `team-sheet.html`, open locally in Firefox, use as a standalone offline tracker. Edit fields directly. No AI needed. |
| **2** | Store the file in Google Drive or iCloud to enable sync across devices |
| **3** | Journal with a local model (Ollama + Open WebUI); paste the AI's JSON output into team-sheet manually |
| **4** | The default setup: AI project + `instructions.md` + `data.json` in project knowledge |
| **5** | Use a journalling app that connects to a frontier model; import its output into team-sheet if it can produce compatible JSON |

---

## Quick reference: controls by threat

| Threat | Mitigation |
|--------|-----------|
| Physical discovery of journal | Lock/hide physical journal; consider what you write down |
| Device theft | Full-disk encryption + strong login password |
| Account compromise | Strong unique password + 2FA on AI provider account |
| AI provider trains on your data | Opt out in provider settings; use a pseudonym; use a local model |
| AI provider data retention | Review their privacy policy; prefer providers with short retention windows |
| Third-party app storing your data | Read the app's privacy policy; prefer apps that don't store session content server-side |
| Browser data loss | Export JSON regularly; keep a copy in AI project knowledge |

---

## A note on content sensitivity

The material in team-sheet is more sensitive than most personal data. A parts map can include exile-level content: old pain, shame, childhood wounds, significant life events, mental health information, and neurodivergence-related material. This content may be therapeutic in nature.

**This matters in two ways:**

**The stakes of exposure are higher.** A leaked character-sheet might reveal your goals and habits. A leaked team-sheet could reveal things you've never told anyone. Apply the same care to your `data.json` that you'd apply to therapy notes.

**Frontier AI sessions carry this weight too.** When you journal with an AI at level 4, you may share exile-level material in the course of the conversation. This content reaches the provider's servers, not just the JSON output. If this concerns you, consider a local model (level 3), a pseudonym, or staying at a more surface level with frontier AI and reserving deeper material for offline reflection.

---

*team-sheet is designed to give you as much control as possible: no server, no account, no telemetry. The AI layer is optional and entirely your choice. The more sensitive the material you bring to sessions, the more carefully you should choose your level.*

---

For a full provider-by-provider comparison (including how to disable training, data retention by plan, and how to run a local model), see [ai-privacy-guide.md](ai-privacy-guide.md).
