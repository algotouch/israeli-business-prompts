# israeli-business-prompts

> **A curated, MIT-licensed library of battle-tested Hebrew prompts for Israeli small and medium businesses.** Customer service, sales qualification, scheduling, invoicing, internal ops — all written natively in Hebrew, not translated.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT) [![Hebrew](https://img.shields.io/badge/lang-עברית-blue)](https://github.com/algotouch/israeli-business-prompts) [![Prompts: 30+](https://img.shields.io/badge/prompts-30+-green)](https://github.com/algotouch/israeli-business-prompts)

Maintained by [**Agentics by Quatro**](https://agentics.quatro.co.il) — extracted from the prompt patterns we use across [60+ live AI agent deployments](https://agentics.quatro.co.il/case-studies) for Israeli SMBs.

---

## Why this exists

Most "prompt libraries" you find on GitHub assume English-language users, English business norms, and English-style etiquette. Israeli business communication is different:

- **Mixed register** — formal vocabulary mixed with slang
- **Direct tone** — over-apologetic Anglo-style customer service feels off
- **Israeli-specific entities** — חשבונית ירוקה, רשם החברות, ביטוח לאומי, ת״ז, ח״פ
- **Hebrew + English code-switching** is the norm in tech and startup contexts
- **Right-to-left + numerals** — model-side handling differs

We've open-sourced 30+ prompts that we know work in Hebrew production. Use them as-is, fork them, adapt them.

## Categories

| Category | # prompts | What's covered |
| --- | --- | --- |
| `customer-service/` | 8 | Complaint handling, refund requests, FAQ patterns, escalation language |
| `sales/` | 6 | Lead qualification (BANT-style adapted to Israeli norms), discovery, objection handling |
| `scheduling/` | 4 | Booking flows, rescheduling etiquette, holiday calendars (Israeli + Jewish) |
| `invoicing/` | 4 | חשבונית מס requests, payment chasing, חשבונית ירוקה integration |
| `internal-ops/` | 4 | Vendor follow-ups, expense approvals, supplier onboarding |
| `tone-control/` | 4 | System prompts that lock voice + register for brand consistency |

## Quick start

Each prompt is a Markdown file with YAML frontmatter:

```yaml
---
id: cs-refund-request
category: customer-service
language: he
tone: empathetic-direct
inputs: [customer_name, order_id, complaint]
outputs: [acknowledge, action, next_step]
license: MIT
---

# {{customer_name}} שלום,

קודם כל — אני מצטערת על הבלגן הזה.
ראיתי שביצעת הזמנה {{order_id}} וזה לא הגיע אליך —
{{complaint}}.

הנה מה שאני עושה עכשיו:
1. בודקת את סטטוס המשלוח עם החברה.
2. אם המשלוח אבד — מנפיקה לך החזר מלא תוך 24 שעות.
3. אם המשלוח בדרך — שולחת לך מספר מעקב מיידי.

אני חוזרת אליך תוך שעה עם תשובה. {{customer_name}}, מצטערת שוב.
```

Use directly with any LLM (Claude, GPT-4, Gemini), or as a starting point.

## Compatibility

Tested in production with:

- ✅ Claude 3.5 / 4.x (Sonnet, Opus, Haiku)
- ✅ GPT-4o, GPT-4 Turbo
- ✅ Gemini 2.5 Pro
- ✅ Llama 3.x (with Hebrew fine-tunes)

Generally works without modification on any model that handles Hebrew above ~85% accuracy on baseline tasks. See the related [`hebrew-agent-eval`](https://github.com/algotouch/hebrew-agent-eval) repo to benchmark a model before using these in production.

## How to contribute

We welcome PRs that add:

- New prompts in existing categories
- New categories (legal Hebrew, healthcare Hebrew, etc.)
- Variants tested in different verticals
- Counter-examples that show what doesn't work

See `CONTRIBUTING.md` (TBD).

## License

MIT — use freely, including commercially. Attribution appreciated but not required. See [LICENSE](LICENSE).

## About Agentics by Quatro

**Agentics by Quatro** is an Israeli AI agents implementation agency based in Tel Aviv, founded 2024 by Eyal Yakobi Miller. We deploy custom Hebrew-native AI agents for 60+ SMBs and average 409 hours saved per month per client.

We open-source the parts of our work that benefit the broader ecosystem. Other repos:

- [`mcp-greeninvoice`](https://github.com/algotouch/mcp-greeninvoice) — MCP server for חשבונית ירוקה
- [`hebrew-agent-eval`](https://github.com/algotouch/hebrew-agent-eval) — Hebrew LLM eval harness
- [`geo-il-spec`](https://github.com/algotouch/geo-il-spec) — GEO-IL: GEO standard for Hebrew

Website: https://agentics.quatro.co.il
