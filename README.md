# 📈 English‑Log — Daily 30‑Minute English Practice
Automating reading → speaking → feedback cycles (Mon–Fri 09:30 KST)  
JSON‑based logs + GitHub Actions = visible, data‑driven progress 🚀

---

## 🗂 Folder Structure
    english-log/           # daily JSON logs: 2025‑04‑17.json, ...
    .github/
    └─ workflows/
       ├─ log-commit.yml   # commits new JSON from ChatGPT sessions
       └─ chart-update.yml # weekly graph generation
    assets/
    └─ progress.png        # auto‑generated score chart
    README.md

---

## 🔄 Daily Flow
1. **Reading (~10 min)** — leveled text (CEFR A2 → …), quick T/F quiz  
2. **Speaking (~15 min)** — AVM conversation + 1‑minute summary  
3. **Feedback (~5 min)** — *IELTS Speaking* band, strengths & improvements  
4. ChatGPT saves a JSON file to **`english-log/`** and pushes it.

---

## 🏅 Scoring
We adopt the **IELTS Speaking band (0–9)** — widely used, granular, and focused purely on speaking ability.

---

## 📊 Progress Chart
A GitHub Action converts JSON → CSV → line chart (**assets/progress.png**) every Sunday at 00:00 KST.  
The README always shows your latest chart for at‑a‑glance growth tracking.

![Progress](assets/progress.png)

---

## ⚙️ Setup
1. **Add repository secrets**  
   * `GH_PAT` with `repo` scope (or rely on the built‑in `GITHUB_TOKEN`).  
2. **Copy the workflow files** in `.github/workflows/` from this template.  
3. **Start your next ChatGPT session** — it will append today’s JSON; Actions handle commits and chart generation automatically.

---

> *Happy learning! Every JSON is one brick in your fluency wall.* 🧱
