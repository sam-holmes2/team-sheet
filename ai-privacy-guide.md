# AI Privacy Guide

This guide covers how each major AI provider handles your data: conversations, uploaded files, and exported JSON. It focuses on privacy and sensitive data protection.

The guide is factual and non-prescriptive. The goal is to give you the information you need to make your own informed choice about which setup to use.

**Note on accuracy:** Privacy policies change. This guide reflects publicly documented policies as of early 2025. Verify current terms at each provider before making decisions that depend on them.

---

## Key terms

**Training on your data:** whether the provider uses your conversation content to improve or fine-tune their AI models. Opting out of training does not affect data storage. These are two separate policies.

**Human review:** whether employees or contractors can read your conversations, typically for safety, quality assurance, or content moderation purposes.

**Retention:** how long your conversation data is stored on the provider's servers after a session ends. Separate from training.

**Zero Data Retention (ZDR):** a contract-level option (usually enterprise or API) where inputs and outputs are not stored after processing. The model still processes your data in memory to generate a response, but no log is written to disk.

**Jurisdiction:** the country or region whose laws govern your data. This affects your legal rights, what governments can compel, and what procedural requirements apply.

**HIPAA eligible:** whether the provider will sign a Business Associate Agreement (BAA), making them contractually bound to US healthcare data protection standards. Relevant in professional regulated contexts; not a requirement for personal use.

**Enterprise DPA:** a Data Processing Agreement, a contractual commitment specifying how the provider handles your data. Standard in business and enterprise tiers.

---

## Comparison: data handling

Ordered from most to least data control. Rows within each tier are not meaningfully ranked against each other.

| Tier | Provider + Plan | Used for training | Human review | Data retention | Zero retention option |
|---|---|---|---|---|---|
| **Local** | Ollama (any model) | Never: data never leaves device | Never | None. stays on device | N/A |
| **Local** | LM Studio | Never: data never leaves device | Never | None. stays on device | N/A |
| **Local** | Jan | Never: data never leaves device | Never | None. stays on device | N/A |
| **Local** | GPT4All | Never: data never leaves device | Never | None. stays on device | N/A |
| **ZDR / Enterprise cloud** | Anthropic API + Zero Data Retention | Never | No | Not stored (processed in memory only) | This is ZDR |
| **ZDR / Enterprise cloud** | OpenAI API + Zero Data Retention | Never | No | Not stored | This is ZDR |
| **ZDR / Enterprise cloud** | Claude on AWS Bedrock | Never | No | Configurable (30 days default) | Yes |
| **ZDR / Enterprise cloud** | Claude on Google Vertex AI | Never | No | Configurable (within your GCP project) | Yes |
| **ZDR / Enterprise cloud** | GPT-4 on Azure OpenAI | Never | No | 30 days default (configurable) | Yes |
| **ZDR / Enterprise cloud** | Gemini on Google Vertex AI | Never | No | Configurable (within your GCP project) | Yes |
| **Enterprise consumer** | Anthropic Claude.ai Enterprise | Never | No | Configurable (90 days default) | Available |
| **Enterprise consumer** | OpenAI ChatGPT Enterprise | Never | No | 90 days (configurable) | Available |
| **Standard API** | Anthropic API (standard, no ZDR) | Never | Possible (safety review) | 30 days | Upgrade to ZDR tier |
| **Standard API** | OpenAI API (standard, no ZDR) | Never | Possible (safety review) | 30 days | Upgrade to ZDR tier |
| **Standard API** | Mistral API | Never | No | 30 days | No |
| **Paid consumer** | Anthropic Claude.ai Team | Never | No | 90 days | No |
| **Paid consumer** | OpenAI ChatGPT Team | Never | No | Until deleted | No |
| **Paid consumer** | Google Workspace + Gemini | Never (for foundational model training) | No | Per Workspace retention policy | No |
| **Paid consumer** | Anthropic Claude.ai Pro | Opt-out available | Possible | 30 days minimum | No |
| **Paid consumer** | OpenAI ChatGPT Plus | Opt-out available | Possible | Until deleted | No |
| **Paid consumer** | Mistral Le Chat Pro | Opt-out available | Possible | 30 days | No |
| **Paid consumer** | Google Gemini Advanced | Opt-out available | Yes (explicitly stated in policy) | 18 months default | No |
| **Free** | Google AI Studio (API prototyping) | May be used to improve services | Possible | Varies | No |
| **Free** | Anthropic Claude.ai Free | Opt-out available | Possible | 30 days minimum | No |
| **Free** | OpenAI ChatGPT Free | Opt-out available | Possible | Until deleted | No |
| **Free** | Mistral Le Chat Free | On by default (opt-out available) | Possible | 30 days | No |
| **Free** | Google Gemini Free | On by default (opt-out available) | Yes (explicitly stated in policy) | 18 months default | No |

