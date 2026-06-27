# 🎵 UGC Tagger

An AI-assisted TikTok UGC tagging platform built with Streamlit to automate content trend analysis for music marketing.

---

## Overview

UGC Tagger is designed to reduce the manual effort required to analyse TikTok User Generated Content (UGC) collected from MelodyIQ.

Instead of manually watching every TikTok and filling content tags, the application uses Google's Gemini model to automatically generate:

- Narrative
- Creative Type
- Content Details

Posts with low confidence or incomplete information are automatically routed to a human review workflow before exporting the final dataset.

---

# Features

### 📥 Data Input

- Upload MelodyIQ CSV/XLSX reports
---

### 🤖 AI Tagging Pipeline

The application uses a multi-stage AI workflow.

Tier 0
- Visual-only analysis
- Used when captions are missing or too vague

Tier 1
- Cover image + metadata analysis

Tier 2
- Video frame analysis
- Activated only when Tier 1 confidence is low

Tier 3
- Human review
- Manual correction for uncertain or incomplete posts

---

### 📝 Human Review

Supports:

- AI Suggest
- Manual Narrative editing
- Custom Narrative
- Creative Type editing
- Content Details editing
- Manual Market correction
- Manual engagement metrics
    - Views
    - Likes
    - Comments
    - Shares
    - Saves
- Remove unavailable posts from export

---

### 📊 Dashboard

Includes:

- Total Posts
- AI Tagged
- Automation Rate
- Review Rate
- Average Confidence
- Market Summary
- Narrative Distribution
- Creative Type Distribution
- Track Leaderboard

---

### 📤 Export

- Merge AI results back into the original MelodyIQ spreadsheet
- Match using TikTok Video ID
- Export as CSV
- Export as Excel (.xlsx)

---

# Workflow

MelodyIQ Report
        │
        ▼
Upload CSV / XLSX
        │
        ▼
Apify TikTok Scraper
(API or JSON Upload)
        │
        ▼
AI Tagging Pipeline

Tier 0
   │
Tier 1
   │
Tier 2
   │
Tier 3 (Human Review)

        │
        ▼
Merge into Original Report
        │
        ▼
Export Final Dataset
---

# Installation

Clone the repository

git clone https://github.com/<your-username>/ugc-tagger.git
cd ugc-tagger
Install dependencies

pip install -r requirements.txt
Run locally

streamlit run app.py
---

# Required Packages

Main packages used:

- streamlit
- pandas
- plotly
- requests
- openpyxl
- opencv-python
- google-genai
- apify-client

---

# API Keys

The application requires:

- Google Gemini API Key
- Apify API Token

For local development these can be entered in the application.

For deployment they should be stored securely using Streamlit Secrets or environment variables.

---

# Disclaimer

This project is intended as an AI-assisted workflow tool.

AI-generated tags should be reviewed by analysts before being used in downstream reporting.

TikTok content analysed by this application is publicly available content.

---

# Author

Developed as an internship project for exploring AI-assisted UGC content tagging and workflow automation in music marketing analytics.

---

# License

This repository is currently provided for demonstration and evaluation purposes.
