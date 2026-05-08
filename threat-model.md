# Threat Model: team-sheet

_Last reviewed: 2026-05-08_

This document covers residual security risks that cannot be fully eliminated by the app — risks the user should be aware of. IFS sessions can involve sensitive personal material, so understanding these risks is especially important.

---

## 1. Cloud AI provider receives your IFS session data

**When it applies:** Whenever you use an Anthropic (Claude) model in the in-app chat.

**What is sent:** A summary of your parts map — parts, connections, session notes, memories, and your conversation messages. This goes to Anthropic's servers and is subject to [Anthropic's privacy policy](https://www.anthropic.com/privacy).

**How to avoid it:** Use a local Ollama model instead. Ollama runs entirely on your device and sends nothing to any server. The app prompts you to acknowledge this before opening cloud chat for the first time, and shows a persistent warning banner while a cloud model is active.

---

## 2. GitHub receives your encrypted backup

**When it applies:** When you use the Sync feature to push a backup to GitHub.

**What is sent:** An AES-256-GCM encrypted blob. Your plaintext data and your password never leave your device — only the ciphertext is transmitted.

**Risk:** GitHub (and anyone who gains access to your repo) holds the encrypted blob. It cannot be read without your password. Use a fine-grained GitHub Personal Access Token scoped only to the backup repository.

---

## 3. Other local HTML files can read unencrypted data

**When it applies:** When no security password is set and you open another HTML file from your local filesystem.

**What it means:** When the app runs as a `file://` page, all local HTML files share the same storage namespace. A malicious local file (e.g. something downloaded and opened) could read your parts map, session notes, and API key from storage.

**How to eliminate it:** Set a security password in Settings. This encrypts everything in storage — no other local file can read it without the password. Given the sensitivity of IFS data, this is strongly recommended.

---

## 4. Content Security Policy is not enforced locally

**When it applies:** When running the app as a local `file://` page (which is the normal use case).

**What it means:** The CSP header in the file restricts outbound connections to only the expected endpoints (Anthropic, GitHub, Ollama, GitHub raw content). Browsers enforce this policy when the app is served over HTTPS (e.g. the demo site), but not for `file://` pages. Locally, the enforcement comes from the app's own code rather than the browser's CSP.

**Practical impact:** Low. The app makes no outbound calls except the ones described in risks 1 and 2 above, and only when you explicitly trigger them.