---

## Comparison: jurisdiction, protections, and cost

Same row order as the table above. Prices are approximate as of early 2025 and subject to change.

| Provider + Plan | Jurisdiction / Infrastructure | HIPAA eligible | Enterprise DPA | Approx. cost |
|---|---|---|---|---|
| Ollama (any model) | Your device | N/A | N/A | Free |
| LM Studio | Your device | N/A | N/A | Free (personal use) |
| Jan | Your device | N/A | N/A | Free |
| GPT4All | Your device | N/A | N/A | Free |
| Anthropic API + ZDR | US (AWS infrastructure) | Eligible | Available | Usage-based |
| OpenAI API + ZDR | US | Eligible | Available | Usage-based |
| Claude on AWS Bedrock | Your chosen AWS region | Eligible | Amazon's DPA | Usage-based |
| Claude on Google Vertex AI | Your chosen GCP region | Eligible with BAA | Google Cloud DPA | Usage-based |
| GPT-4 on Azure OpenAI | Your chosen Azure region | Eligible with BAA | Microsoft DPA | Usage-based |
| Gemini on Google Vertex AI | Your chosen GCP region | Eligible with BAA | Google Cloud DPA | Usage-based |
| Anthropic Claude.ai Enterprise | US (AWS) | Yes, BAA available | Yes | Custom pricing |
| OpenAI ChatGPT Enterprise | US (options vary) | Yes, BAA available | Yes | Custom pricing |
| Anthropic API (standard) | US (AWS) | No | No | Usage-based |
| OpenAI API (standard) | US | No | No | Usage-based |
| Mistral API | EU (France) | No | GDPR-covered | Usage-based |
| Anthropic Claude.ai Team | US (AWS) | No | No | ~$30/user/mo |
| OpenAI ChatGPT Team | US | No | No | ~$25/user/mo |
| Google Workspace + Gemini | US (configurable) | Eligible | Google Workspace DPA | $14-28/user/mo (add-on) |
| Anthropic Claude.ai Pro | US (AWS) | No | No | ~$20/mo |
| OpenAI ChatGPT Plus | US | No | No | ~$20/mo |
| Mistral Le Chat Pro | EU (France) | No | GDPR-covered | ~€15/mo |
| Google Gemini Advanced | US/EU | No | No | ~$20/mo (via Google One) |
| Google AI Studio (API prototyping) | US | No | No | Free (with rate limits) |
| Anthropic Claude.ai Free | US (AWS) | No | No | Free |
| OpenAI ChatGPT Free | US | No | No | Free |
| Mistral Le Chat Free | EU (France) | No | GDPR-covered | Free |
| Google Gemini Free | US/EU | No | No | Free |

---

## Notes on specific providers

### Anthropic

**Training opt-out (Claude.ai Free and Pro):**
Settings > Privacy Controls > turn off "Improve Claude for everyone". This stops your data from being used for training. It does not affect storage or retention.

**Zero Data Retention (API):**
Anthropic's ZDR tier means inputs and outputs are not logged after processing. The model still processes your data in memory during the session, but nothing is written to storage afterward. ZDR is available to API customers. Check the Anthropic API console or contact their sales team for current eligibility requirements.

