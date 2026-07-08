# Customer Feedback Intelligence Dashboard

**[Live Demo](https://YOUR-USERNAME.github.io/customer-feedback-intelligence-dashboard/)** · Built during Summer 2026 Internship

> Interactive analytics dashboard that transforms 176K customer feedback records into actionable insights for reducing escalations and improving customer satisfaction.

![Dashboard Preview](https://img.shields.io/badge/status-live-brightgreen) ![Tech](https://img.shields.io/badge/stack-HTML%2FJS%2FChart.js-blue)

---

## The Problem

Customer service teams receive thousands of complaints daily across calls, emails, social media, and surveys. Without centralized analytics, escalation patterns go unnoticed until they become expensive — costing $225+ per formal escalation in credits and labor.

## The Solution

A three-page interactive dashboard that connects feedback volume, escalation routing, and sentiment analysis into one drillable workflow:

| Page | Purpose | Key Feature |
|------|---------|-------------|
| **Overview** | What's happening across all channels? | Clickable source cards, lifecycle mapping, volume trends |
| **Escalations** | What's costing us money? | Reduction calculator with per-issue savings estimates and recommended actions |
| **Sentiment** | What are customers actually saying? | VADER analysis with drillable feedback records |

## What I Built

- **Full-stack data pipeline**: Collected, cleaned, and unified feedback from 4 channels into a single normalized dataset
- **NLP sentiment scoring**: Applied VADER sentiment analysis to 176K records, classifying each as positive/negative/neutral
- **Category classification**: Used TF-IDF and clustering to map feedback into 17 issue categories aligned with real escalation classifications
- **Interactive dashboard**: Single-page app with cascading filters, drill-down charts, and context-aware AI insights
- **Escalation calculator**: Custom prevention rates and recommended actions for 37 issue types based on resolvability analysis

## Technical Highlights

- **Zero dependencies** — Pure HTML/CSS/JS, no framework, no build step
- **176K records** rendered performantly with lazy loading and pagination
- **Cascading filter architecture** — Header filters propagate across all 3 pages, page-level filters cascade through widgets
- **Chart.js** with custom plugins (inline data labels, center text, dark mode color switching)
- **Accessibility** — Dark mode, colorblind mode (blue/orange/amber palette), keyboard navigation
- **AI insights system** — Context-aware badges and floating cards that adapt to current filter state

## Skills Demonstrated

`Data Analytics` `NLP/Sentiment Analysis` `Data Visualization` `Frontend Development` `UX Design` `Business Intelligence` `Python` `JavaScript` `Chart.js` `CSS Animations`

## How to Run Locally

```bash
git clone https://github.com/YOUR-USERNAME/customer-feedback-intelligence-dashboard.git
cd customer-feedback-intelligence-dashboard
python -m http.server 8000
# Open http://localhost:8000
```

## Data Disclaimer

All data is synthetic/mock. No real customer information, PII, or proprietary company data is included. Customer names, accounts, and feedback text are generated for demonstration purposes only.

---

*Built by Kenneth Chow · Summer 2026*
