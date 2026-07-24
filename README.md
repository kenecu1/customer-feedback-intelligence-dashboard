<p align="center">
  <img src="data/SPEC%20BANENR%20header.png" alt="SPEC - Customer Feedback Intelligence Dashboard" width="100%">
</p>

<p align="center">
  Built by Kenneth Chow · Summer 2026
</p>

<p align="center">
  <a href="https://iridescent-taiyaki-2af528.netlify.app/"><strong>Live Demo</strong></a> · <a href="#the-problem">Problem</a> · <a href="#the-dashboard">Dashboard</a> · <a href="#business-impact">Impact</a> · <a href="#data-sources">Data</a> · <a href="#the-pipeline">Pipeline</a> · <a href="#machine-learning--nlp">ML</a> · <a href="#tools--why">Tools</a> · <a href="#skills-demonstrated">Skills</a> · <a href="#run-locally">Run</a>
</p>

> [!IMPORTANT]
> **⭐ Adopted in practice.** The Group Vice President of Customer Operations endorsed this dashboard, and the department is adopting its design and framework for future use.

---

> **Disclaimer:** Calls, emails, and surveys are fully AI-generated, so all names and fields are fake and map to no real person. The social channel uses real public Reddit posts with account info removed. No real customer data, PII, or proprietary company information is included.
>
> **Built with AWS Kiro:** The dashboard design and front-end were developed with the help of [AWS Kiro](https://kiro.dev/), an AI-powered development environment.

---

<a id="the-problem"></a>

<img src="data/problem%20header%202.png" alt="The Problem" width="100%">

**Problem Statement:** Customers often find it hard to leave feedback or get timely help. In extreme cases, they feel they need to escalate all the way to top leadership to get their issues resolved. At the same time, the volume of unstructured input (emails, surveys, calls, social posts) becomes difficult to analyze at scale.

**Project Objective:** Design a scalable system that uses AI and natural language processing to automatically convert unstructured customer feedback into actionable insights.

**My Focus:**
- Map the customer feedback journey across all input channels (calls, emails, social media, surveys)
- Identify pain points: where customers get stuck, confused, or ignored
- Use NLP and analytics to:
  - Cluster similar feedback together automatically
  - Detect recurring themes and trends (billing, speed, outages, support experience)
  - Prioritize the highest impact issues based on severity, volume, and cost

**Deliverable:** A feedback insights layer for internal teams that surfaces the most important problems quickly so analysts can identify escalation patterns and reduction opportunities without manually reading through spreadsheets.

<details>
<summary><strong>What is an escalation?</strong></summary>

When a customer's complaint doesn't get resolved through normal support, it gets formally escalated. This means it leaves the regular support team and gets sent to executives, regulatory agencies, or a dedicated corporate team to handle. Each one costs the company money through customer credits (typically ranging from $50 to several hundred dollars per case), labor from multiple departments, and sometimes legal response requirements. At scale, thousands of escalations per month can represent hundreds of thousands in operational costs. Most of them are preventable if you can catch the underlying problem early.

</details>

---

<a id="the-dashboard"></a>

<img src="data/dashboard%20header%202.png" alt="The Dashboard" width="100%">

Three interconnected pages (Overview, Escalations, Sentiment). Every widget is drillable, and filters carry across all three pages, so narrowing down on one page follows you to the next. Where a page's header banner has a pipeline strip, it's clickable too.

<details>
<summary><strong>AI Insights (live assistant)</strong></summary>

A prototype of how AI could assist analysts: a built in assistant that reads the dashboard and guides you to what matters.

<table>
  <tr>
    <td width="80" align="center"><img src="data/ai%20button%20new.png" width="50" alt="AI button"></td>
    <td>A floating button sits in the top corner of every page. Click it any time to pull up insights for whatever you are currently looking at.</td>
  </tr>
</table>

#### Feedback Intelligence

<img src="data/aioutput%20exmape.png" alt="Feedback Intelligence summary" width="80%">

Reads the current data, does the analysis behind the scenes, and lays out a recommended course of action as a compact mini dashboard inside the dashboard. It is a glimpse of what a full AI implementation could hand an analyst: the digging done and the next move already suggested.

#### Highlights the recommended widget

<img src="data/ai%20widget%20feature.png" alt="AI highlighting a widget" width="80%">

To make the recommendation obvious, the AI draws a highlight around the exact widget it is pointing to, so you can see at a glance where to look. The highlight and the recommendation update as you filter, always matching the current data.

</details>

<details>
<summary><strong>Overview features</strong></summary>

### Overview - What's happening

The Overview walks you down the customer journey, filtering from broad to specific as you move top to bottom. Each widget narrows the scope further.

#### Source Cards

<img src="data/Source%20cards.png" alt="Source cards" width="80%">

Four clickable cards, one per channel, each showing that channel's feedback volume with a mini donut chart. Clicking a card filters the entire dashboard down to that source, so you can isolate just calls, emails, social, or surveys.

#### Feedback Volume Trend

<img src="data/Feedback%20volume%20trend.png" alt="Feedback volume trend" width="80%">

Weekly feedback volume with a rolling average line, so spikes and trends stand out.

#### Lifecycle Stages

<img src="data/Lifecycle%20stage.png" alt="Lifecycle stages" width="80%">

Ranks the customer lifecycle stages (Sales → Order → Activation → Service → Retention) from the most feedback to the least, so you can see where in the journey issues are concentrated.

#### Issue Categories

<img src="data/Issue%20categories.png" alt="Issue categories" width="80%">

Horizontal bar chart ranking issue categories by volume, with click-to-highlight filtering so you can focus the rest of the page on a single category.

#### Sentiment by Category

<img src="data/Sentiment%20by%20category.png" alt="Sentiment by category" width="80%">

Stacked bars showing positive/negative/neutral split per category. Clickable to drill into a single category, then further into individual sentiment counts.

#### Feedback Records

<img src="data/Feedback%20records.png" alt="Feedback records" width="80%">

Searchable, filterable table of the actual customer feedback text behind all the charts above.

#### Processing Pipeline

<img src="data/overview%20clickable%20pipeline.png" alt="Processing pipeline" width="80%">

A clickable pipeline strip showing the stages each feedback record moves through before it reaches the dashboard. Click any stage to see what happens in that step.

</details>

<details>
<summary><strong>Escalation features</strong></summary>

### Escalations (ESC) - What's costing us money

The Escalations page zeroes in on the feedback that turned into costly tickets, showing which categories drive them, where they get routed, and where the biggest reduction opportunities are.

#### Flow Strip

<img src="data/flow%20strip.png" alt="Flow strip" width="80%">

Visual funnel showing how feedback narrows down from all feedback → escalations → leadership, framing how much volume actually turns into costly tickets.

#### Category ESC Breakdown

<img src="data/category%20esc%20break.png" alt="Category ESC breakdown" width="80%">

Categories ranked by escalation volume, with indicators flagging whether each one escalates at an above or below average rate.

#### Routing Pie Chart

<img src="data/routing%20pie%20chart.png" alt="Routing pie chart" width="80%">

Breakdown of where escalations get routed (Executive / Agency / Internal), with clickable segments to filter.

#### Top Issue Classifications

<img src="data/top%20issue%20classification.png" alt="Top issue classifications" width="80%">

Bar chart of the most common issue classifications, with click-to-highlight that feeds directly into the reduction calculator.

#### Reduction Opportunity Calculator

<img src="data/reduction%20opportunity%20calculator.png" alt="Reduction opportunity calculator" width="80%">

Per-issue savings estimates with custom preventable percentages, a methodology explanation, and 3 recommended actions per issue type (37 issues covered).

#### ESC Tickets

<img src="data/esc%20tickets.png" alt="ESC tickets" width="80%">

Scrollable list of the actual escalation records, each opening into a full detail modal.

</details>

<details>
<summary><strong>Sentiment features</strong></summary>

### Sentiment - What are customers actually saying

The Sentiment page focuses on how customers actually feel, scoring every record and letting you filter down to the exact feedback behind the numbers.

#### Total Records Analyzed

<img src="data/total%20analyzed.png" alt="Total records analyzed" width="80%">

Headline count of every record scored across all channels, next to a plain-language explanation of the +1.0 to -1.0 satisfaction scale and the positive/negative/neutral thresholds.

#### Sentiment KPI Cards

<img src="data/kpi%20cards.png" alt="Sentiment KPI cards" width="80%">

Positive, negative, and neutral totals shown as cards. Click any card to filter the feedback list down to just that sentiment.

#### Sentiment Over Time

<img src="data/sentiment%20over%20time.png" alt="Sentiment over time" width="80%">

Rolling-average line chart showing how sentiment trends week over week.

#### Customer Feedback

<img src="data/Customer%20feedback.png" alt="Customer feedback" width="80%">

Drillable list of the actual customer records, sorted by sentiment score so the most positive and most negative rise to the top. Records are clickable, showing feedback based on the active filters.

</details>

<details>
<summary><strong>Settings</strong></summary>

Two accessibility options: dark mode and colorblind mode.

#### Dark Mode

<img src="data/dark%20mode.png" alt="Dark mode" width="80%">

Turns the whole dashboard dark for comfortable viewing in low light.

#### Colorblind Mode

<img src="data/color%20blind%20mode.png" alt="Colorblind mode" width="80%">

Swaps the positive, negative, and neutral colors for a colorblind safe palette across every chart and label, so the data stays readable for colorblind users.

</details>

---

<a id="business-impact"></a>

<img src="data/impact%20and%20whats%20next.png" alt="Impact & What's Next" width="100%">

**What this delivers**

- **Endorsed and adopted.** The Group Vice President of Customer Operations endorsed the dashboard, and the department is adopting its design and framework for future use.
- **One source of truth.** Consolidates feedback from four separate channels into a single view, replacing hours of manual gathering and spreadsheet reading with an instant overview.
- **Problems ranked by cost, not guesswork.** Surfaces the top issues alongside their estimated savings, so teams know exactly where to cut escalations first.
- **A direct line to savings.** The built in calculator translates escalation volume into an estimated preventable cost, using an adjustable prevention rate and a per case cost. Every escalation avoided removes customer credits, cross department labor, and potential legal costs, so reducing them converts straight into dollars saved.
- **Enterprise insight for about $40.** Built entirely with Kiro and no costly third party software, and ready to deploy today on the company's existing tools.
- **Bottom line.** Analysts spend less time analyzing and more time acting, and the business sees measurable cost savings.

<details>
<summary><strong>Future improvements</strong></summary>

To run this for real, the biggest step is turning it into an autonomous pipeline rather than a one time export.

- **Autonomous data pipeline:** move from the current data lake to a data lakehouse so feedback flows in and updates on its own, with no manual steps.
- **Scheduled refresh:** refresh the dashboard weekly, or even daily, instead of a single static snapshot.
- **Wider time range:** cover a full year or more so trends are clearer and more reliable.
- **Broader coverage:** expand beyond mobile call data to capture escalations across all products and channels.

</details>

---

<a id="data-sources"></a>

<img src="data/data%20source%20header%203.png" alt="Data Sources" width="100%">

The dashboard ingests feedback from 4 channels, each with different formats and characteristics. All 4 are centralized into one unified dataset with 4 attributes: unique customer ID, date/time, actual feedback text, and source (which channel it came from).

| Channel | Volume | What it is | Raw Format |
|---------|--------|------------|------------|
| **Calls** | ~90K records | Mobile customer feedback from any customer calling in | Excel (.xlsx), queried from SQL Server/Redshift, AI generated based on real data structure |
| **Emails** | ~200 records | Direct customer feedback sent to the company | Plain text (.txt), AI generated (originals contained too much PII) |
| **Social Media** | ~460 records | Posts from the company's Reddit community | JSON, scraped from Reddit |
| **Surveys** | ~86K records | Feedback surveys across Mobile, Internet, Video, and general service | Excel (.xlsx), queried from SQL Server/Redshift, AI generated based on real data structure |

<details>
<summary><strong>Click to see raw data examples</strong></summary>

<br>

### Calls:
<img src="data/call%20data.png" alt="Call Data Sample" width="80%">

### Emails:
<img src="data/email%20data.png" alt="Email Data Sample" width="80%">

### Social:
<img src="data/Social%20data.png" alt="Social Media Data Sample" width="80%">

### Surveys:
<img src="data/survey%20data.png" alt="Survey Data Sample" width="80%">

</details>

---

<a id="the-pipeline"></a>

<img src="data/pipeline%20header%202.png" alt="The Pipeline" width="100%">

Raw feedback goes through 6 stages before it reaches the dashboard:

<table>
  <tr>
    <td width="80" align="center"><img src="data/icon-raw-feedback.svg" width="50" alt="Raw Feedback"></td>
    <td><strong>Raw Feedback</strong><br>We pull in customer feedback from all four channels: phone calls, emails, social media posts, and surveys. Each source looks completely different, so at this point nothing lines up.</td>
  </tr>
  <tr>
    <td width="80" align="center"><img src="data/icon-normalize.svg" width="50" alt="Normalize"></td>
    <td><strong>Clean &amp; Combine</strong><br>Everything is cleaned up and reshaped into one consistent format. The clutter, like email signatures and social media handles, is stripped out so every piece of feedback can be compared fairly.</td>
  </tr>
  <tr>
    <td width="80" align="center"><img src="data/icon-nlp-classify.svg" width="50" alt="NLP Classify"></td>
    <td><strong>Categorize</strong><br>The system reads each piece of feedback and automatically sorts it into one of 17 issue types, such as billing, connectivity, or outages. This is what lets us count and rank problems without anyone reading every message by hand.</td>
  </tr>
  <tr>
    <td width="80" align="center"><img src="data/icon-sentiment.svg" width="50" alt="Sentiment"></td>
    <td><strong>Score the Mood</strong><br>Each record gets a satisfaction score, from very happy to very upset. It works even on messy, informal language like slang and social posts, so we can tell how customers actually feel.</td>
  </tr>
  <tr>
    <td width="80" align="center"><img src="data/icon-ecaf-mapping.svg" width="50" alt="Ticket Mapping"></td>
    <td><strong>Connect to Costly Cases</strong><br>We link feedback to the cases that eventually became expensive escalations. This surfaces the early warning signs, so similar issues can be caught before they grow.</td>
  </tr>
  <tr>
    <td width="80" align="center"><img src="data/icon-dashboard.svg" width="50" alt="Dashboard"></td>
    <td><strong>Dashboard</strong><br>All of it is packaged into an interactive dashboard where anyone can filter, drill into the details, and surface the biggest problems in seconds, with no technical skills required.</td>
  </tr>
</table>

---

<a id="machine-learning--nlp"></a>

<img src="data/machine%20learning%20header%202.png" alt="Machine Learning & NLP" width="100%">

**Built within real constraints:** a standard laptop, network restrictions, company regulations, no pre-trained data, and a one week time limit.

Working within those limits, the system uses lightweight models to categorize and score all 176K records. Here is what each part does and why. Expand the sections below for the technical detail.

> **Note:** The pipeline code is built around internal company systems and data structures, so it is kept private. This public repo ships the interactive dashboard and fully synthetic sample data; the section below explains the approach.

| Component | Model / Method | What it does |
|-----------|---------------|--------------|
| **Turning text into data** | TF-IDF | Turns written feedback into numbers the computer can compare, giving weight to the words that matter most |
| **Sorting feedback** | LinearSVC | Places each piece of feedback into the right issue category |
| **Catching the obvious cases** | Keyword matching | Flags clearly worded mentions first for high accuracy, then lets the model handle the rest |
| **Reading "not" correctly** | Negation detection | Understands phrases like "not a billing issue" so feedback isn't filed under the wrong category |
| **Measuring the mood** | VADER | Rates how positive or negative each message is, quickly and without expensive hardware |
| **Spotting costly cases early** | Escalation scoring | Flags the feedback most likely to turn into an expensive escalation |

<details>
<summary><strong>Click for the architecture</strong></summary>

The whole pipeline was built backward from one requirement, then solved one problem at a time.

**Step 1: The target was 17 categories.**
Real escalations are filed under 17 issue categories, so every piece of feedback had to land in one of those same 17 buckets. Everything downstream was designed to hit that.

**Step 2: How do we label feedback into those 17 categories?**
Hand-labeling thousands of records wasn't realistic. Instead I started from a keyword lexicon a coworker had already built on similar feedback data, mapped to the same 17 categories. Matching feedback against those curated keywords gave a reliable first pass and solved the core question of how to categorize anything at all.

**Step 3: How do we turn the text into numbers?**
The model needs numbers, not words. TF-IDF converts each piece of feedback into a numerical fingerprint that weights the words that actually separate one category from another. I chose TF-IDF specifically because company regulations ruled out sending data to outside services or pulling in large pre-trained models. TF-IDF runs fully offline on the data we already had.

**Step 4: What about feedback the keywords miss, and new data later?**
TF-IDF and keywords are limited. They only recognize the exact vocabulary they were fit on, they have no understanding of meaning or context, and they don't adapt when feedback is worded in a new way or when more data gets added. To cover those gaps, a LinearSVC model learns the patterns behind the keyword labels and generalizes them to text the keywords alone would never catch. It trains in seconds, handles the sparse TF-IDF output well where models like random forests and neural nets struggle, and stays fully interpretable.

**Step 5: How do customers actually feel?**
With feedback categorized, sentiment was next. VADER was a strong fit because it ships with a pre-built lexicon of rated words, so it needs no training data, handles slang and informal text, and scores each record from very negative to very positive in milliseconds (which matters since sentiment re-scores on every filter change).

**Step 6: Which feedback is about to become expensive?**
Finally, signal words combined with the sentiment score flag the records most likely to turn into a costly escalation. That is what drives the Escalations page. Using an estimated callback cost per case, I turned that volume into a dollar figure, which is what powers the reduction opportunity calculator.

**Result: 95.8% weighted F1 score across the 17 categories.** Versus a transformer like BERT, the accuracy difference on these well-separated categories is marginal and not worth the added compute, dependencies, and complexity, especially under the constraints above.

</details>

---

<a id="tools--why"></a>

<img src="data/tools%20header%202.png" alt="Tools & Why" width="100%">

The project splits into two parts: a backend that handles the data and model work, and a frontend built with AWS Kiro. Expand each below to see the tools and why they were chosen.

<details>
<summary><strong>Backend (data pipeline and models)</strong></summary>

The classification and sentiment pipeline that turns raw feedback into the categorized, scored data behind the dashboard.

| Tool | Purpose | Why this one? |
|------|---------|---------------|
| **Data lake** | Where the raw source data lives; queried directly to study its schema and structure | Standard enterprise storage for large, raw, multi source data |
| **SQL** | Querying the real source data to understand its schema and structure | Let me model the synthetic data accurately on the real tables |
| **Python** | The data pipeline, NLP, and classification | Industry standard for ML and NLP work |
| **scikit-learn** | TF-IDF vectorization and the LinearSVC classifier | Fast, reliable, runs offline with no GPU |
| **VADER (NLTK)** | Sentiment scoring | Handles informal and social media language with no training data |
| **Pandas / NumPy** | Cleaning, merging, and transforming the data | Core data science toolkit |
| **Web scraping (Reddit API)** | Collecting real social media feedback from a public Reddit community | Brought in genuine customer language to complement the synthetic data |
| **Regex** | Word boundary keyword matching and negation detection | Precise, transparent text matching for the keyword tier |
| **JSON data layer** | Processed results exported as static JSON, loaded by the frontend through the browser fetch API | Keeps the app fully static, no server or live API to maintain |

</details>

<details>
<summary><strong>Frontend (built with AWS Kiro)</strong></summary>

The dashboard interface was built and iterated using Kiro, which generated the HTML, CSS, and JavaScript.

| Tool | Purpose | Why this one? |
|------|---------|---------------|
| **AWS Kiro** | AI development environment used to build the dashboard | Accelerated the frontend build and design iteration |
| **HTML / CSS** | Structure and the custom design system (dark mode, accessibility) | Full control over the look with no framework overhead |
| **JavaScript (vanilla)** | Interactivity, filter state, and drill-downs | Zero build step, single file, runs anywhere |
| **Chart.js 4.4** | Interactive charts and visualizations | Lightweight, canvas-based, flexible plugin API |
| **Netlify** | Production hosting | Free CDN, instant deploys, custom domains |

</details>

---

<a id="skills-demonstrated"></a>

<img src="data/skills%20header%202.png" alt="Skills Demonstrated" width="100%">

**Machine Learning & NLP:**
`Machine Learning` `Natural Language Processing` `Text Classification` `Sentiment Analysis` `TF-IDF` `LinearSVC` `VADER`

**Data & Analytics:**
`Exploratory Data Analysis` `ETL Pipeline Design` `Data Lake / Lakehouse` `Data Cleaning & Wrangling` `Web Scraping` `Feature Engineering` `Data Visualization` `Cost Impact Modeling`

**Engineering & Product:**
`Interactive Dashboard Design` `Frontend (HTML, CSS, JavaScript)` `Chart.js` `Responsive Design` `Accessibility` `AI-Assisted Development`

**Tools:**
`Python` `SQL` `scikit-learn` `Pandas` `NumPy` `NLTK` `Regex` `AWS Kiro` `Netlify`

---

<a id="run-locally"></a>

<img src="data/run%20locally%20header%202.png" alt="Run Locally" width="100%">

```bash
git clone https://github.com/kenecu1/customer-feedback-intelligence-dashboard.git
cd customer-feedback-intelligence-dashboard
python -m http.server 8000
# Open http://localhost:8000
```

Or just visit the **[Live Demo](https://iridescent-taiyaki-2af528.netlify.app/)**.

---

<p align="center">
  <strong>Built by Kenneth Chow · Summer 2026 Internship Project</strong><br>
  <sub>All data is synthetic. No real customer information is included.</sub>
</p>
