<img width="3840" height="1920" alt="A _ Split _ EU compliance-led" src="https://github.com/user-attachments/assets/32f6078b-a54f-47f5-94fb-0adea2454558" />

# Scribo — free, AI-native e-invoicing

EN 16931-compliant e-invoices (XRechnung, ZUGFeRD, Factur-X, Peppol BIS UBL, Spanish Facturae) plus plain US PDF — generated from any LLM, CLI, or the web. No signup, no paywall. The sender's email is the login.

[**Try it now → scribo.causaprima.ai**](https://scribo.causaprima.ai)

> Scribo is the public e-invoicing product from [Causa Prima](https://causaprima.ai). This repo is the brand hub: read on for the right surface to use, then jump to a focused repo.

## Pick a surface

| You want… | Use | Repo |
|---|---|---|
| To generate invoices from Claude Desktop, Cursor, Cline, ChatGPT App | **MCP server** (hosted) | [`scribo-mcp`](https://github.com/causa-prima-ai/scribo-mcp) |
| To generate invoices from Claude Code or Codex CLI | **Skill** | [`scribo-skill`](https://github.com/causa-prima-ai/scribo-skill) |
| To generate invoices from a terminal or a shell script | **CLI** _(planned — track the repo)_ | [`scribo-cli`](https://github.com/causa-prima-ai/scribo-cli) |
| To call the HTTP API directly from your own code | **API** | [`scribo-api-docs`](https://github.com/causa-prima-ai/scribo-api-docs) |
| To click a button and download a PDF | **Web app** | [scribo.causaprima.ai](https://scribo.causaprima.ai) |

## Why Scribo exists

German e-invoicing went mandatory for B2B in 2025 (Wachstumschancengesetz, §14 UStG). The EU is rolling out ViDA and Peppol mandates across member states. Most freelancers and micro-SMBs don't know — and the existing tools are either accountant-grade ERP or hand-rolled PDFs that don't validate.

Scribo's bet: if e-invoicing is now infrastructure, it should be free, conversational, and reachable from any AI assistant. So we ship every surface as a separately-indexed open repo, with one hosted backend behind them.

## Built by Causa Prima

Scribo is the first publicly distributed product from [Causa Prima](https://causaprima.ai), the agentic-AI CFO office for pre-seed/seed startups. The Scribo surface repos are open-source MIT. The hosted service and the Causa Prima platform behind it are proprietary.

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

MIT.
