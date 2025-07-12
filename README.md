
# 🛠️ Remote Job Scraper & Telegram Notifier (n8n Workflow)

This project is an automated workflow built with [n8n](https://n8n.io) that:

1. Fetches remote job offers from multiple free public APIs
2. Filters out irrelevant or duplicate listings
3. Sends the new jobs directly to a Telegram channel or bot
4. Logs every unique job link into a Google Sheet to prevent duplication

---

## 📌 Features

- 🔄 Automated job fetching on a schedule (cron)
- 🌐 Integrated with 4 job APIs:
  - Remotive
  - RemoteOK
  - Arbeitnow
  - Adzuna
- 🎯 Filters jobs by keywords (`developer`, `engineer`, `fullstack`, etc.)
- 📤 Sends jobs to Telegram in a structured format
- 🧾 Tracks already sent jobs in Google Sheets
- 💬 Clean message formatting with emojis
- 🛑 Duplicate-proof — jobs are not re-sent if they already exist in the sheet

---

## 🔧 Requirements

- [n8n](https://n8n.io) installed locally or hosted
- A Telegram bot + chat ID
- A Google Sheet with at least one column named `url`
- API keys for:
  - [Adzuna](https://developer.adzuna.com/) (free tier available)

---

## 📁 Project Structure

```
.
├── README.md          # This file
├── jobs.json          # Main n8n workflow definition
```

---

## 🚀 Setup Instructions

### 1. Import the Workflow

- Open your n8n instance
- Click on "Import Workflow" and upload `Automated Remote Job Scraper.json`

### 2. Configure Credentials

- **Telegram Bot:**
  - Create a bot via [@BotFather](https://t.me/BotFather)
  - Add the bot token in n8n's credentials as `telegramApi`
- **Google Sheets:**
  - Authenticate with your Google account
  - Set up a sheet with a `url` column
- **Adzuna API:**
  - Register at https://developer.adzuna.com/
  - Replace the API credentials in the Adzuna request URL

### 3. Telegram Chat ID

- Use [@userinfobot](https://t.me/userinfobot) or check message logs to find your chat ID

---

## 🧠 Logic Flow (Simplified)

```text
Cron Trigger
   ↓
HTTP Requests (Remotive, RemoteOK, Arbeitnow, Adzuna)
   ↓
Normalize Data
   ↓
Merge All Jobs
   ↓
Read URLs from Sheet
   ↓
Filter Duplicates
   ↓
Send to Telegram
   ↓
Append to Google Sheets
```

---

Enjoy automated job hunting! 🚀
