<!-- Banner — replace with a screenshot of the dashboard overview banner -->
<p align="center">
  <img src="assets/banner.png" alt="Customer Feedback Intelligence Dashboard" width="100%">
</p>

<h1 align="center">Customer Feedback Intelligence Dashboard</h1>

<p align="center">
  <strong>An end-to-end analytics platform that transforms raw customer feedback into actionable escalation reduction strategies.</strong>
</p>

<p align="center">
  <a href="https://dulcet-zabaione-dabd93.netlify.app/">Live Demo</a> · 
  <a href="#the-problem">Problem</a> · 
  <a href="#data-sources">Data</a> · 
  <a href="#the-pipeline">Pipeline</a> · 
  <a href="#the-dashboard">Dashboard</a> · 
  <a href="#tools--why">Tools</a>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/status-live-brightgreen" alt="Status">
  <img src="https://img.shields.io/badge/data-100%25%20synthetic-orange" alt="Data">
  <img src="https://img.shields.io/badge/built-Summer%202026-blue" alt="Built">
</p>

---

> **Disclaimer:** All data in this project is synthetic/mock. No real customer data, PII, or proprietary information is included. Names, accounts, and feedback text are generated for demonstration purposes only.

---

## The Problem

Telecom companies receive tens of thousands of customer complaints daily across phone calls, emails, social media, and surveys. When complaints go unresolved, they escalate into formal cases (ECAFs) that require executive attention, cost $225+ each in credits and labor, and can result in regulatory filings with the FCC or BBB.

**The challenge:** There was no centralized way to see which complaint categories escalate the most, where those escalations get routed, or what specific issues drive the highest cost. Analysts had to manually dig through spreadsheets.

**The goal:** Build a single interactive tool that lets an analyst go from "we have a problem" to "here's exactly what to fix and how much we'd save" in under 60 seconds.

---

## Data Sources

The dashboard ingests feedback from 4 channels, each with different formats and characteristics:

| Channel | Volume | What it looks like | Why it matters |
|---------|--------|-------------------|----------------|
| **Calls** | ~90K records | Agent transcription notes | Highest volume, most escalation-prone |
| **Emails** | ~200 records | Formal written complaints | Structured, high intent to act |
| **Social Media** | ~460 records | Public posts (Twitter, Reddit) | Visible to other customers, reputational risk |
| **Surveys** | ~86K records | NPS and CSAT responses | Direct satisfaction measurement |

<!-- Add screenshots of raw data samples here -->
<details>
<summary><strong>Click to see raw data examples</strong></summary>

<!-- Replace these with actual screenshots -->
_Add screenshots showing what each data source looks like before processing_

- Call transcript sample
- Email sample  
- Social media post sample
- Survey response sample

</details>

---

## The Pipeline

Raw feedback goes through 4 stages before it reaches the dashboard:

```
Raw Feedback → Normalize & Clean → NLP Classification → Sentiment Scoring → Dashboard
```

<details>
<summary><strong>Click for detailed pipeline explanation</strong></summary>

### Stage 1: Collection & Normalization
All 4 sources are cleaned and merged into one consistent format. Email headers/signatures are stripped. Survey scales are normalized. Social media handles are removed.

### Stage 2: Category Classification
Using TF-IDF vectorization and clustering, each record is assigned to one of 17 issue categories (billing, connectivity, outage, etc.) that align with real escalation classification systems.

### Stage 3: Sentiment Scoring (VADER)
Each record receives a satisfaction score from +1.0 (very satisfied) to -1.0 (very dissatisfied). VADER was chosen because it handles informal language, slang, and social media tone better than traditional models.

### Stage 4: ECAF Mapping
Records are cross-referenced with escalation data to identify which feedback eventually became formal complaints, enabling predictive pattern recognition.

</details>

---

## The Dashboard

Three interconnected pages, each answering a different question:

### Overview — "What's happening?"

Shows all feedback volume, source breakdown, category distribution, lifecycle stage mapping, and sentiment trends.

<!-- Add screenshot of Overview page -->
<details>
<summary><strong>Click to see Overview features</strong></summary>

- **Source cards** — 4 clickable cards showing volume per channel with mini donut charts
- **Lifecycle stages** — Maps complaints to customer journey (Sales → Order → Activation → Service → Retention)
- **Issue Categories** — Horizontal bar chart with click-to-highlight filtering
- **Sentiment by Category** — Stacked bars, clickable to drill into a single category then into individual sentiment counts
- **Feedback Volume Trend** — Weekly volume with rolling average, dark-mode aware
- **Feedback Records** — Searchable, filterable table of actual customer text

