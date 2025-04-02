# 🚀 Voice Bot Invoice & Forecast System

![n8n](https://img.shields.io/badge/Built%20with-n8n-blue?style=flat&logo=n8n) 
![Google Sheets](https://img.shields.io/badge/Uses-Google%20Sheets-brightgreen?style=flat&logo=google-sheets)
![AI-Powered](https://img.shields.io/badge/Powered%20by-DeepSeekAI-orange?style=flat&logo=ai)

🔊 **Voice-Powered AI Assistant** that generates **invoices** 📜, retrieves **logistics data** 📦, and performs **predictive analysis** 📊. It uses **n8n**, **Google Sheets**, and **LLM AI Agents** to automate logistics workflows.

---

## 🏗 Project Overview

### 🎯 **What this Project Does?**
- 🗣️ Accepts **voice commands** (e.g., _"Can you print today's invoice?"_).
- 📑 Retrieves **logistics invoice data** from Google Sheets.
- 🧠 Uses **AI models** to process and understand the command.
- 📄 **Generates an invoice in PDF/HTML format**.
- 🔮 (Optional) Performs **forecasting & predictive analytics** on logistics data.

![Image](https://github.com/user-attachments/assets/8ea83a50-2a86-4aef-96d0-41a9860bc660)

---

### 🔥 **Why Use This?**
✅ Automates invoice generation  
✅ Enhances logistics management with AI  
✅ Saves time & minimizes human errors  
✅ Easily extensible with more AI integrations  

---

## 🏗 **Workflow Architecture**

📌 The system consists of the following components:

1️⃣ **Webhook Node** – Receives voice command as input.  
2️⃣ **AI Agent Node** – Uses an LLM to process commands & extract intent.  
3️⃣ **Google Sheets Node** – Fetches logistics data based on the request.  
4️⃣ **Function Node** – Filters data (e.g., finding the invoice for today).  
5️⃣ **Template Node** – Generates invoice in HTML format.  
6️⃣ **(Optional) Forecasting Node** – Uses past data for trend analysis.  
7️⃣ **Webhook Response Node** – Returns the generated invoice.

## ⚙️ **Setup Instructions**

### 🛠 **Prerequisites**
- 🏗 **n8n Cloud / Local Setup**  
- 📊 **Google Account** (for Google Sheets integration)  
- 📄 **Google Sheet** (Containing invoice data)  

### 🚀 **Step-by-Step Setup**
#### 📌 **1. Prepare Google Sheets**
1. **Create a Google Sheet** with columns:

2. **Obtain your Google Sheets API Credentials**:
- Share the sheet with `service-account-email@n8n.io`
- Enable Google Sheets API from [Google Cloud Console](https://console.cloud.google.com/)

#### ⚙️ **2. Build the Workflow in n8n**
1. **Create Webhook Node**
- Method: `POST`
- Path: `/voice-command`

2. **Add AI Agent Node**
- Model: `DeepSeekAI (Free)`
- Memory: `Simple Memory`
- Tools: `Google Sheets`

3. **Connect Google Sheets Node**
- **Spreadsheet ID:** _(Your Google Sheet ID)_
- **Operation:** `Read Rows`
- **Filter:** Based on **Shipment Date**

4. **Generate Invoice**
- Use **Template Node** for HTML structure
- Convert to **PDF** (Optional)

5. **Webhook Response**
- Send the generated invoice as output.

6. **(Optional) Add Forecasting Node**
- Uses past invoices to predict **future logistics trends**.

---

**🎯 Future Improvements**
✅ Add multi-language support for voice commands.
✅ Improve forecasting model with ML training.
✅ Add email & WhatsApp notifications for generated invoices.
