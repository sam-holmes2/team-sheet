# AI Privacy Guide

This guide covers how the major AI providers handle your data: conversations, uploaded files, and exported JSON depending on the specific provider and plan you use. It focuses on privacy and sensitive data protection for personal use. This info is non-prescriptive. The goal is to give you the information you need to make your own informed decisions.

**Note on accuracy:** Privacy policies change. This guide reflects publicly documented policies as of early 2026. Verify current terms at each provider before making privacy-sensitive decisions that depend on them.

Provider privacy policies: [Anthropic](https://www.anthropic.com/privacy) | [OpenAI](https://openai.com/policies/privacy-policy) | [Google](https://policies.google.com/privacy) | [Mistral](https://mistral.ai/privacy-policy/) | [Ollama](https://ollama.com/privacy)

---

## The short version

If privacy matters to you, here is what to know:

- **Local models (Ollama, LM Studio):** Nothing you write ever leaves your device. This is the highest-privacy option. Setup takes about 10 minutes.
- **Cloud AI (Anthropic, OpenAI, Google, Mistral):** Your session content is sent to their servers and may be stored for weeks to years. Most providers let you opt out of training data use, but storage is separate from training.
- **API keys:** If you use the in-app cloud AI chat, your API key grants access to your account. Store it in a password manager (1Password, Bitwarden, Apple Passwords, etc.), not in a document or email. Never share it or paste it into websites you don't trust.

---

## Key terms

**Training on your data:** whether the provider uses your conversation content to improve their AI models. Opting out does not affect storage. These are two separate policies.

**Human review:** whether employees or contractors can read your conversations, typically for safety or quality purposes.

**Retention:** how long your data is stored on the provider's servers after a session ends.

**Zero Data Retention (ZDR):** a developer-tier option where inputs and outputs are not stored after processing. Only available via API, not consumer plans.

**Confidential computing / secure enclave:** hardware-enforced privacy where inference runs inside a Trusted Execution Environment (TEE) inaccessible even to provider staff. Offers cryptographic attestation rather than policy-based promises. Currently limited to open-source models.

**Memory:** a cross-conversation feature (now offered by most providers) that stores facts about you across sessions. This is a separate storage layer from conversation history, with its own settings and retention.

---

## Considerations worth knowing

**Your data.json is your most sensitive file.** It contains your full personal history accumulated across all previous sessions. Apply the same care to choosing where you send it as you would to the conversations themselves.

**Training and retention are separate policies.** Opting out of model training does not reduce how long your data is stored. A provider can commit to never training on your data while still retaining conversation logs for 30-90 days. ZDR (only available at API tier) is the only non-local option that addresses both.

**Memory features are a separate data layer.** All major providers now offer cross-conversation memory. These features create persistent storage distinct from conversation history, with their own retention timelines and potentially different training policies. Check and manage them separately from your main privacy settings.

**Project knowledge vs. conversation history.** Files you upload to AI projects (such as `instructions.md` and `data.json`) are stored separately from conversation messages and may have different retention policies. Review current terms for this storage type specifically.

**Browser extensions.** Extensions installed in your AI session browser can read everything you type and receive on that domain. A dedicated browser profile for AI sessions reduces this exposure.

**Network context.** On networks managed by an employer, school, or institution, TLS inspection may allow the network operator to log HTTPS traffic including AI conversations, regardless of the provider's own privacy policy.

**API key security.** Your API key is a password to your AI account. Anyone who has it can send requests and generate charges on your behalf. Keep it in a password manager. Rotate it (create a new one and delete the old one) if you think it may have been exposed.

---

## Comparison

Ordered from most to least data control. Rows within each tier are not meaningfully ranked.

| Tier | Provider + Plan | Training default | Opt-out available | Human review | Retention | Approx. cost |
|---|---|---|---|---|---|---|
| **Local** | Ollama | N/A. stays on device | N/A | Never | On device only | Free |
| **Local** | LM Studio | N/A. stays on device | N/A | Never | On device only | Free |
| **Confidential cloud** | Tinfoil, ExpressAI, NEAR Private Chat | Never | N/A | No (hardware-enforced) | Not stored (hardware-enforced) | Free to ~$20/mo |
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

## Confidential cloud providers

A newer category of consumer AI products built on hardware Trusted Execution Environments (TEEs). In standard cloud AI, privacy depends on the provider's policies and contractual promises. TEE-based services enforce isolation in hardware: the provider's own staff cannot access conversation content, and each inference can generate a cryptographic attestation signed by the CPU manufacturer (Intel or AMD) proving a specific, unmodified model ran in a genuine enclave. Some providers include browser-based tools to verify these attestations yourself.

**Current providers:**
- [Tinfoil](https://tinfoil.sh): consumer chat and API, iOS and web, $20/month. SOC 2 Type II. Open-source attestation verifier.
- ExpressAI (by ExpressVPN, launched March 2026): consumer chat using confidential enclaves, included with ExpressVPN Pro. [More info](https://www.expressvpn.com/blog/expressai-private-ai-platform/)
- [NEAR Private Chat](https://near.ai): uses Intel TDX and NVIDIA Confidential Computing. Open-source model focus.

This category is early-stage. New providers are appearing; search "confidential AI chat" to find current options.

**Limitations:**

**Frontier models are not available.** Claude, GPT-4, and Gemini cannot run in confidential infrastructure because their weights are proprietary. All current providers use open-source models: Llama, Gemma, Mistral, and similar. For IFS work in particular, the quality gap is worth weighing carefully. Open-source models handle structured tasks well but are not yet equivalent to frontier models for nuanced, emotionally complex material.

**Metadata is not protected.** Account details, IP address, and billing information are still collected and governed by standard privacy policies. Confidential computing protects conversation content, not identity. Third-party sub-processors for auth, billing, and infrastructure also receive some of this metadata.

**Trust shifts rather than disappears.** TEE attestation requires trusting the hardware manufacturer. Intel SGX and AMD SEV-SNP have had documented side-channel vulnerabilities. These are high-difficulty attacks rather than mass-exploitation threats, and providers mitigate against known vectors, but hardware isolation is not perfectly immune.

**Limited track record.** Most providers in this space are early-stage companies. SOC 2 certification and open-source verifiers are positive signals, but do not substitute for years of audited operation. Consider this alongside how sensitive your material is.

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
| Llama 3.2 3B | 3B | 4 GB | Compact, fast on any hardware |
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

---

## Backing up your data

`data.json` is the only file that contains your personal history. If you lose your device or clear browser storage, it is gone. Back it up.

| Approach | How | Privacy tradeoff | Best for |
|----------|-----|-----------------|----------|
| **AI project knowledge** | Keep the file in your AI project as part of the normal workflow | Sent to your AI provider (same exposure as your sessions) | Most users, already part of the workflow |
| **Local folder** | Copy `data.json` to a folder on your machine after each session | No exposure beyond your device | Maximum privacy, manual effort |
| **Encrypted cloud** | Upload to zero-knowledge cloud storage (e.g. Proton Drive, Tresorit) | Encrypted before leaving your device; provider cannot read it | Good balance of safety and convenience |
| **Standard cloud** | Upload to Google Drive, Dropbox, iCloud | Provider has access to plaintext content | Convenient, but exposes your map to that provider |
| **Password-locked export** | Enable password in the app, then back up the browser's localStorage via a browser profile backup | Encrypted on disk (AES-256-GCM) | Combined approach: cloud sync of browser profile stays encrypted |

**Practical recommendation:** the simplest safe approach is to keep a copy of `data.json` in a folder that is backed up by your chosen cloud provider, and to use the password lock if that provider's access to your inner world material is a concern. If you use Proton Drive or Tresorit, the file is encrypted client-side before upload. If you use Google Drive or iCloud, the file is readable by the provider.

**What does not need to be backed up:** `team-sheet.html` and `instructions.md` are identical for all users and can be re-downloaded from the GitHub repo at any time.
