# 📊 B3 Shareholder Position Retrieval Tool

A **Streamlit web app** to automate the retrieval of **shareholder data** for Brazilian companies listed on **B3 (Brasil Bolsa Balcão)** using an uploaded Excel file. The app fetches data through B3's public API, processes it, and allows users to download the results in a well-formatted Excel sheet.

---

## 🎯 What It Does

1. 📤 **Upload** an Excel file with `Ticker` and `CVM Code` columns.
2. ✅ **Validates** rows (drops missing or invalid CVM Codes).
3. 🔗 **Encodes** the CVM Code to query B3’s **CompanyCall/GetListedFinancial API**.
4. 🌐 **Fetches shareholder data** for each ticker.
5. 🔎 **Filters out** the “Total” row to keep individual shareholder information.
6. 📊 **Displays a real-time progress bar** while processing each ticker.
7. 👁️ **Previews** the combined result inside the app.
8. 📁 **Generates a downloadable Excel file** with:
   - Merged and bold header: `Combined Shareholder Positions`
   - Columns: `Ticker`, `Name`, `%ON`, `%PN`
   - Auto-adjusted column widths

---

## 🧰 Tech Stack

| Component        | Technology                | Purpose                                      |
|------------------|---------------------------|----------------------------------------------|
| 🐍 Python         | Core Language             | Data handling, API calls, processing          |
| 🧾 Pandas         | DataFrame operations      | Read/write Excel, manipulate data             |
| 🔗 Requests       | HTTP Library              | Make API calls to B3                          |
| 🗂️ OpenPyXL       | Excel Formatting          | Format the downloadable Excel file            |
| 🧪 Base64 / UUID  | Utility Libraries         | Encode API payload, create unique filenames   |
| ⚙️ Streamlit      | Web Framework             | Interactive UI for file upload and download   |
| 📤 BytesIO        | In-Memory File I/O        | Handle Excel files without saving to disk     |

---

## 📂 Input Format

Uploaded Excel file must include the following columns:

| Ticker | CVM Code |
|--------|----------|
| PETR4  | 9512     |
| VALE3  | 9020     |

---

## 💾 Output Format

The resulting Excel file includes:

| Ticker | Name                     | %ON   | %PN   |
|--------|--------------------------|-------|-------|
| PETR4  | Government of Brazil     | 50.00 |       |
| PETR4  | BlackRock Inc.           | 2.34  | 1.22  |
| VALE3  | BNDES Participações S.A. | 10.20 |       |


---




## ⚙️ Demo

https://github.com/user-attachments/assets/83f8ab05-05c1-4248-b91e-59de5a9924a1




