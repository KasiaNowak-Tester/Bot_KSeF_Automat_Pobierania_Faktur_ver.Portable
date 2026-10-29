# KSeF Invoice Bulk Downloader Bot (Portable UI Automation)

## 📌 Project Overview
This project is an automated, production-ready **RPA (Robotic Process Automation)** tool developed in **JavaScript (Node.js)**. It is designed to automate the manual verification and bulk downloading of financial PDF invoices from the Polish National e-Invoices System (**KSeF - Krajowy System e-Faktur**) based on data provided in an external Excel spreadsheet.

Instead of using direct API integrations, this bot performs **UI Automation** via an automated Chrome instance, simulating real user interactions (data entry, form submission, and navigation) to retrieve secure governmental documents. Distributed as a zero-installation, portable application, it can be executed seamlessly on any Windows workstation via a simple batch script (`.bat`).

---

## ⚡ Key Technical Features
*   **Dynamic Data Ingestion:** Automates file-system checks to detect first-time runs, programmatically generating a structured data template (`SZABLON_KSEF.xlsx`) directly in the user's Downloads folder.
*   **UI Automation Framework:** Launches and drives a dedicated, automated Google Chrome browser instance to interact with the web interface, execute searches, and trigger file streams.
*   **Smart Duplicate Prevention (Caching Logic):** Optimizes execution speed and server load by performing local disk lookups. The bot automatically identifies and skips already downloaded invoices, avoiding redundant requests.
*   **Fault Tolerance & Error Logging:** Engineered with a resilient exception-handling workflow. If a data mismatch occurs (e.g., incorrect invoice amount or malformed Tax ID), the bot bypasses the faulty record without crashing and compiles a detailed error report (`bledne_faktury_log.txt`).
*   **Automated Storage Pipeline:** Automatically manages directories, creating output folders (`/faktury_pdf/`) and mapping individual server PDF streams into clean local file paths.

---

## 🛠️ Technology Stack & Architecture

*   **Runtime Environment:** Node.js (packaged into a standalone, portable binary executable architecture).
*   **Automation Engine:** JavaScript (utilizing headless/headful browser control structures to drive the Chrome instance).
*   **Execution Layer:** Windows Batch Scripting (`Uruchom_Bota.bat`) used as a lightweight wrapper to trigger the Node.js runtime environment without requiring local IDE installations.
*   **Data Parsing:** Excel stream reader capable of parsing multi-column financial ledgers (`.xlsx` architecture).

---

## ⚙️ How It Works (Technical Workflow)
1.  **Initialization:** The batch script triggers the environment. On the first run, the system deploys a clean Excel data schema to the local system path.
2.  **File Selection:** Utilizes a standard Windows OS file dialog window allowing the user to select the populated ledger.
3.  **UI Navigation & Execution:** The bot spins up the browser, parses rows line-by-line, populates input fields (Invoice Number, KSeF ID, Tax ID, Amounts), and executes submissions.
4.  **Verification & Downstream:** Validates web responses. Successful matches trigger automatic downloads into `/faktury_pdf/`, while execution anomalies are appended to the error logs.

---

### 👤 Contact & Author
*   Full contact details (Email/Phone) are available in my attached CV
*   **Role Focus:** QA Engineer | UI Automation & Low-Code Developer
