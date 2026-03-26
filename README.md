# 🍁 CRA Tax Optimization AI Agent

An n8n-powered conversational AI agent that helps Canadians optimize their taxes using CRA 2024/2025 rules — runs entirely on free-tier infrastructure.

---

## What it does

Ask it anything about your Canadian tax situation and it will:

- Calculate your federal + provincial tax across all 13 provinces/territories
- Model RRSP, TFSA, and FHSA contribution strategies based on your income bracket
- Flag the 2024 capital gains inclusion rate change (2/3 above $250K)
- Advise incorporated professionals on salary vs dividend splits
- Reference the correct CRA form or publication for every strategy

---

## Stack

`n8n` · `OpenAI GPT-4o-mini` · `Window Buffer Memory` · `Google Sheets` · `Webhook`

---

## How it works

```
Chat Trigger → AI Agent (CRA system prompt)
                    ├── calculate_canadian_tax      (federal brackets, RRSP savings, effective rate)
                    ├── get_provincial_tax_brackets (all provinces, 2024 rates)
                    └── get_cra_contribution_limits (RRSP, TFSA, FHSA, CPP, EI, capital gains)
```

The agent maintains conversation memory, asks for province + filing status upfront, and always attaches a disclaimer to recommend professional advice.

---

## Setup

1. Import `cra-tax-agent.json` into n8n (Workflows → Import from file)
2. Add your OpenAI API credential to the Chat Model node
3. Activate and open the chat interface — that's it

> Self-hosted n8n is free with no execution limits. The only cost is OpenAI API usage (~$0.01–0.03 per conversation).

---

## Limitations

- Federal estimates only — provincial tax is provided as a reference rate, not a full calculation
- CRA brackets are hardcoded for 2024/2025 and must be manually updated each spring
- Not a substitute for professional tax advice

---

*Built by [Ikechukwu Miller](https://github.com/Ikechukwu50) · Nigeria 🇳🇬*
