# KassaBank-automates-reports.
Claude AI skill that automates daily cash and bank reports (KASA-BANKA) for hotel accounting in Uzbekistan.
# Kassa Automation 🧾🤖

A Claude skill that automates the **daily cash and bank report (KASA-BANKA workbook)** used in hotel accounting.

Every day, an accountant has to copy yesterday's workbook, paste in new bank statements, carry the closing balance forward, update the USD rate, and check that everything balances. This skill teaches an AI agent (Claude) to do the whole routine safely and consistently.

## ✨ What it does

1. Creates today's workbook from the latest one (the old file is never changed)
2. Reads new bank statements and puts each transaction on the correct account sheet
3. Updates each account's closing balance on the main `KASA-BANKA` sheet
4. Rolls the opening cash balance (`DEVREDEN KASA`) forward from yesterday's total
5. Fetches the official USD rate from the Central Bank of Uzbekistan (cbu.uz)
6. Keeps the daily payment and income formulas limited to *today's* activity
7. **Reconciles** the books: the bottom-up total must equal the top-down total in UZS, USD, EUR and RUB
8. Writes a short report of every change

## 🔒 Why the Excel file is edited as XML

Libraries like `openpyxl` delete embedded images, drawings and printer settings when they save a file. To avoid losing them, this skill treats the `.xlsx` file as a zip archive and changes only the exact cells it needs. It then checks that no media or settings were lost.

## 📂 Files

| File | Purpose |
|---|---|
| `SKILL.md` | The full instructions the AI agent follows |
| `README.md` | This description |

## 🚀 How to use

1. Install the skill in Claude (Claude Code or Claude Cowork).
2. In your **private** copy, replace the `<ACCOUNT_…>` and `<PATH_TO_PYTHON>` placeholders with your real values.
3. Type `/kassa` or ask: *"Prepare today's kassa."*

## ⚠️ Note

All bank account numbers and company names in this public version are **placeholders**. Real financial data should never be published.

## 👤 Author

**Bilol** — Accountant and Computer Science student at WIUT, Tashkent.
Built from a real daily workflow and improved through real mistakes.
