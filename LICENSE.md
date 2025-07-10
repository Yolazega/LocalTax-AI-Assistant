# 📜 LocalTax AI Assistant – License Strategy

This repository and concept combine open-source components with proprietary (closed-source) modules. This hybrid license strategy is intentional and must not be altered without the explicit consent of the project owner.

---

## ✅ 1️⃣ Open-Source Parts

The following components are released as **open-source** under the MIT License **or** Creative Commons BY-NC-SA 4.0, at the repository owner's choice:

- `/src/imap_email_reader.py` – Local IMAP email scanner and attachment downloader.
- `/src/ocr_parser.py` – Local OCR processing script (Tesseract-based).
- `/src/vector_store.py` – Local vector database integration (ChromaDB or FAISS).
- `/config.yaml` – Example configuration templates.
- `/requirements.txt` – Dependency list.
- General helper scripts that only handle parsing, local data storage, or basic API calls **excluding any core logic**.

Users are allowed to:
- Use, modify, and distribute these parts freely for personal and **non-commercial** use.
- Fork the repository and build extensions under the same open license.
- Submit improvements (pull requests) back to the repository.

---

## ✅ 2️⃣ Closed-Source Parts (Proprietary)

The following parts are **proprietary** and **NOT open-source**:

- `/src/wiso_mapper.py` – Contains smart field mapping logic that translates extracted data into correct tax form entries.
- `/src/rpa_auto_filler.py` – Contains RPA (Robotic Process Automation) logic that auto-fills tax forms in third-party tax software (WISO or equivalent).
- `/src/openai_proxy_trainer.py` – Contains any hybrid cloud-to-local training bridges that interact with external LLMs (OpenAI or other) for semantic tax logic.
- `/src/main.py` – If it combines proprietary orchestration logic.
- Any future modules or plugins that replicate or build upon the core matching, decision, or RPA logic.

These parts **remain the intellectual property of the project owner (Yolazega)**.

---

## ✅ 3️⃣ Restrictions

**You may NOT:**
- Copy, resell, sublicense, reverse-engineer, or redistribute the proprietary modules without explicit permission.
- Use the proprietary parts for any commercial service or integration without an official commercial license.
- Remove or alter any license statements or copyright notices.

---

## ✅ 4️⃣ Allowed Commercial Use (License Option)

If you wish to use the full system **including closed parts** for commercial purposes (e.g. as a SaaS, integrated product, or paid client service), you must obtain a valid commercial license directly from the owner:

**Contact:** [Your Business Email or Legal Entity Here]

Terms:
- Paid license fee (monthly, annual, or per-user basis)
- No resale or sublicensing without separate agreement
- Custom support and updates may be included case by case

---

## ✅ 5️⃣ Why Hybrid?

This hybrid model ensures:
- Transparency for developers and contributors.
- Trust in the open, inspectable parts.
- Protection of the unique business value and core tax automation flow that differentiates this project from generic tools.

---

## ✅ 6️⃣ Copyright

© 2024 Yolazega. All rights reserved.
Parts licensed under MIT or CC BY-NC-SA 4.0 where marked.
Proprietary parts remain fully protected by copyright and applicable trade secret law.

---

## ✅ 7️⃣ License Enforcement

Violations of this license may result in takedown requests, DMCA notices, or legal action. The project owner reserves the right to revoke access to proprietary modules if terms are breached.

---

## 📌 Summary

- **Open Parts:** Use freely, non-commercial.
- **Closed Parts:** Proprietary, must be licensed for commercial use.
- **Contact for commercial license:** [Your Contact Email]

---

## 📂 Suggestion for Repository Structure

/open/ → All open modules (IMAP, OCR, Vector)
/closed/ → Placeholder for closed modules (README only)
/docs/ → Full LICENSE.md and detailed usage rules

---

## 🔑 Final Note

This license file is part of every distribution and must stay attached to any fork, copy, or clone of the LocalTax AI Assistant project.

By cloning or using this repository you accept these conditions.

---

**End of License Statement** 