# 📈 English‑Log — Daily 30‑Minute English Practice
Automating reading → speaking → feedback cycles (Mon–Fri 09:30 KST)  
JSON‑based logs + GitHub Actions = visible, data‑driven progress 🚀

---

## 🗂 Folder Structure
```text
english-log/           # daily JSON logs: YYYY-MM-DD.json
.github/
└─ workflows/
   ├─ log-commit.yml   # commits new JSON from ChatGPT sessions
   └─ chart-update.yml # weekly graph generation
assets/
└─ progress.png        # auto‑generated score chart
README.md
```

---

## 🔄 Daily Flow
1. **Reading (~10 min)** — level‑matched passage (≈150 words) + quick T/F quiz  
2. **Speaking (~15 min)** — voice conversation on the same topic + 1‑minute summary  
3. **Feedback (~5 min)** — *IELTS Speaking* band, strengths & improvements  
4. ChatGPT outputs a JSON file to **`english-log/`** and pushes it.

---

## 🏅 Scoring
We adopt the **IELTS Speaking band (0–9)** — widely used, granular, and focused purely on speaking ability.

---

## 📊 Progress Chart
A GitHub Action converts JSON → CSV → line chart (**assets/progress.png**) every Sunday at 00:00 KST.  
The README always shows the latest chart for at‑a‑glance tracking.

![Progress](assets/progress.png)

---

## ⚙️ Setup
1. **Add repository secrets**  
   * `GH_PAT` with `repo` scope (or rely on the built‑in `GITHUB_TOKEN`).  
2. **Copy the workflow files** in `.github/workflows/` from this template.  
3. **Start your next ChatGPT session** — it will add today’s JSON; Actions manage all commits and chart updates automatically.

---

## 🎤 Voice Mode Reading Guide
You can complete the entire reading phase in ChatGPT’s Advanced Voice Mode (AVM) right inside your desktop browser.

| Step | Learner Action | ChatGPT Action | What Gets Logged |
|------|----------------|----------------|------------------|
| 1. Text shown | Read the passage on‑screen | Provides a 150 ± 20‑word passage and a short vocabulary list | — |
| 2. Say “Start” | Begin reading aloud | Records `startTime` | — |
| 3. Say “Done” | Finish reading | Calculates `reading_seconds` | `reading_seconds` |
| 4. Answer quiz | Say answers (“O X O”) | Parses answers, scores quiz | `comprehension_score` |
| 5. Pronunciation note | — | Compares Whisper transcript to the text, notes missed or mis‑pronounced words | `notes[]` |
| 6. JSON output | — | Prints the complete JSON block in the chat | You save it to `english-log/` |

### Enabling Voice Mode
1. Click the **🎤 mic icon** in any chat and select **Advanced Voice**.  
2. Grant microphone permission in your browser.  
3. Choose a voice and start speaking — each turn appears as a grey collapsed bubble (click to expand the transcript).

---

## FAQ

| Question | Answer |
|----------|--------|
| **Is the timing precise?** | `reading_seconds` is derived from chat timestamps. It is accurate to within a few seconds—good enough for progress tracking. |
| **How accurate is pronunciation feedback?** | Whisper reliably flags obvious mispronunciations. For phoneme‑level analysis you would still need a dedicated app. |
| **Do I have to copy JSON manually?** | Manual copy‑paste works fine. For zero‑click logging you can add a small userscript or local helper that detects the JSON block and pushes it via the PAT. |
| **Can I keep the transcript visible?** | Yes. In **Settings → Voice** enable “Always show transcript,” or expand individual bubbles. |

---

*Every JSON file is one brick in your fluency wall — keep stacking!* 🧱

