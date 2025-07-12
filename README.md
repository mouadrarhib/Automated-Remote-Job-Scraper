# 🔧 Automated Remote Job Scraper with n8n, Telegram & Google Sheets

This project is a fully automated job aggregator built using [n8n](https://n8n.io/), designed to collect remote job postings from multiple APIs, filter and normalize the data, remove duplicates, and send them directly to Telegram while logging them to Google Sheets.

---

## 🚀 Features

- 🔁 **Automated Scheduling** with Cron
- 🌍 **API Integration** with:
  - Remotive
  - RemoteOK
  - Arbeitnow
  - Adzuna
- 🧠 **Normalization & Filtering** based on keywords like `developer`, `engineer`, `frontend`, `backend`, etc.
- 🧹 **Duplicate Removal** via comparison with Google Sheets URLs
- 💬 **Instant Telegram Notifications**
- 📊 **Google Sheets Logging** of all unique job entries

---

## 🧰 Technologies Used

- **n8n** for workflow automation
- **JavaScript** code nodes for custom logic
- **Google Sheets API** for reading/writing job data
- **Telegram Bot API** for sending formatted job alerts
- **REST APIs** with HTTP Requests

---

## 📌 Workflow Overview

1. **Cron Trigger** starts the process.
2. Each job board API is queried (`Remotive`, `RemoteOK`, `Arbeitnow`, `Adzuna`).
3. Jobs are **filtered** by keywords and **normalized** into a unified format.
4. All jobs are **merged**.
5. Google Sheet is checked for **existing URLs**.
6. New jobs are sent to **Telegram** and **logged** in Google Sheets.

---

## 📦 Output Sample (Telegram Format)

```
📌 Delphi Developer
🏢 Phizenix  
🌍 Remote, Coos County  
📅 2025-06-09  
🔗 [Apply Here](https://www.adzuna.com/details/5241184553?utm_medium=api&utm_source=2fc5963c)
```

---

## 🧪 Learning Outcomes

This was my **first real-world project using n8n**, where I learned:
- API handling inside visual workflows
- JavaScript integration within n8n Code nodes
- Real-time bot integration with Telegram
- De-duplication logic via sets and filters
- Connecting Google Sheets dynamically

---

## 📂 Project Status

✅ Completed and running live with scheduled Cron jobs.  
🔄 Open to improvements and more integrations (e.g. LinkedIn, Indeed, etc).

---

## 👨‍💻 Author

**Mouad Rarhib**  
[LinkedIn](https://www.linkedin.com/in/mouadrarhib) • [GitHub](https://github.com/MouadRarhib)

---

## 📃 License

This project is open source and available under the [MIT License](LICENSE).