**Project knowledge vs. conversation history:**
When using AI projects with persistent context, files you upload (including `instructions.md` and `data.json`) are stored as "project knowledge", which may have different retention policies than conversation history. Review current terms specifically for this storage type.

**Memory feature:**
The "Memory" feature, if enabled, stores facts about you across conversations. This is a separate storage layer from conversation history, with its own retention timeline. Manage it separately in Settings > Memory.

**Subprocessor:**
Anthropic's infrastructure runs on Amazon Web Services. Your data physically sits on Amazon's hardware even when using Anthropic's service directly.

**AWS Bedrock:**
Accessing Claude through AWS Bedrock applies Amazon's data processing terms rather than Anthropic's consumer terms. Amazon commits to not using customer data to train models.

---

### OpenAI

**Training opt-out (ChatGPT Free and Plus):**
Settings > Data Controls > turn off "Improve the model for everyone".

**API training policy:**
OpenAI has committed since March 2023 to not using API inputs and outputs to train or improve their models by default.

**Memory feature:**
ChatGPT's "Memory" feature, if enabled, stores facts about you across conversations. Manage it separately in Settings > Personalization > Memory.

**Azure OpenAI:**
Accessing GPT-4 through Azure applies Microsoft's enterprise data processing terms. Microsoft commits to not using customer data for training, and data stays in your chosen Azure region.

---

### Google

**Gemini Apps Activity:**
The primary privacy control for Gemini Free and Gemini Advanced. Turn it off in Gemini settings or via My Activity > Gemini Apps Activity. When off, conversations are not saved to your account and are not used for training.

**Human review:**
Google's policy explicitly states that trained reviewers may read Gemini conversations to improve the product. This is more explicit than most providers. Turning off Gemini Apps Activity reduces but may not eliminate this.

**Retention:**
Gemini defaults to 18 months of conversation history. This can be reduced to 3 months or disabled in Google activity settings.

**Vertex AI:**
A separate enterprise product from the Gemini consumer offerings. Customer data is not used to train Google's foundational models. Data stays within your GCP project and region.

**AI Studio:**
Google's prototyping API environment. Data handling is substantially less restrictive than Vertex AI and is not intended for sensitive personal content.

---

### Mistral

**EU jurisdiction:**
Mistral is a French company. Data is stored in the EU under French and EU law, including GDPR. EU residents have stronger statutory rights (access, rectification, erasure) and government access requires compliance with EU legal process, which carries stricter procedural requirements than US process.

**API:**
Not used for training by default. 30-day retention. GDPR gives EU residents the right to request erasure.

---

### Local models (Ollama, LM Studio, Jan, GPT4All)

No conversation data leaves your device. Model weights are downloaded from provider servers on first use: the provider can see which models you downloaded, but not conversation content. After download, all inference runs offline.

Conversation data is stored locally in the application's files or database, subject to your device's own security controls rather than any provider's policies.

---

## Setting up Ollama for local sessions

Ollama is a tool for running AI language models on your own computer. Once a model is downloaded, it runs fully offline with no network connection required.

### Hardware requirements

Models are stored and run at 4-bit quantization by default in Ollama, so memory requirements are roughly 4-5 GB per 7 billion parameters. The figures below reflect this.

| Hardware | Models that fit comfortably | Notes |
|---|---|---|
| Apple Silicon (M1/M2/M3/M4), 8 GB RAM | 7B-8B | Good performance. unified memory used efficiently by Metal |
| Apple Silicon, 16 GB RAM | up to 14B | Comfortable for mid-range models |
| Apple Silicon, 32 GB RAM | up to 34B | High capability |
| Apple Silicon, 48 GB+ RAM | 70B | Near-frontier output quality |
| NVIDIA GPU, 8 GB VRAM (RTX 3060/4060 class) | 7B-8B | Windows or Linux |
| NVIDIA GPU, 16 GB VRAM (RTX 3080 class) | up to 14B | |
| NVIDIA GPU, 24 GB VRAM (RTX 3090/4090 class) | up to 34B | |
| NVIDIA GPU, 48 GB VRAM | 70B | |
| CPU only (no discrete GPU) | 3B-7B | Functional but slow for interactive use |

