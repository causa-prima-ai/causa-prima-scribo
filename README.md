<img width="3840" height="1920" alt="A5 _ Every surface_ one invoice (1)" src="https://github.com/user-attachments/assets/45e8cabd-9e60-4b61-aa8b-7bd405c60018" />

# Scribo
> Free, AI-native e-invoicing — every surface, one invoice.

## Contents

- [What is Scribo?](#what-is-scribo)
- [Demo](#demo)
- [Pick a surface](#pick-a-surface)
- [Compliance](#compliance)
- [FAQ](#faq)
- [Resources](#resources)
- [License](#license)

## What is Scribo?

Scribo is a free, conversational e-invoicing tool. Describe an invoice in plain language — "bill Acme GmbH €2,400 for May design work" — and it drafts a structured invoice for you to review, download and send directly.

Just ask your AI agent about Scribo: it ships as an MCP server, a CLI, and a Claude/Codex skill, alongside a public HTTP API and a web app. Free forever — no credit card. You just need a sender email.

**Built by Causa Prima** — Scribo is built by [**Causa Prima**](https://causaprima.ai/), a company building agentic AI for the CFO office. It's our first freely available skill — an early glimpse of what we're building.

## Demo
**Scribo as a skill - works for any Agent that can run the skill**

https://github.com/user-attachments/assets/107875e9-e717-40f5-bbc0-b2af0bd172fe

**As an MCP server — works in any MCP client**

https://github.com/user-attachments/assets/0fc8173b-50d4-4e06-84e8-9dea95af380f

Prefer the terminal, your own code, or a browser? See [Pick a surface](#pick-a-surface).

## Pick a surface

Every surface talks to the same backend and produces the same compliant invoices — pick the one that fits how you and your agents work.

| Options                                                                       | Best for                    | What you get |
| ----------------------------------------------------------------------------- | --------------------------- | ------------ |
| **[Skill](https://github.com/causa-prima-ai/scribo-skill)**       | Claude, ChatGPT & Codex     | A lightweight skill you add once — works across Claude Code, Claude.ai, Claude Desktop, ChatGPT, and the OpenAI Codex CLI through plain bash helpers. No server, no npm install. Just ask, and it drafts the invoice for you. |
| **[MCP server](https://github.com/causa-prima-ai/scribo-mcp)**    | AI assistants & IDE clients | A hosted Model Context Protocol endpoint at `scribo.causaprima.ai/mcp` — add the URL to Claude Desktop, Cursor, Cline, the ChatGPT App, or any MCP client and your assistant generates invoices right in the chat. Nothing to install or run locally. |
| **[CLI](https://github.com/causa-prima-ai/scribo-cli)**           | Terminals, scripts & CI     | The official npm package (`npm i -g @causaprima/scribo-cli`). `scribo create …` writes a finished invoice straight to a file, with sysexits-style exit codes that drop cleanly into shell scripts and pipelines. |
| **[HTTP API](https://github.com/causa-prima-ai/scribo-api-docs)** | Your own code               | The public REST contract every other surface is built on. POST a JSON payload, get back a compliant invoice (PDF + embedded XML) and a durable download URL. Anonymous, rate-limited, OpenAPI 3.1. |
| **[Web app](https://scribo.causaprima.ai)**                                   | A quick one-off             | No setup at all. Describe an invoice in your browser and download the PDF. |

## Compliance

Scribo emits invoices conforming to **EN 16931**, the European e-invoicing standard, with the relevant national CIUS. Every EN 16931 output (ZUGFeRD, XRechnung) is validated against the **Invopop**-hosted validator at generate-time — output that fails the rule set never reaches the user. US plain PDFs carry no EN 16931 XML and are rendered directly.

**Supported formats**

| Jurisdiction | Format | Status |
|---|---|---|
| Germany (B2B) | **ZUGFeRD** COMFORT (PDF/A-3 hybrid + CII XML) | ✅ Live |
| Germany (B2G) | **XRechnung** (UBL / CII) | ✅ Live |
| United States | Plain PDF (no XML, no e-invoice claim) | ✅ Live |
| France | **Factur-X** EN 16931 | 🔜 Coming soon |
| Spain | **Facturae** | 🔜 Coming soon |
| Belgium / NL / LU / AT | **Peppol BIS 3.0** UBL | 🔜 Coming soon |

*Disclaimer: Scribo generates and validates compliant invoice documents. It is **not tax or legal advice** — Scribo does not determine your tax obligations, VAT treatment, or filing requirements.*

## FAQ

<details>
<summary><strong>Is Scribo really free?</strong></summary>

Yes — free forever. No credit card, no subscription, no paywall before your first invoice. You just need a sender email.

</details>

<details>
<summary><strong>Do I need an account or signup?</strong></summary>

No signup form. On your first invoice, Scribo verifies the sender email — a 6-digit code (or one-click link) arrives at that address; one verification covers ~30 minutes of invoicing. The same email doubles as your magic-link login for re-downloads later.

</details>

<details>
<summary><strong>Which countries and formats are supported?</strong></summary>

Live today: **Germany** — ZUGFeRD (B2B) and XRechnung (B2G) — and the **United States** (plain PDF). Coming next: **France** (Factur-X), **Spain** (Facturae), and **Belgium / NL / LU / AT** (Peppol BIS 3.0).

</details>

<details>
<summary><strong>What does "EN 16931-compliant" actually mean here?</strong></summary>

Every EN 16931 output (ZUGFeRD, XRechnung) is validated against the **EN 16931-1:2017** rule set (via the Invopop-hosted validator) before it's returned. Output that fails validation never reaches you. US plain PDFs carry no EN 16931 XML, so no schematron validation applies.

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

- Skill (Claude / Codex) — [`scribo-skill`](https://github.com/causa-prima-ai/scribo-skill) · [docs](https://scribo.causaprima.ai/docs/skill)
- MCP server — [`scribo-mcp`](https://github.com/causa-prima-ai/scribo-mcp) · [docs](https://scribo.causaprima.ai/docs/mcp)
- CLI — [`scribo-cli`](https://github.com/causa-prima-ai/scribo-cli) · [docs](https://scribo.causaprima.ai/docs/cli)
- HTTP API — [`scribo-api-docs`](https://github.com/causa-prima-ai/scribo-api-docs) · [docs](https://scribo.causaprima.ai/docs/api)

## License

Proprietary — `UNLICENSED`. © Causa Prima Germany GmbH. All rights reserved. Distributed for use against the public Scribo API; not open-source. See [LICENSE](./LICENSE).