</details>

### Escalations — "What's costing us money?"

Identifies which complaints become formal escalations, where they get routed, and calculates reduction opportunities.

<!-- Add screenshot of Escalations page -->
<details>
<summary><strong>Click to see Escalation features</strong></summary>

- **Flow strip** — Feedback → ECAFs → Leadership visual funnel
- **Category ECAF Breakdown** — Ranked by volume with above/below average escalation rate indicators
- **Routing Pie Chart** — CEO / Agency (FCC/BBB) / Internal split, clickable segments
- **Top Issue Classifications** — Bar chart with click-to-highlight, feeds into calculator
- **Reduction Opportunity Calculator** — Per-issue savings estimates with custom preventable percentages, methodology explanation, and 3 recommended actions per issue type (37 issues covered)
- **ECAF Tickets** — Scrollable list of actual escalation records with full detail modal

</details>

### Sentiment — "What are customers actually saying?"

Lets you read the actual words customers used, filtered by sentiment type and category.

<!-- Add screenshot of Sentiment page -->
<details>
<summary><strong>Click to see Sentiment features</strong></summary>

- **KPI cards** — Positive/Negative/Neutral percentages, clickable to filter
- **Sentiment Over Time** — 4-week rolling average line chart
- **Customer Feedback** — Drillable list of records sorted by sentiment score
- **VADER Pipeline** — Clickable explainer showing how scoring works

</details>

---

## Tools & Why

| Tool | Purpose | Why this one? |
|------|---------|---------------|
| **Python** | Data pipeline, cleaning, classification | Best ecosystem for NLP and data manipulation |
| **VADER** | Sentiment scoring | Handles informal/social media language without training data |
| **TF-IDF + K-Means** | Category classification | Unsupervised — no labeled training data required |
| **JavaScript (vanilla)** | Dashboard frontend | Zero build step, single file deployment, no framework overhead |
| **Chart.js 4.4** | All visualizations | Lightweight, canvas-based, extensive plugin system |
| **HTML/CSS** | Layout and styling | Custom design system matching Spectrum brand colors |
| **Netlify** | Hosting | Free, fast CDN, instant deploys |

---

## Interactive Features

Everything is designed to be clicked, filtered, and drilled into:

- **Cascading filters** — Header filters (time/source/category) propagate across all 3 pages
- **Click-to-highlight** — Bars pop out, others dim (never zooms away from context)
- **Drill-in/drill-out** — Sentiment chart: click category → see breakdown → click sentiment → see records
- **AI Insights** — Sparkle button activates context-aware badges and recommendation cards
- **Slot machine animation** — Key numbers animate on update
- **Corner bracket hover** — Consistent interaction affordance on all clickable elements
- **Dark mode** — Full dark palette with Chart.js color adaptation
- **Colorblind mode** — Blue/orange/amber palette (deuteranopia/protanopia safe)

---

## Thought Process

<details>
<summary><strong>Click to read design decisions</strong></summary>

**Why a single HTML file?**  
Recruiters and executives should be able to open it without installing anything. No node_modules, no build step, no "npm install". Just open and use.

**Why no React/Vue/Angular?**  
The dashboard is read-heavy, not interaction-heavy. Vanilla JS with Chart.js handles this use case without framework overhead. It also demonstrates understanding of core web fundamentals.

**Why synthetic data?**  
Real escalation data contains customer PII and proprietary business metrics. The synthetic data preserves the statistical patterns and relationships needed to demonstrate the analytics while being completely safe to share publicly.

**Why VADER over transformers?**  
VADER runs client-side in milliseconds. Transformer models require a server, API calls, and compute costs. For a dashboard that re-scores on every filter change, speed matters more than marginal accuracy gains.

**Why per-issue recommendations in the calculator?**  
Generic "reduce escalations" advice is useless. An analyst needs to know: for THIS specific issue, what percentage is preventable, WHY it escalates, and WHAT specific process change would fix it. That's what makes the tool actionable vs decorative.

</details>

---

## Run Locally

```bash
git clone https://github.com/kenecu1/customer-feedback-intelligence-dashboard.git
cd customer-feedback-intelligence-dashboard
python -m http.server 8000
# Open http://localhost:8000
```

Or just visit the **[Live Demo](https://dulcet-zabaione-dabd93.netlify.app/)**.

---

<p align="center">
  <strong>Built by Kenneth Chow · Summer 2026 Internship Project</strong><br>
  <sub>All data is synthetic. No real customer information is included.</sub>
</p>
