# Contra Privacy Policy

**Last updated: 2026-09-04**

Contra ("the extension") is a writing-review tool built on a simple principle: **your words and your credentials never touch a server we operate, because we operate none.** This policy describes exactly what the extension stores, what it sends, and to whom.

## 1. What We Collect

**Nothing.** Contra collects no personal data, no usage statistics, no analytics, no crash reports, and no telemetry of any kind. There is no Contra backend.

## 2. Bring Your Own Key (BYOK)

Contra calls large-language-model APIs using **your own API key**, from your own browser.

- Your API key is stored **only on your device**, in the extension's local storage area.
- At rest, the key is encrypted with **AES-GCM-256** using a key derived via PBKDF2 (SHA-256, 100,000 iterations). Plaintext keys are never written to storage.
- Your key is transmitted **only to the official API domain of the provider you selected** (e.g. `api.anthropic.com`, `api.openai.com`). This is enforced in code, not just promised in prose: the extension refuses to construct a provider whose endpoint is not https and not an official domain.
- **Custom endpoints** (Pro feature): if you explicitly configure and confirm a third-party endpoint, your key is sent to that endpoint — over https only. The confirmation dialog states this plainly before you can proceed. This is your explicit choice; the default never changes silently.

## 3. Text You Review

Text you select for review is sent directly from your browser to the LLM provider you configured, under your own API account and that provider's privacy policy. It is not sent anywhere else. Selecting a different provider changes the destination — nothing else receives it.

## 4. Pro License Validation

If you activate Pro, the extension sends **your license key — and nothing else —** to `live.dodopayments.com` (Dodo Payments, our payment processor) to validate it. The validation result is cached locally and silently revalidated at most once every 7 days. No device identifiers, browsing data, or reviewed text are included in this request.

## 5. Local Encryption: Honest Boundaries

We believe in stating security boundaries truthfully rather than overselling them.

- **Default mode (device-bound):** the encryption key is derived from your extension ID and browser user agent. This protects your API key against **other software on your machine silently reading the extension's storage** (e.g. malware dumping `chrome.storage`). It does **not** protect against an attacker who has debugging access to your browser or full control of your user account — such an attacker could derive the same key.
- **Passphrase mode (Pro):** the encryption key is derived from a passphrase you choose. The passphrase is **never stored anywhere**; without it, no software on your machine — including Contra itself — can decrypt your keys. If you forget the passphrase, stored keys cannot be recovered.

## 6. One-Click Revocation

The settings panel includes a **"Revoke and clear all"** button. It wipes every locally stored secret — all provider API keys and the cached license — from your device, and returns the extension to its unconfigured state. To complete a revocation, also delete the key in your provider's dashboard; the extension will remind you of this.

## 7. Permissions

| Permission | Why |
|---|---|
| `storage` | Store your encrypted key, settings, and daily quota locally |
| `activeTab` | Read the text you explicitly select on the current page |
| `sidePanel`, `contextMenus` | Show the review UI and the right-click menu entry |
| Content script on all pages (`<all_urls>`) | Statically injected page-extraction helper (Readability full-text parsing and selection reading). It only runs in response to your explicit action — clicking "read selection" / "read full page", or the right-click menu entry. It collects and transmits nothing on its own. |
| Host permissions: `api.anthropic.com`, `api.openai.com`, `openrouter.ai`, `api.deepseek.com`, `dashscope.aliyuncs.com`, `ark.cn-beijing.volces.com`, `live.dodopayments.com` | Allow BYOK requests to connect directly from the extension to the official API domains of the six supported providers (avoiding browser CORS restrictions), plus license validation with our payment processor (Dodo Payments). No data is sent to any other host, and nothing is collected by us. |

The extension makes no connections other than those described in Sections 2–4. **Custom endpoints** (Pro) are not covered by the host permissions above: calls to a user-configured endpoint rely on that endpoint's own CORS support.

## 8. Changes

Any future change to this policy will ship with the extension and update the date above. Since we collect nothing, there is nothing to retroactively change our minds about.

## 9. Contact

Questions about this policy: open an issue on the project repository linked from the store listing.
