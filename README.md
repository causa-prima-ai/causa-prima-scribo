<img width="3840" height="1920" alt="A5 _ Every surface_ one invoice (1)" src="https://github.com/user-attachments/assets/45e8cabd-9e60-4b61-aa8b-7bd405c60018" />

# Scribo
> Free, AI-native e-invoicing — every surface, one invoice.

## Contents

- [What is Scribo?](#what-is-scribo)
- [Pick a surface](#pick-a-surface)
- [Compliance](#compliance)
- [FAQ](#faq)
- [Resources](#resources)
- [License](#license)
- [Previous README](#previous-readme)

## What is Scribo?

Scribo is a free, conversational e-invoicing tool. Describe an invoice in plain language — "bill Acme GmbH €2,400 for May design work" — and it drafts a structured invoice for you to review, download and send directly.

Just ask your AI agent about Scribo: it ships as an MCP server, a CLI, and a Claude/Codex skill, alongside a public HTTP API and a web app. Free forever — no credit card. You just need a sender email.

**Built by Causa Prima** — Scribo is built by [**Causa Prima**](https://causaprima.ai/), a company building agentic AI for the CFO office. It's our first freely available skill — an early glimpse of what we're building.

## Pick a surface

Every surface talks to the same backend and produces the same compliant invoices — pick the one that fits how you work.

| Surface | Best for | What you get |
|---|---|---|
| **[Skill](https://github.com/causa-prima-ai/causa-prima-scribo-skill)** | Claude, ChatGPT & Codex | A lightweight skill you add once — works across Claude Code, Claude.ai, Claude Desktop, ChatGPT, and the OpenAI Codex CLI through plain bash helpers. No server, no npm install. Just ask, and it drafts the invoice for you. |
| **[MCP server](https://github.com/causa-prima-ai/causa-prima-scribo-mcp)**<br>hosted at `scribo.causaprima.ai/mcp` | AI assistants & IDE clients | A hosted Model Context Protocol endpoint — add one URL to Claude Desktop, Cursor, Cline, the ChatGPT App, or any MCP client and your assistant generates invoices right in the chat. Nothing to install or run locally. |
| **[CLI](https://github.com/causa-prima-ai/causa-prima-scribo-cli)**<br>`npm i -g @causaprima/scribo-cli` | Terminals, scripts & CI | The official npm package. `scribo create …` writes a finished invoice straight to a file, with sysexits-style exit codes that drop cleanly into shell scripts and pipelines. |
| **[HTTP API](https://github.com/causa-prima-ai/causa-prima-scribo-api-docs)** | Your own code | The public REST contract every other surface is built on. POST a JSON payload, get back a compliant invoice (PDF + embedded XML) and a durable download URL. Anonymous, rate-limited, OpenAPI 3.1. |
| **[Web app](https://scribo.causaprima.ai)** | A quick one-off | No setup at all. Describe an invoice in your browser and download the PDF. |

## Compliance

Scribo emits invoices conforming to **EN 16931**, the European e-invoicing standard, with the relevant national CIUS. Every invoice is validated against the **Invopop**-hosted EN 16931 validator at generate-time — output that fails the rule set never reaches the user.

**Supported formats**

| Jurisdiction | Format | Status |
|---|---|---|
| Germany (B2B) | **ZUGFeRD** COMFORT (PDF/A-3 hybrid + CII XML) | ✅ Live |
| Germany (B2G) | **XRechnung** (UBL / CII) | ✅ Live |
| United States | Plain PDF (no XML, no e-invoice claim) | ✅ Live |
| France | **Factur-X** EN 16931 | 🔜 Coming soon |
| Spain | **Facturae** | 🔜 Coming soon |
| Belgium | **Peppol BIS 3.0** UBL | 🔜 Coming soon |

*Disclaimer: Scribo generates and validates compliant invoice documents. It is **not tax or legal advice** — Scribo does not determine your tax obligations, VAT treatment, or filing requirements.*

## FAQ

<details>
<summary><strong>Is Scribo really free?</strong></summary>

Yes — free forever. No credit card, no subscription, no paywall before your first invoice. You just need a sender email.

</details>

<details>
<summary><strong>Do I need an account or signup?</strong></summary>

No signup form. Scribo uses a magic-link login: you provide a sender email (which the invoice needs anyway), confirm via a one-time link, and you're in.

</details>

<details>
<summary><strong>Which countries and formats are supported?</strong></summary>

Live today: **Germany** — ZUGFeRD (B2B) and XRechnung (B2G) — and the **United States** (plain PDF). Coming next: **France** (Factur-X), **Spain** (Facturae), and **Belgium** (Peppol BIS 3.0).

</details>

<details>
<summary><strong>What does "EN 16931-compliant" actually mean here?</strong></summary>

Every invoice is validated against the **EN 16931-1:2017** rule set (via the Invopop-hosted validator) before it's returned. Output that fails validation never reaches you.

</details>

<details>
<summary><strong>Is the US version compliant?</strong></summary>

Yes. There is no US e-invoicing mandate, so Scribo produces a fully compliant plain PDF.

</details>

<details>
<summary><strong>Does Scribo give tax or legal advice?</strong></summary>

No. Scribo generates and validates compliant invoice *documents*. It does not determine your tax obligations, VAT treatment, or filing requirements.

</details>

<details>
<summary><strong>How do AI agents / LLMs use Scribo?</strong></summary>

Scribo is built to be operated by an agent. It ships as an **MCP server**, a **CLI**, and a **Claude/Codex skill**, plus a public **HTTP API** and a **web app** — all on the same backend. An agent can discover Scribo, create an invoice, and return the file on a user's behalf.

</details>

<details>
<summary><strong>Who builds Scribo?</strong></summary>

[Causa Prima](https://causaprima.ai/) — a company building agentic AI for the CFO office. Operated by Causa Prima Germany GmbH, Munich.

</details>

## Resources

- **Web app** — [scribo.causaprima.ai](https://scribo.causaprima.ai)
- **Documentation** — [scribo.causaprima.ai/docs](https://scribo.causaprima.ai/docs)
- **Compliance & trust** — [scribo.causaprima.ai/compliance](https://scribo.causaprima.ai/compliance)
- **Causa Prima** — [causaprima.ai](https://causaprima.ai)

**Other Scribo surfaces**

- Skill (Claude / Codex) — [`causa-prima-scribo-skill`](https://github.com/causa-prima-ai/causa-prima-scribo-skill) · [docs](https://scribo.causaprima.ai/docs/skill)
- MCP server — [`causa-prima-scribo-mcp`](https://github.com/causa-prima-ai/causa-prima-scribo-mcp) · [docs](https://scribo.causaprima.ai/docs/mcp)
- CLI — [`causa-prima-scribo-cli`](https://github.com/causa-prima-ai/causa-prima-scribo-cli) · [docs](https://scribo.causaprima.ai/docs/cli)
- HTTP API — [`causa-prima-scribo-api-docs`](https://github.com/causa-prima-ai/causa-prima-scribo-api-docs) · [docs](https://scribo.causaprima.ai/docs/api)

## License

Proprietary — `UNLICENSED`. © Causa Prima Germany GmbH. All rights reserved. Distributed for use against the public Scribo API; not open-source. See [LICENSE](./LICENSE).

---

## Previous README

> **Note:** This repo's README is being migrated to Scribo's shared structure (consistent title, shared sections, and per-surface sections). The content below is the previous README, preserved verbatim — minus the header visual, which now sits at the top of this page. The sections above are being filled in from it.

<details>
<summary>Show previous README</summary>

# Scribo — free, AI-native e-invoicing

EN 16931-compliant e-invoices (XRechnung, ZUGFeRD, Factur-X, Peppol BIS UBL, Spanish Facturae) plus plain US PDF — generated from any LLM, CLI, or the web. No signup, no paywall. The sender's email is the login.

[**Try it now → scribo.causaprima.ai**](https://scribo.causaprima.ai)

> Scribo is the public e-invoicing product from [Causa Prima](https://causaprima.ai). This repo is the brand hub: read on for the right surface to use, then jump to a focused repo.

## Pick a surface

| You want… | Use | Repo |
|---|---|---|
| To generate invoices from Claude Desktop, Cursor, Cline, ChatGPT App | **MCP server** (hosted) | [`scribo-mcp`](https://github.com/causa-prima-ai/causa-prima-scribo-mcp) |
| To generate invoices from Claude Code or Codex CLI | **Skill** | [`scribo-skill`](https://github.com/causa-prima-ai/causa-prima-scribo-skill) |
| To generate invoices from a terminal or a shell script | **CLI** _(planned — track the repo)_ | [`scribo-cli`](https://github.com/causa-prima-ai/causa-prima-scribo-cli) |
| To call the HTTP API directly from your own code | **API** | [`scribo-api-docs`](https://github.com/causa-prima-ai/causa-prima-scribo-api-docs) |
| To click a button and download a PDF | **Web app** | [scribo.causaprima.ai](https://scribo.causaprima.ai) |

## Why Scribo exists

German e-invoicing went mandatory for B2B in 2025 (Wachstumschancengesetz, §14 UStG). The EU is rolling out ViDA and Peppol mandates across member states. Most freelancers and micro-SMBs don't know — and the existing tools are either accountant-grade ERP or hand-rolled PDFs that don't validate.

Scribo's bet: if e-invoicing is now infrastructure, it should be free, conversational, and reachable from any AI assistant. So we ship every surface as a separately-indexed public repo, with one hosted backend behind them.

## Built by Causa Prima

Scribo is the first publicly distributed product from [Causa Prima](https://causaprima.ai), the agentic-AI CFO office for pre-seed/seed startups. The Scribo repos and the hosted service behind them are proprietary — © Causa Prima Germany GmbH, all rights reserved.

## Status

| Surface | Status |
|---|---|
| Web app | ✅ Live |
| Public HTTP API | ✅ Live |
| MCP server (hosted) | ✅ Live |
| Claude / Codex skill | ✅ Available |
| CLI (npm) | 🚧 Planned |
| ChatGPT GPT, Gemini Gem, Poe bot | 🚧 Planned |

## License

Proprietary — © Causa Prima Germany GmbH. All rights reserved. See [LICENSE](./LICENSE).

</details>