Higher parameter counts generally produce more nuanced, contextually aware responses but require more memory and run more slowly. A 14B model running at a comfortable speed will often be more useful in practice than a 70B model running so slowly that conversation flow breaks.

### Model options for reflective and journalling sessions

The following models perform well at nuanced contextual conversation and structured JSON output. The field moves quickly; newer releases may outperform what is listed here.

| Model | Size | Min memory | Notes |
|---|---|---|---|
| Llama 3.1 8B | 8B | 8 GB | Meta's capable baseline. good instruction following |
| Gemma 2 9B | 9B | 8 GB | Google's efficient model. strong at nuanced text |
| Mistral 7B Instruct | 7B | 8 GB | Good at structured output and instruction following |
| Qwen 2.5 14B | 14B | 16 GB | Strong reasoning and complex contextual prompts |
| Phi-4 | 14B | 16 GB | Microsoft's efficient model. strong performance for its size |
| Mistral Small 3.1 | 22B | 24 GB | Strong balance of quality and speed |
| Llama 3.3 70B | 70B | 48 GB | Closest to frontier model quality. requires high-end hardware |

The gap between a 7B local model and a frontier model is meaningful for deep reflective work: local models are less nuanced, less consistent at following complex instructions, and more prone to missing subtle context. The gap narrows significantly as model size increases toward 70B.

### Installation

**Step 1. Install Ollama**

