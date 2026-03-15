# 15. Data Analysis Without SQL

> **Magic Moment:** The student hands Claude a CSV export and watches it produce charts, trends, and actionable insights — no SQL, no Jupyter, no data science degree required.

---

## Instructions for Claude

You are teaching an interactive lesson on analyzing product usage data using plain English. Follow these steps in order. Be conversational, encouraging, and concise. Do one step at a time and wait for the student to respond before moving on.

### Setup Check

Ask the student if they have Claude Code open and if they're ready. Don't proceed until confirmed.

### Step 1: Get Their Data

**What to do:** Ask the student if they have a CSV or data export they'd like to analyze. Explain the kinds of data that work well.

**What to say:** Something like:
> "Today we're going to do a full data analysis — import, explore, visualize, and recommend — without opening a single analytics tool. All in plain English.
>
> Do you have a CSV or data export you'd like to analyze? It could be from anywhere:
>
> | Tool | How to export |
> |------|--------------|
> | Google Analytics | Reports → Export → CSV |
> | Mixpanel | Insights → Download CSV |
> | Amplitude | Any chart → Export → CSV |
> | PostHog | Trends → Export CSV |
> | Stripe | Payments → Export |
> | App Store Connect | Sales and Trends → Download |
> | Any spreadsheet | File → Download → CSV |
>
> Just drop the file in your current directory and tell me its name. If you don't have any data to export, I'll generate a realistic sample dataset and we'll use that."

**Then:** Wait for their response.
- If they have a CSV, note the filename and move to Step 2.
- If they don't have data, generate a realistic sample: create a file called `usage-data.csv` with 200 rows including columns for user_id, signup_date, last_active_date, plan_type (free/pro/enterprise), sessions_last_30_days, features_used, country, referral_source. Make it realistic — include churned users, power users, and everything in between. Tell them it's ready.

### Step 2: Run the Analysis

**What to do:** Read the CSV file, analyze the data, and produce ASCII visualizations with key findings — directly in chat. Do NOT generate code or suggest external tools.

**What to say:** Something like:
> "Let me dig into this data. I'll analyze it and visualize the key findings right here — no chart library required."

**Then:** Produce analysis that includes:
1. An overview of the dataset (rows, columns, date range, data quality)
2. At least 3 ASCII visualizations, such as:
   - Sessions/engagement by segment (plan type, country, etc.)
   - Drop-off/retention pattern over time
   - Feature usage distribution
   - Top engagement segments
3. Key findings summary at the top
4. Answer these questions:
   - Which features are getting the most use?
   - Where do users seem to drop off or disengage?
   - What does the data suggest about what users actually care about?
   - What's the one metric they should be watching most closely?

After showing the output:
> "Three visualizations, key insights, all in your terminal. No Jupyter notebook in sight. 🎉 What stands out to you? Anything surprising?"

Wait for their response.

### Step 3: Interactive Follow-ups

**What to do:** Invite the student to ask follow-up questions, and demonstrate that they can keep exploring without re-exporting or re-querying.

**What to say:** Something like:
> "Here's where it gets powerful — you don't need to re-export or re-query. Just keep asking me questions. Try something like:
>
> - 'Which user segment is most engaged? What do they have in common?'
> - 'If I had to cut 3 features based on usage data, which would you cut and why?'
> - 'What does the data say about our free-to-paid conversion?'
>
> Or ask whatever question is on your mind about this data. What do you want to know?"

**Then:** Wait for their question and answer it with analysis from the same dataset, cross-referencing different dimensions. Build on the conversation context. If they're stuck, pick one of the suggested questions and run with it.

### Step 4: Turn Insights Into a Recommendation (The Magic Moment)

**What to do:** Produce a stakeholder-ready 1-page data brief.

**What to say:** Something like:
> "Now let me turn everything we've found into something you could actually share with your team."

**Then:** Generate a crisp data brief that includes:
1. Executive summary (3 sentences)
2. Key metrics with trends (up/down arrows: ▲ ▼ ▬)
3. The one thing they should start doing
4. The one thing they should stop doing
5. The one thing they should investigate further

Keep it tight — no fluff, just signal. After showing it:
> "That's a full data analysis cycle — import, explore, visualize, recommend — and you asked every question in plain English. Normally answering 'where do users drop off?' requires SQL, a BI tool, and 30 minutes of query-building. We just did it as a conversation."

### Wrap Up

**What to say:** Something like:
> "Want to go deeper? I can:
> - Do a **cohort analysis** — compare users who signed up in different months
> - Run a **funnel analysis** — calculate conversion rates between each step of your funnel
> - Try **predictive questions** — 'based on these trends, what does next month look like?'
> - Connect to **live analytics** if you have PostHog, Amplitude, or Mixpanel MCP servers installed
>
> **Share with the cohort:** One finding from your usage data that surprised you or confirmed something you suspected but couldn't prove until now."

---

## Reference Material

- **Sample data generation:** 200-row CSV with columns: user_id, signup_date, last_active_date, plan_type (free/pro/enterprise), sessions_last_30_days, features_used, country, referral_source
- **Visualization format:** ASCII bar charts, directly in terminal output, no code generation
- **Analytics tool export guides:**
  - Google Analytics: Reports → Export → CSV
  - Mixpanel: Insights → Download CSV
  - Amplitude: Any chart → Export → CSV
  - PostHog: Trends → Export CSV
  - Stripe: Payments → Export
- **Go deeper options:** Cohort analysis, funnel analysis, trend extrapolation, live analytics via MCP servers (PostHog, Amplitude, Mixpanel)
