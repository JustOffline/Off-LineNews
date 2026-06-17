# Off-LineNews

**A self-updating tracker for social media bans, platform restrictions, and digital censorship legislation worldwide.**

Live site → **[justoffline.github.io/Off-LineNews](https://justoffline.github.io/Off-LineNews)**

News auto-updates every day at 07:00 UTC from 14 free RSS feeds. No API keys. No database. No hosting costs.

---

## Install in 4 steps (5 minutes)

### Step 1 — Upload the files

In your `Off-LineNews` repository, click **Add file → Upload files** and upload all of these at once, preserving the folder structure:

```
index.html
SOURCES.md
README.md
scripts/fetch_news.py
.github/workflows/daily-update.yml
```

> **Note on `.github` folder:** GitHub's file uploader may hide folders starting with `.` on some browsers. If you can't see `.github/workflows/daily-update.yml` after uploading, create it manually: go to your repo → **Add file → Create new file** → type the path `.github/workflows/daily-update.yml` → paste the contents of that file → commit.

Commit all files to the `main` branch.

---

### Step 2 — Enable GitHub Pages

1. Go to your repo → **Settings** (top nav)
2. Click **Pages** in the left sidebar
3. Under **Source** → select **Deploy from a branch**
4. Branch: `main` · Folder: `/ (root)`
5. Click **Save**

Your site will be live at `https://justoffline.github.io/Off-LineNews` within about 60 seconds.

---

### Step 3 — Run the news fetcher now (don't wait until tomorrow)

1. Go to your repo → **Actions** tab
2. Click **Daily News Update** in the left list
3. Click the **Run workflow** dropdown (top right of the table)
4. Click the green **Run workflow** button

The bot will run in ~30 seconds, fetch today's news, update `index.html`, and push the commit. Refresh your live site to see the news cards populate.

---

### Step 4 — Done

The workflow runs automatically every day at 07:00 UTC from now on. You don't need to touch anything.

To manually trigger an extra update anytime: repeat Step 3.

---

## What updates automatically vs manually

| Section | How it updates |
|---|---|
| **3.0 News** | ✅ Auto — every day at 07:00 UTC |
| **1.0 Platform Tracker** | ✍️ Manual — edit `index.html` |
| **2.0 Legislation** | ✍️ Manual — edit `index.html` |

---

## Editing platform status or legislation

Open `index.html` directly in GitHub (click the file → pencil icon to edit → commit). The platform cards and legislation table are clearly labelled in the HTML with comments. Changes go live on GitHub Pages within ~30 seconds.

---

## News sources

14 free RSS feeds — no API keys needed:

BBC Technology · The Guardian · Al Jazeera · OONI · Rest of World · EFF · TechCrunch · Wired · Techdirt · NetBlocks · Freedom House · Access Now · The Intercept · AP Technology

Full list with URLs in [SOURCES.md](SOURCES.md).

---

## Troubleshooting

**The Actions tab shows a failed run**
Click the failed run → click the job name → read the log. The most common cause is a feed returning a non-XML response (some feeds are flaky). The script skips broken feeds and continues — it will try again tomorrow.

**The `.github` folder isn't showing up after upload**
Create the workflow file manually: **Add file → Create new file** → enter `.github/workflows/daily-update.yml` as the filename → paste the YAML content.

**News cards aren't updating on the live site**
Check the Actions tab to confirm the workflow ran and committed. GitHub Pages can take up to 60 seconds to redeploy after a commit.

**I want to add or remove a news source**
Edit the `RSS_FEEDS` list near the top of `scripts/fetch_news.py`.

**I want to change which keywords trigger inclusion**
Edit the `KEYWORDS` list in `scripts/fetch_news.py`.

---

## Repo structure

```
Off-LineNews/
├── index.html                     ← the site
├── SOURCES.md                     ← methodology
├── README.md                      ← this file
├── scripts/
│   ├── fetch_news.py              ← news bot (runs daily)
│   └── seen_guids.json            ← auto-created; dedup cache
└── .github/
    └── workflows/
        └── daily-update.yml       ← GitHub Actions schedule
```

---

## Report an error or missing data

Open an [Issue](https://github.com/JustOffline/Off-LineNews/issues/new) with a source link.