Download from [ollama.com](https://ollama.com) and install. Ollama runs as a background service and provides a local API at `localhost:11434`. No account or login required.

**Step 2. Download a model**

Open Terminal and run:

```
ollama pull llama3.1
```

Replace `llama3.1` with any model name from the table above. Examples:

```
ollama pull gemma2:9b
ollama pull qwen2.5:14b
ollama pull phi4
```

The download happens once per model. After that, the model is available offline.

**Step 3. Test in terminal**

```
ollama run llama3.1
```

Opens a basic chat prompt. Type a message and press Enter. Type `/bye` to exit.

**Step 4. (Optional) Open WebUI: a full browser-based chat interface**

Open WebUI provides a browser interface similar to a commercial AI chat product, with conversation history, model switching, and file upload. It runs entirely on your machine via Docker.

Requirements: [Docker Desktop](https://www.docker.com/products/docker-desktop/) installed and running.

```
docker run -d \
  -p 3000:8080 \
  --add-host=host.docker.internal:host-gateway \
  -v open-webui:/app/backend/data \
  --name open-webui \
  --restart always \
  ghcr.io/open-webui/open-webui:main
```

Open `http://localhost:3000` in your browser after the container starts. Conversation history is stored in a local Docker volume on your machine.

**Important:** Use the locally hosted version via Docker, not the cloud-hosted version at `openwebui.com`. The hosted version sends conversations to their servers.

**Step 5. Using with this app**

Local models do not maintain persistent project context between sessions the way cloud AI projects do. To give the model the information it needs each session:

- Paste the contents of `instructions.md` at the start of your conversation, or upload it as a file if using Open WebUI.
- Paste your current `data.json` when you want the model to update it.
- At the end of the session, ask for an updated JSON block. Copy it and import it into the app using the import button.

This workflow is more manual than a persistent cloud AI project, but the output format is identical.

### What Ollama sends externally

| Action | Data sent externally |
|---|---|
| Installing Ollama | Downloaded from ollama.com. no conversation data |
| Pulling a model | Model name sent to ollama.com to retrieve the file. no conversation data |
| Running a model | Nothing. inference is entirely local |
| Open WebUI via local Docker | Nothing. runs entirely on your machine |
| Open WebUI at openwebui.com | Conversation data sent to their servers |

Ollama does not send telemetry about your conversations. The only external communications are model file downloads.

---

## Additional considerations

These factors are less obvious but affect how private your sessions actually are in practice.

### Training and retention are separate policies

Opting out of model training does not reduce how long your data is stored on the provider's servers. A provider can commit to never training on your data while still retaining conversation logs for 30-90 days for safety, debugging, or legal compliance purposes. Zero Data Retention (ZDR) is the only option that addresses both.

### Memory features as a separate data layer

Several providers offer cross-conversation memory that stores facts about you persistently across sessions. These features create a storage layer distinct from conversation history, with their own retention timelines and potentially different training policies. Check and manage them separately from your main privacy settings.

### Project knowledge vs. conversation history

In AI projects with persistent context, files you upload are stored as "project knowledge" rather than conversation messages. The retention policy for project knowledge may differ from conversation history. Your `data.json`, uploaded as project knowledge, is the most sensitive file in this workflow: it contains your full personal history across all sessions.

### System prompts as data

`instructions.md`, when uploaded to project knowledge or pasted as a system prompt, also reaches the provider's servers. It contains app framing and no personal content, but it is still data subject to the provider's policies.

### Clipboard exposure

When you copy your `data.json` to paste into an AI conversation, the full JSON sits in your clipboard. Browser extensions with clipboard or "read all site data" permissions can access it. Other apps on your system may also read clipboard contents silently.

### Browser extensions

Extensions installed in the browser you use for AI sessions can read everything you type and receive on that domain. Extensions with broad permissions are a data leakage vector that bypasses provider policies entirely. A separate browser profile or dedicated browser for AI sessions reduces this exposure.

### Corporate and institutional networks

On networks managed by an employer, school, or institution, SSL inspection may be active. This allows the network operator to decrypt and log HTTPS traffic, including AI conversations. This applies regardless of which provider you use and regardless of the provider's own privacy policy. Local models running on personal hardware avoid this entirely.

### Managed devices

Devices enrolled in employer or institutional device management (MDM) may have monitoring software installed: screen recording, keystroke logging, or screenshot capture. These can capture AI sessions regardless of which provider you use. Local models do not help here if the device itself is being monitored.

### Subprocessors

AI providers typically run on third-party cloud infrastructure. Anthropic uses AWS; OpenAI uses Microsoft Azure; most others use one of the three major clouds. Your data physically sits on that infrastructure provider's hardware even when you are interacting with the AI provider directly. Enterprise plans usually include explicit contractual commitments about which subprocessors have access.

### Legal access

Governments can compel providers to produce user data through legal process: subpoenas, court orders, national security letters. The applicable legal process depends on the jurisdiction where data is stored and where the provider is incorporated. Providers operating under EU law face stricter procedural requirements and stronger user protections than those solely under US law. Providers with ZDR carry no stored conversation data to hand over. Local models carry none at all.

### Right to deletion

Under GDPR (EU residents) and similar laws in other jurisdictions, you have the right to request deletion of your personal data from a provider's systems. Most providers have a data deletion request process. Timelines for deletion vary and may not cover all backup systems immediately.

### Third-party app wrappers

Apps that appear to be standalone journalling or reflection tools may be wrappers around frontier model APIs. They may store your conversation content in their own database independently of the underlying AI provider's data handling. The relevant privacy policy to check is the app's own policy, not just the underlying model provider's.

### The exported JSON as data

When you export your full `data.json` to paste into an AI session, you are sending your complete personal history in that file. The file contains everything accumulated across all previous sessions. This is worth bearing in mind when choosing which provider or tier to use for sessions involving your most sensitive material.

---

*Verify current policies at each provider before making privacy-sensitive decisions.*

Provider privacy policies: [Anthropic](https://www.anthropic.com/privacy) | [OpenAI](https://openai.com/policies/privacy-policy) | [Google](https://policies.google.com/privacy) | [Mistral](https://mistral.ai/privacy-policy/) | [Ollama](https://ollama.com/terms)
