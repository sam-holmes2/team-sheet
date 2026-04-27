# AI Privacy Guide

This guide covers how the major AI providers handle your data: conversations, uploaded files, and exported JSON depending on the specific provider and plan you use. It focuses on privacy and sensitive data protection for personal use. This info is non-prescriptive. The goal is to give you the information you need to make your own informed decisions.

**Note on accuracy:** Privacy policies change. This guide reflects publicly documented policies as of early 2026. Verify current terms at each provider before making privacy-sensitive decisions that depend on them.

Provider privacy policies: [Anthropic](https://www.anthropic.com/privacy) | [OpenAI](https://openai.com/policies/privacy-policy) | [Google](https://policies.google.com/privacy) | [Mistral](https://mistral.ai/privacy-policy/) | [Ollama](https://ollama.com/privacy)


---

## Key terms

**Training on your data:** whether the provider uses your conversation content to improve their AI models. Opting out does not affect storage. These are two separate policies.

**Human review:** whether employees or contractors can read your conversations, typically for safety or quality purposes.

**Retention:** how long your data is stored on the provider's servers after a session ends.

**Zero Data Retention (ZDR):** a developer-tier option where inputs and outputs are not stored after processing. Only available via API, not consumer plans.

**Memory:** a cross-conversation feature (now offered by most providers) that stores facts about you across sessions. This is a separate storage layer from conversation history, with its own settings and retention.

---

## Considerations worth knowing

**Your data.json is your most sensitive file.** It contains your full personal history accumulated across all previous sessions. Apply the same care to choosing where you send it as you would to the conversations themselves.

**Training and retention are separate policies.** Opting out of model training does not reduce how long your data is stored. A provider can commit to never training on your data while still retaining conversation logs for 30-90 days. ZDR (only available at API tier) is the only non-local option that addresses both.

**Memory features are a separate data layer.** All major providers now offer cross-conversation memory. These features create persistent storage distinct from conversation history, with their own retention timelines and potentially different training policies. Check and manage them separately from your main privacy settings.

**Project knowledge vs. conversation history.** Files you upload to AI projects (such as `instructions.md` and `data.json`) are stored separately from conversation messages and may have different retention policies. Review current terms for this storage type specifically.

**Browser extensions.** Extensions installed in your AI session browser can read everything you type and receive on that domain. A dedicated browser profile for AI sessions reduces this exposure.

**Network context.** On networks managed by an employer, school, or institution, TLS inspection may allow the network operator to log HTTPS traffic including AI conversations, regardless of the provider's own privacy policy.

---

## Comparison

Ordered from most to least data control. Rows within each tier are not meaningfully ranked.

| Tier | Provider + Plan | Training default | Opt-out available | Human review | Retention | Approx. cost |
|---|---|---|---|---|---|---|
| **Local** | Ollama | N/A. stays on device | N/A | Never | On device only | Free |
| **Local** | LM Studio | N/A. stays on device | N/A | Never | On device only | Free |
| **ZDR (developer API)** | Anthropic API + ZDR | Never | N/A | No | Not stored | Usage-based |
| **ZDR (developer API)** | OpenAI API + ZDR | Never | N/A | No | Not stored | Usage-based |
| **Standard API** | Anthropic API | Never | N/A | Possible (safety review) | 30 days | Usage-based |
| **Standard API** | OpenAI API | Never | N/A | Possible (safety review) | 30 days | Usage-based |
| **Paid consumer** | Anthropic Claude Pro | On by default | Yes | Possible | 5 years (opted in) or 30 days (opted out) | ~$20/mo |
| **Paid consumer** | OpenAI ChatGPT Plus | On by default | Yes | Possible | Until deleted | ~$20/mo |
| **Paid consumer** | Google AI Pro | On by default | Yes | Yes (explicitly stated) | 18 months default | ~$20/mo |
| **Paid consumer** | Mistral Le Chat Pro | On by default | Yes. Pro includes No Telemetry Mode | Possible | Until deleted | ~$15/mo |
| **Free** | Anthropic Claude Free | On by default | Yes | Possible | 5 years (opted in) or 30 days (opted out) | Free |
| **Free** | OpenAI ChatGPT Free | On by default | Yes | Possible | Until deleted | Free |
| **Free** | Google Gemini Free | On by default | Yes | Yes (explicitly stated) | 18 months default | Free |
| **Free** | Mistral Le Chat Free | On by default | Yes (less accessible than Pro) | Possible | Until deleted | Free |

Enterprise and API-only options (AWS Bedrock, Google Vertex AI, Azure OpenAI, Claude for Work, ChatGPT Enterprise) offer stronger controls including configurable retention and no training.

---

## Notes on specific providers

### Anthropic

**Training policy change (September 2025):**
Anthropic updated their consumer terms in September 2025. Training is now on by default for Free, Pro, and Max plans. Prior to this, the default was opted out. Users who accepted the updated terms without changing the toggle were opted in automatically. To check or change your current setting: Settings > Privacy Controls > "Improve Claude for everyone".

**Retention:**
Tied to training choice. Opted in: up to 5 years in de-identified training pipelines. Opted out: 30-day retention. This two-tier system was introduced with the September 2025 policy change.

**Memory:**
Claude Memory launched for Pro and Max users in October 2025. It is opt-in. Once enabled, it stores facts about you across conversations in a separate storage layer. Manage it in Settings > Memory. Team and Enterprise plans have separate memory controls.

**API:**
API usage is governed by commercial terms and is not affected by the September 2025 consumer policy change. API data is never used for training by default.

---

### OpenAI

**Training opt-out:**
Settings > Data Controls > turn off "Improve the model for everyone". Applies to ChatGPT Free and Plus. Temporary Chat sessions are never stored or used for training.

**Retention:**
Conversations are kept until you delete them. Deleted conversations are purged within 30 days.

**Memory:**
ChatGPT Memory is on by default for Plus users (rolled out May 2025). It stores facts about you across conversations and persists until explicitly cleared. Manage it in Settings > Personalization > Memory.

**API:**
OpenAI does not train on API inputs and outputs by default.

---

### Google

**Training and review opt-out:**
Turn off Gemini Apps Activity at myaccount.google.com > Data and Privacy > Gemini Apps Activity. When off, future conversations are not saved to your account and not used for training. Note: conversations that have already been reviewed by human reviewers may be retained for up to 3 years and are not retroactively deleted.

**Human review:**
Google's policy explicitly states that trained reviewers may read Gemini conversations to improve the product. This is more explicit than most other providers.

**Retention:**
18 months by default. Adjustable to 3 months, or you can disable history entirely.

**Personal Intelligence (2026):**
In early 2026, Google introduced "Personal Intelligence": Gemini's cross-app access to your Gmail, Drive, Maps, and other Google services, enabled by default for US users. This substantially expands what Gemini can access and process. It is managed separately from Gemini Apps Activity.

**Plan name:**
Google AI Pro (formerly Gemini Advanced) is the paid consumer tier, ~$19.99/month.

---

### Mistral

**Training opt-out:**
All plans: Settings toggle labeled "Allow your interactions to be used to train our models". Le Chat Pro additionally includes No Telemetry Mode, a stronger option that disables all data collection beyond what is needed to serve the request.

**Retention:**
Conversations are retained until you delete them or delete your account. (Earlier documentation cited 30 days; the current policy stores data until deletion.)

**EU jurisdiction:**
Mistral is a French company. Data is stored in the EU under GDPR. EU residents have stronger statutory rights, and government data access requires compliance with EU legal process.

---

## Local models (Ollama, LM Studio)

No conversation data leaves your device. Model weights are downloaded once from provider servers; the provider can see which models you downloaded but not conversation content. All inference runs offline after download.

**Important: Ollama cloud models.** Ollama v0.12 (April 2025) added cloud-hosted models to the Ollama interface alongside local ones. If you select a cloud model, your prompts are sent to Ollama's servers. To maintain local privacy, only use models that are listed as downloaded locally.

---

### Hardware requirements
Ollama runs AI models on your own computer, fully offline after a one-time model download.


Models run at 4-bit quantization by default in Ollama, so memory requirements are roughly 4-5 GB per 7 billion parameters.

| Hardware | Models that fit | Notes |
|---|---|---|
| Apple Silicon (M1-M4), 8 GB RAM | 7B-8B | Good performance via Metal |
| Apple Silicon, 16 GB RAM | up to 14B | Comfortable |
| Apple Silicon, 32 GB RAM | up to 34B | High capability |
| Apple Silicon, 48+ GB RAM | 70B | Near-frontier quality |
| NVIDIA GPU, 8 GB VRAM | 7B-8B | Windows or Linux |
| NVIDIA GPU, 16 GB VRAM | up to 14B | |
| NVIDIA GPU, 24 GB VRAM | up to 34B | |
| CPU only | 3B-7B | Functional but slow |

### Recommended models

| Model | Size | Min RAM | Notes |
|---|---|---|---|
| Llama 3.2 3B | 3B | 4 GB | Compact. fast on any hardware |
| Llama 3.1 8B | 8B | 8 GB | Good general capability |
| Gemma 2 9B | 9B | 8 GB | Strong at nuanced text |
| Qwen 2.5 14B | 14B | 16 GB | Strong reasoning |
| Phi-4 | 14B | 16 GB | Efficient for its size |
| Llama 3.3 70B | 70B | 48 GB | Closest to frontier quality |

### Installation

**1. Install Ollama**
Download from [ollama.com](https://ollama.com) and install. No account required.

**2. Download a model**
```
ollama pull llama3.1
```
```
ollama pull qwen2.5:14b
```
The download happens once. After that, the model runs fully offline.

**3. Run a session**
```
ollama run llama3.1
```
For a browser-based chat interface similar to commercial AI products, [Open WebUI](https://github.com/open-webui/open-webui) can be run locally via Docker. All data stays on your machine.

**4. Using with this app**
Local models do not maintain persistent project context between sessions. At the start of each session, paste `instructions.md` and your current `data.json`. At the end, copy the updated JSON block and import it into the app. The workflow is more manual but the output format is identical.
