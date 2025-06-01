# 🧾 AI Invoice – GPT-4o Powered Invoice Automation

AI Invoice is a Python-based system that automates invoice extraction, analysis, and reporting using **OpenAI GPT-4o**, **Pandas**, and **Excel**. It processes multiple invoice PDFs, extracts key financial data, summarizes insights, and generates a structured Excel report—all in seconds.

---

## 🚀 Features

- 🔍 Extract structured invoice data using GPT-4o vision + JSON mode  
- 📊 Perform revenue, tax, and net income analysis with Pandas  
- 📈 Auto-generate Excel reports with charts and monthly breakdowns  
- ⚙️ Async multi-invoice processing for faster batch performance  
- ✅ Data validation using Pydantic for schema consistency  

---

## 📁 Project Structure

```bash
├── app/
│   ├── config.py         # Configurations (e.g. paths, company name)
│   ├── extraction.py     # GPT-4o logic for image → JSON data
│   ├── processing.py     # Validation, analysis, and Excel reporting
│   ├── prompt.py         # Structured system prompt for GPT-4o
│   └── main.py           # Async pipeline orchestration
├── data/invoices/        # Place your PDF invoices here
├── .env.example          # Template for environment variables
````

---

## ⚙️ Setup & Installation

### 🔐 Prerequisites

* Python 3.11+
* [Poetry](https://python-poetry.org/) package manager

### 📦 Install Dependencies

```bash
poetry install
```

### 🔧 Environment Setup

Copy the example env and update your OpenAI API key:

```bash
cp .env.example .env
```

Edit `.env` to include:

```
OPENAI_API_KEY=your_openai_key
```

---

## ▶️ Running the App

1. Set your company name and data paths in `config.py` (for classifying incoming/outgoing invoices).
2. Place PDF invoices into `data/invoices/`.

Run the processing pipeline:

```bash
poetry run process-invoices
```

Output: an Excel report with two sheets (`Invoices` and `Summary`) in under 15 seconds.

---

## 🛠 Tech Stack

* 🔮 [OpenAI GPT-4o](https://openai.com/gpt-4o) (Vision + JSON mode)
* 🧠 [Pydantic](https://docs.pydantic.dev) (Validation)
* 📊 [Pandas](https://pandas.pydata.org/) (DataFrame operations)
* 📁 [xlsxwriter](https://xlsxwriter.readthedocs.io/) (Excel report generation)
* 🧵 Async I/O with `asyncio` and `tqdm.asyncio` for parallel PDF processing

---

## 📌 Example Output

**Extracted JSON (GPT-4o):**

```json
{
  "invoice_number": "DT-45678",
  "invoice_date": "2024-01-07",
  "issuer": { "name": "DevTools Pro", ... },
  "recipient": { "name": "TechNova Solutions", ... },
  "invoice_items": [...],
  "subtotal": 10500.00,
  "tax": 866.25,
  "total": 11366.25
}
```

**Generated Excel Report:**

* `Invoices` sheet: Raw structured data
* `Summary` sheet: Revenue, Expenses, Net Income, Tax + Monthly Chart

---

## 📂 Use Cases

* Invoice automation for finance/admin teams
* Expense/revenue analytics for small businesses
* Document parsing base for AI back-office automation

---

## 🧠 Extendability

This system is easily extendable to:

* Timesheet processing
* Purchase order analysis
* Receipt digitization
* Contract parsing
---
