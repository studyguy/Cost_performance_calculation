# Cost-Performance Calculator (工作性价比计算器)

> Quantify "is this job actually worth it?" into a single score, a radar chart, and a brutally honest one-liner — a single-file static page, zero dependencies, no backend, no build step. Fill in a few numbers and the truth shows up instantly.

**[🧮 Try It Online](https://studyguy.github.io/Cost_performance_calculation/)** · **[📦 Source Code](https://github.com/studyguy/Cost_performance_calculation)**

---

## 📖 What Is This

When you have an offer or are thinking about job-hopping, "how much does it pay" barely answers "is this job worth it?" — a 20k salary on a 996 schedule can be worse than 15k with weekends off. Enter a few numbers (salary, hours, commute, environment, team, growth, stability) and this tool scores you across **six weighted dimensions**, producing a composite score with an S–E grade, a radar chart, and a commentary with personality.

**Runs entirely locally**: profiles and theme live in your browser's `localStorage` — no backend, no analytics, no tracking. Clearing browser data clears your profiles.

## ✨ Features

- **Six-dimension weighted scoring**: salary return 34% · time cost 18% · material environment 8% · team atmosphere 12% · growth 14% · stability 14%
- **Real income accounting**: social insurance, simplified income tax, year-end bonus, and hidden perks are auto-converted — "take-home monthly / total monthly / annual income" visible live
- **City purchasing-power adjustment**: scores corrected by city cost of living (tier-1 1.32 → tier-4-and-below 0.75, tier-2 as baseline)
- **Commute & overtime linkage**: commute slider with tiered copy (remote / light / standard / long / extreme); unpaid overtime penalizes the time dimension using the Labor Law's 1.5–3× overtime-pay rationale
- **S–E grade scale**: S ≥85 "dream job" → E <25 "run", each grade with a witty line (the soul of this project)
- **Real-time**: change any input and the score, grade, commentary, and radar chart refresh instantly
- **Profiles & comparison**: save multiple evaluations, compare them side by side on the radar chart and metric table, and view historical trends
- **Dark mode + mobile layout**: follows system preference and persists; single-column layout on narrow screens

## 🧮 Scoring Model at a Glance (v3, six dimensions)

```
Composite = Σ(dimension subscore × weight) ÷ (education expectation × experience expectation)
```

- **Salary return**: real income ÷ city cost index → purchasing-power hourly rate on a log curve
- **Time cost**: work + commute hours × vacation correction × overtime-payback correction
- **Expectation coefficients**: education (non-211/985 bachelor 0.8 → overseas PhD 2.2) and years of experience (fresh grad 0.95 → 12+ years 1.2) — same money, higher expectations, harder to score high

**Grades**: S ≥85 / A ≥70 / B ≥55 / C ≥40 / D ≥25 / E <25

> Model history: v1 "hourly base × environment × team ÷ education" → v2 four-dimension weights + log hourly curve → v3 full six-dimension rebuild with real-income accounting and city purchasing power.
> Accounting note: income tax ignores special deductions and uses gross salary as the housing-fund base — estimates only, not tax or financial advice.

## 🚀 Quick Start

| Method | How |
|---|---|
| 🧮 Try online | [studyguy.github.io/Cost_performance_calculation](https://studyguy.github.io/Cost_performance_calculation/) |
| 💻 Run locally | Clone the repo and drag `index.html` into your browser; or `python3 -m http.server 8000` and open `http://127.0.0.1:8000/` |

**Three steps**: ① Enter salary, pick experience/education, tune hours/days/commute ② Choose environment/team/growth ③ Read your score, grade, commentary, and radar chart live; "Save as profile" to compare on the Compare page and track trends on the Profiles page.

## 🛠️ Technical Notes

- **Single-file static page**: `index.html` alone is the whole app (HTML + CSS + JS), zero dependencies, no build step
- **Canvas-drawn radar chart**; older profiles migrate and recompute automatically
- **Privacy by design**: everything stays in `localStorage` — export or back up before deleting

## 📁 Project Structure

```
Cost_performance_calculation/
├── index.html   # The entire app (HTML + CSS + JS in one file)
└── README.md    # This file
```

## 📜 Disclaimer

For entertainment only. The scoring model is one quantitative view of "cost-performance" — not career advice.

Take a breath. Life is more than this quarter's KPI.
