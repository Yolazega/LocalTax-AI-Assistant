# 📘 LocalTax AI Assistant – Full Concept (ENGLISH)

## ✅ Project Vision

The LocalTax AI Assistant is a fully local, privacy-first tax automation pipeline for freelancers and small business owners who want maximum control over their sensitive tax data. The system combines local OCR parsing, an AI-powered conversational logic layer, smart matching with bank statements, and automatic form-filling for tax software (e.g. WISO). All core intelligence runs on your local hardware: Jetson Orin NX + a high-performance PC.

## 🔒 Key Objective

To replace unreliable, expensive tax advisors with a personal assistant that:

* Learns your tax logic over time (through local examples and Cloud coaching)
* Matches invoices and payments automatically
* Fills tax software fields automatically
* Stays 100% offline and encrypted

## ⚙️ Core Features

1️⃣ **IMAP Email Reader**

* Connects locally to your email inbox.
* Downloads PDF/JPG attachments tagged with custom filters (date range, subject keywords).

2️⃣ **OCR Parser**

* Uses Tesseract to scan invoices and receipts.
* Saves text results to your local `/data` folder.

3️⃣ **Vector Store + Memory**

* Saves all scanned documents and extracts semantic data.
* Stores tax contexts ("Laptop for home office", "Partial private use").

4️⃣ **Hybrid Cloud Coaching**

* Uses ChatGPT or other LLM via API for deep tax rules.
* Sends anonymized prompts only (no names, no IDs).
* Stores every new answer locally for future use.

5️⃣ **Matching Engine**

* Cross-checks scanned invoices with bank statement CSVs.
* Matches payments within date range and fuzzy amount tolerance.
* Links invoice to payment with timestamped memory.

6️⃣ **WISO Mapper**

* Maps structured results (category, deduction percent, tax code) to the correct WISO input fields.
* Remembers previous mappings to automate future ones.

7️⃣ **RPA Auto Filler**

* Uses PyAutoGUI or Selenium to input data into WISO's GUI automatically.
* Can run headless or with user supervision.

8️⃣ **Master Runner (`main.py`)**

* One single command to run the entire pipeline.
* User selects tax year dynamically.
* Pipeline filters emails + files for that year only.

## 📂 Folder Structure

```
/LocalTax-AI-Assistant
│
├── /data
│   ├── incoming_emails/
│   ├── receipts/
│   ├── account_statements/
│   ├── memory_vectors/
│   ├── mobile_uploads/
├── /src
│   ├── imap_email_reader.py
│   ├── ocr_parser.py
│   ├── vector_store.py
│   ├── openai_proxy_trainer.py
│   ├── wiso_mapper.py
│   ├── rpa_auto_filler.py
│   └── main.py
├── config.yaml
├── requirements.txt
└── README.md
```

## 🔑 Privacy & Data Security

* All processing is local by default.
* Data is encrypted with VeraCrypt/BitLocker.
* No cloud storage unless you choose to back up.

## ✅ Advantages

* Fully local: You control 100% of the tax data.
* Flexible: Adjust date ranges, filters, categories anytime.
* Saves time: No more repetitive manual input.
* Learns your patterns: The more you use it, the smarter it gets.

## 🧩 Example Use Case

> User receives a PDF invoice by email ➜ The IMAP reader downloads it ➜ OCR parser scans it ➜ Vector store matches it to a payment ➜ OpenAI trainer clarifies tax logic ➜ Mapper prepares WISO fields ➜ RPA auto-fills ➜ User checks and submits via ELSTER.

## ✅ Deployment

* Runs on Jetson Orin NX + PC (Ryzen 7 + RTX GPU).
* Python 3.11+ required.
* Easy to extend: Add modules for new countries, new forms.

## ⚙️ Requirements

* Python, LangChain, ChromaDB/FAISS, pytesseract, Selenium, PyAutoGUI.
* Secure IMAP credentials.

## ⚡ Licensing

* MIT or CC BY-NC-SA 4.0 for open-source use.
* Commercial use only with permission.

## 📱 Mobile Capture Module – Extension for LocalTax AI Assistant

### 📲 Mobile Upload Workflow (Optional)

**What it does:**

* Users can snap photos of receipts, restaurant bills, or other expenses directly on their smartphone.
* Images are temporarily stored in a user-chosen cloud folder (e.g., Google Drive, iCloud, Nextcloud) or sent by email to a dedicated inbox.
* The LocalTax AI Assistant pulls these images from the cloud folder or email inbox and processes them **locally only**.
* OCR scanning, classification, matching to bank statements, and WISO field mapping are done fully **offline** on the Jetson/PC setup.
* The cloud or email is only a temporary transit point. Users remain in control and can delete photos anytime.

### ✅ Why this works

✔️ Adds real-world flexibility for business trips and daily expenses.
✔️ Keeps sensitive tax data local — only the image is in transit.
✔️ Users can decide case by case which receipts to upload immediately and which to handle at home.

### 📁 How it fits in the Blueprint

* **New source folder:** `/data/mobile_uploads/`
* **Optional sync script:** Watches your cloud folder and copies new images locally.
* **Same OCR module:** Processes mobile images just like email attachments.
* **Same matching logic:** Connects receipts to payments and maps fields automatically.

**Result:** One seamless workflow covering both email and on-the-go scanning — without sacrificing local privacy.

✅ Added to the core concept!

## 🚀 Next Step

Push this repo to GitHub, adjust `config.yaml` with your IMAP and OpenAI keys, run `main.py` — and let your taxes manage themselves!

**End of Concept Summary.**
