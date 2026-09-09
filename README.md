# Contra — The Devil's Advocate for Writers

> **English** | [中文](./README_CN.md)

**Publish nothing your harshest reader hasn't already attacked.**

Contra is a browser side panel that stress-tests your writing before you publish. Select any text — a Substack essay, a launch post, an opinion piece — and three independent adversarial AI cores go to work in parallel, streaming structured findings into red, amber, and green cards.

[![Manifest V3](https://img.shields.io/badge/Manifest-V3-blue)]() [![Chrome + Edge](https://img.shields.io/badge/Chrome%20%2B%20Edge-supported-4285F4)]() [![Price](https://img.shields.io/badge/Pro-%249%20lifetime-166534)]() [![Telemetry](https://img.shields.io/badge/telemetry-zero-b91c1c)]()

---

## The Three Editors

| Core | Role | Output |
|---|---|---|
| ⚔️ **Hostile Reviewer** | Finds the 3 most lethal logical breakpoints — the exact sentences a hostile expert reader would quote against you | Red cards, severity-rated |
| 🔍 **Blind-Spot Hunter** | Runs in parallel and *independently*: missing stakeholders, unexamined assumptions, counter-evidence from 2024–2026 | Amber cards with counter-evidence |
| 🛡️ **Steel-Man Rewriter** | Prebunks your weakest passages so opponents have nothing to grab | Green before/after rewrite cards |

The two analysis cores never see each other's output — genuine disagreement is the product. The rewriter anchors every fix to a specific flaw ID.

## Key Features

- **Parallel dual-core engine** with a synthesized steel-man pass — measurably more novel findings than asking a model directly (Framework Gain ≥ 1.5, enforced by our eval suite)
- **Stage-driven progress**: per-core elapsed timers, thinking-stage reassurance, skeleton cards — zero dead-screen anxiety
- **One-click export** of the full review as a `.txt` report
- **Bilingual UI** (English / 中文); review output follows the article's language
- **Works on any page**: full-text extraction (Readability) or select text → right-click → *Send selection to Contra*
- **First-run onboarding** gets you productive in 30 seconds

## Privacy by Architecture

- **BYOK** — bring your own API key: Anthropic, OpenAI, OpenRouter, DeepSeek, Qwen, Doubao, or Kimi. There is no Contra server; your text goes straight from your browser to the provider you chose.
- **Encrypted at rest** — keys are AES-GCM encrypted on your device; Pro adds an optional passphrase vault.
- **Zero telemetry** — no analytics, no tracking, no accounts.
- **One-click revoke** — wipe all local secrets instantly.

Details: [Privacy Policy](./PRIVACY.md)

## Pricing

**Free**: Hostile Reviewer core · all seven providers · 10 reviews/day
**Pro — $9 lifetime**: all three cores · unlimited reviews · custom endpoints · passphrase vault

One-time purchase. No subscription, no account. Checkout is handled by a compliant merchant of record (global cards, VAT included); you receive a license key by email and paste it into Settings → Activate Pro.

## Install

- **Chrome Web Store / Microsoft Edge Add-ons**: links coming soon (under review)
- **Manual (developer mode)**: download the latest release zip, unpack, then `chrome://extensions` → Developer mode → *Load unpacked*

## Development

Built with [WXT](https://wxt.dev/) + React 19 + TypeScript + Tailwind CSS v4.

```bash
npm install
npm run dev        # hot-reload side panel
npm run build      # chrome-mv3 production build
npm run build:edge # edge build
npx vitest run     # 190+ unit/contract tests
npm run eval       # quantitative engine eval (BYOK, writes eval/reports/)
```

The engine ships with a quantitative quality gate: LLM-as-Judge scoring, Claim Uniqueness Ratio, and anti-sycophancy quotas over a curated 6-case corpus — prompt changes must not regress the gate.

## License

Contra is commercial software. See [LICENSE](./LICENSE). The Baker Street methodology that inspired the engine is MIT-licensed upstream.

---

*Stop shipping arguments that fold at the first hostile comment. Run them through Contra first.*
