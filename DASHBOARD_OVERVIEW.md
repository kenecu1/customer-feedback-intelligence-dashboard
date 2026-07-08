# Customer Feedback Analytics Dashboard — Walkthrough

All data is synthetic (fake) for compliance purposes. This demonstrates how real data would be explored.

---

## Starting Point: Overview

When you open the dashboard, you land on the Overview page. Think of it as the starting point where you can see everything at a high level, then click deeper into anything that catches your eye.

---

## Step 1: Data Sources

At the top you'll see four cards, one for each source of feedback: Calls, Emails, Social Media, and Surveys. Each card shows a small donut chart with the sentiment split (positive, negative, neutral) and the total number of records from that source.

Try this: Click one of the source cards. The entire dashboard filters to show only feedback from that source. Click it again to deselect.

---

## Step 2: Trends Over Time

Below the source cards is a chart showing feedback volume over time as a weekly average, plus a cumulative sum line. This tells you if volume is going up, down, or staying steady.

---

## Step 3: Customer Journey

Next you'll see four journey stages laid out: Sales, Order, Activation, and Post Activation/Repair. These represent where a customer is in their lifecycle when they gave feedback. They're ranked by volume so you can immediately see which stage generates the most complaints.

Try this: Click a journey stage. Everything on the page filters to show only feedback from that stage. This is how you'd narrow in on, say, activation issues specifically.

---

## Step 4: Top Issue Categories

Below the journey is a bar chart showing the top issue categories (billing, connectivity, cancellation, etc.). The number next to each bar tells you how many records fall into that category.

Try this: Click a category bar to filter the dashboard to just that issue. You can now see trends, sentiment, and raw records for just that one category.

---

## Step 5: Raw Feedback Records

At the bottom is a table of individual feedback records. You can see the date, source, category, sentiment, and a preview of the text.

Try this: Click any row. A popup opens showing the full feedback text with all details. This is the actual voice of the customer.

---

## Moving to Escalations

Now that you've explored the overview, click "Escalations" in the left sidebar (or the "Escalations" button at the bottom of the overview). This takes you to the escalations focused page. Any filters you already set carry over.

---

## Escalations Page

This page answers: which issues become ECAFs, how often, and where do they get routed?

**What you see from top to bottom:**

1. A banner summarizing the full pipeline (176K feedback records narrowed down to 750 ECAFs, how many reached CEO, how many went to an agency like FCC/BBB).

2. A flow strip showing the conversion at each stage with percentages.

3. A risk vs volume bubble chart. Each bubble is a category. Bigger bubble = more ECAFs. Position shows how risky vs how loud a category is.

4. A narrative breakdown table. Each row is a category showing: how many ECAFs it generated, the rate, the top issue classification, and what percentage went to CEO or to an external agency.

5. Charts showing routing (CEO vs Agency vs CCED) and top issue classifications.

6. KPI summary cards.

7. The actual ECAF ticket list at the bottom.

**Try this walkthrough:**

- Click a bubble in the risk chart to filter to that category
- Or click a row in the narrative table — it scrolls you down to the tickets filtered to that category
- Click a bar in the Top Issue Classifications chart to filter tickets to that specific issue type
- Click any ticket card to open the full ECAF detail: customer recount, issue classification, how it was routed, assigned department, everything
- When you're done filtering, click "clear" to reset

---

## Moving to Sentiment

Click "Sentiment" in the left sidebar. This page shows how customers feel broken down by category and source.

You'll see positive/negative/neutral percentages at the top, then charts showing which categories have the most negative sentiment and how sentiment trends over time.

At the bottom is a "Most Negative Feedback" list. Click any item to read the full record.

---

## Features Available on Every Page

**Filters (top dropdowns):**
- Time Period — narrow to a date range
- Source — show only one source
- Category — focus on one issue type

These update everything on the page at once and persist when you switch between pages.

**AI Insights (sparkle icon, top right corner):**
Click the sparkle icon. Cards pop up with a summary of what's notable in your current view. If you've filtered to billing, the AI summary talks about billing. Switch to escalations, it updates. Click the icon again to close.

**Dark Mode:**
Click the gear icon (Settings) in the sidebar to toggle dark mode.

**Feedback Popups:**
Anywhere you see feedback text or a ticket, click it. A popup opens with the full detail and a blurred background. Click outside or press Escape to close.

---

## The Story It Tells (Top to Bottom)

1. Here's all our feedback, here's where it comes from (Overview, source cards)
2. Here's when it's happening (trends chart)
3. Here's where customers are in their journey when they complain (journey stages)
4. Here's what they're complaining about (category chart)
5. Here's which complaints become escalations (Escalations page)
6. Here's where those escalations end up — CEO, agency, or handled internally (routing and narrative table)
7. Here's the individual ticket if you want to read the full story (ECAF modal)
8. Here's how customers feel overall and which areas are most negative (Sentiment page)

---

## Summary

Everything is interactive. Click charts, click rows, click tickets. Filters work across all pages. The AI icon gives you quick summaries. Explore freely and let me know what you think could be added, changed, or removed.
