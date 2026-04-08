# 💬 WhatsApp Chat Analyzer

A **Streamlit-powered web app** that transforms your exported WhatsApp chat history into rich visual insights — message trends, word clouds, emoji breakdowns, activity heatmaps, and more.

---

## 🚀 Features

| Feature | Description |
|---|---|
| 📊 **Top Statistics** | Total messages, words, media shared, and links exchanged |
| 📅 **Monthly & Daily Timeline** | Line charts showing messaging activity over time |
| 🗓️ **Activity Map** | Busiest days of the week and months of the year |
| 🔥 **Weekly Heatmap** | Hour-of-day vs. day-of-week activity heatmap |
| 👥 **Most Busy Users** | Bar chart + percentage table for group chats |
| ☁️ **Word Cloud** | Visual frequency map of the most used words |
| 🔤 **Most Common Words** | Top-20 most frequent words (stop words filtered) |
| 😂 **Emoji Analysis** | Emoji frequency table and pie chart |

All analyses can be run **overall** (entire group/chat) or filtered to a **specific user**.

---

## 🛠️ Tech Stack

- **[Streamlit](https://streamlit.io/)** — Interactive web UI
- **[Pandas](https://pandas.pydata.org/)** — Data wrangling & processing
- **[Matplotlib](https://matplotlib.org/) / [Seaborn](https://seaborn.pydata.org/)** — Charts and heatmaps
- **[WordCloud](https://github.com/amueller/word_cloud)** — Word cloud generation
- **[emoji](https://pypi.org/project/emoji/)** — Emoji detection and counting
- **[urlextract](https://pypi.org/project/urlextract/)** — URL extraction from messages
- **Python 3.x** — Core language

---

## 📁 Project Structure

```
Whatsapp-Chat-Analysis/
│
├── app.py               # Main Streamlit application
├── helper.py            # Analysis functions (stats, word cloud, emoji, timelines)
├── preprocessor.py      # Parses raw WhatsApp export .txt into a structured DataFrame
├── stop_hinglish.txt    # Custom stop-word list (English + Hinglish)
└── README.md
```

---

## ⚙️ Installation

### 1. Clone the repository

```bash
git clone https://github.com/Navinrajput2712/Whatsapp-Chat-Analysis.git
cd Whatsapp-Chat-Analysis
```

### 2. Install dependencies

```bash
pip install streamlit pandas matplotlib seaborn wordcloud emoji urlextract
```

### 3. Run the app

```bash
streamlit run app.py
```

The app will open in your browser at `http://localhost:8501`.

---

## 📤 How to Export Your WhatsApp Chat

1. Open any WhatsApp **chat or group**.
2. Tap the **three-dot menu (⋮)** → **More** → **Export chat**.
3. Choose **Without media**.
4. Save the `.txt` file to your device.

---

## 🧪 How to Use

1. Launch the app with `streamlit run app.py`.
2. In the **sidebar**, click **"Choose a file"** and upload your exported `.txt` file.
3. Select a **user** from the dropdown — choose *"Overall"* for group-level analysis.
4. Click **"Show Analysis"** to generate all charts and statistics.

---

## 📦 Module Overview

### `preprocessor.py`
Parses the raw WhatsApp export text file using regex. It:
- Splits messages by timestamp pattern (`DD/MM/YYYY, HH:MM - `)
- Extracts user names and message content
- Adds derived columns: `month`, `year`, `day_name`, `only_date`, `period` (Morning / Afternoon / Evening / Night)

### `helper.py`
Contains all the analysis logic:
- `fetch_stats()` — Counts messages, words, media, and links
- `monthly_timeline()` / `daily_timeline()` — Time-series aggregations
- `week_activity_map()` / `month_activity_map()` — Day/month frequency counts
- `activity_heatmap()` — Pivot table for day × time-period heatmap
- `most_busy_users()` — Top users by message count with percentage share
- `create_wordcloud()` — Generates a word cloud filtered by stop words
- `most_common_words()` — Top-20 words after stop-word removal
- `emoji_helper()` — Counts and ranks emojis used in messages

### `app.py`
The Streamlit front-end that wires everything together — file upload, user selection, and rendering all charts.

---

## 📝 Notes

- The preprocessor expects the **standard WhatsApp export format**: `DD/MM/YYYY, HH:MM - Username: Message`.
- The `stop_hinglish.txt` file contains common English and Hinglish stop words to improve word cloud and common-word quality.
- Group notifications (e.g., "You were added") are automatically excluded from user-level analysis.

---

## 🤝 Contributing

Pull requests are welcome! To contribute:
1. Fork the repository
2. Create a feature branch: `git checkout -b feature/your-feature`
3. Commit your changes and push
4. Open a Pull Request

---

## 📄 License

This project is open-source. Feel free to use and modify it for personal or educational purposes.

---

## 👤 Author

**Navin Rajput**  
GitHub: [@Navinrajput2712](https://github.com/Navinrajput2712)
