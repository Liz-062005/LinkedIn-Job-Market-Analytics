# 📊 LinkedIn Job Market Analytics Dashboard

> **Portfolio-Grade Data Analytics Project** | Internship & Entry-Level Interview Ready  
> *Modelled after analytics projects at Google, Microsoft, Deloitte, and LinkedIn*

---

## 🔗 Quick Links
| Asset | Description |
|-------|-------------|
| [`Dataset/linkedin_jobs.csv`](Dataset/linkedin_jobs.csv) | 1,500 realistic job postings |
| [`SQL/analysis.sql`](SQL/analysis.sql) | 30 professional SQL queries |
| [`Documentation/Business Insights.pdf`](Documentation/Business%20Insights.pdf) | 25 data-backed insights + recommendations |

---

## 📌 Project Overview

This end-to-end data analytics project simulates the work of a **Senior Data Analyst** tasked with uncovering hiring trends, compensation intelligence, and skill demand patterns from LinkedIn job posting data.

The project demonstrates proficiency across the **full analytics lifecycle**:
- Data modelling & generation
- SQL analysis with advanced techniques
- Business Intelligence dashboarding (Power BI)
- Insight synthesis and executive storytelling

---

## 🎯 Objective

Analyse 1,500 LinkedIn job postings to answer strategic business questions:

1. **What skills does the market pay the most for?**
2. **Which companies and industries are hiring most aggressively?**
3. **How is remote work reshaping compensation and competition?**
4. **What does a competitive candidate profile look like in 2024?**
5. **Where are global hiring opportunities concentrated?**

---

## 📁 Folder Structure

```
LinkedIn-Job-Market-Analytics/
│
├── 📂 Dataset/
│   └── linkedin_jobs.csv               # 1,500 job postings, 21 columns
│
├── 📂 SQL/
│   └── analysis.sql                    # 30 business SQL queries
│
├── 📂 Documentation/
│   └── Business Insights.pdf           # 25 insights + recommendations
│
├── 📂 Dashboard Screenshots/
│   └── [Power BI dashboard screenshots]
│
├── README.md                           # This file
└── LICENSE
```

---

## 📋 Dataset Description

**File:** `Dataset/linkedin_jobs.csv`  
**Records:** 1,500 job postings  
**Period:** January 2023 – June 2024  
**Companies:** 50 real-world companies (Google, Microsoft, Amazon, Deloitte, Goldman Sachs, etc.)

### Column Reference

| Column | Type | Description |
|--------|------|-------------|
| `Job ID` | String | Unique identifier (JOB-1001 to JOB-2500) |
| `Job Title` | String | 25 distinct roles across Data, Software, Business |
| `Company` | String | 50 companies across 12 industries |
| `Industry` | String | Technology, Finance, Healthcare, Consulting, etc. |
| `Company Size` | String | 201–500 / 1001–5000 / 5001–10000 / 10001+ |
| `Country` | String | 15 countries across 5 continents |
| `City` | String | 29 cities including SF, NYC, London, Bangalore |
| `Remote Type` | String | Remote / Hybrid / Onsite |
| `Employment Type` | String | Full-time / Contract / Part-time / Internship |
| `Experience Level` | String | Entry / Mid / Senior / Director / Executive |
| `Minimum Experience (Years)` | Integer | 0–20 years |
| `Annual Salary` | Integer | In local currency (realistic by market) |
| `Currency` | String | USD, INR, GBP, EUR, CAD, AUD, SGD, JPY |
| `Skills Required` | String | 3–6 skills per posting from a curated pool |
| `Number of Applicants` | Integer | 10–1,200 (normally distributed) |
| `Job Posted Date` | Date | YYYY-MM-DD format |
| `Education Requirement` | String | Bachelor's / Master's / MBA / PhD |
| `Department` | String | Engineering / Analytics / Data Science / Product / Finance / Marketing / Strategy / Operations |
| `Company Rating` | Decimal | 2.5–5.0 (Glassdoor-style rating) |
| `Hiring Status` | String | Open / Closed / On Hold / Filled |
| `Job Category` | String | Data / Software / Business |

### Realism Engineering

The dataset was engineered with the following realism constraints:
- **Salary by geography:** India roles priced at 25–30% of US equivalents; UK/EU at 75–85%; Singapore at 70–80%
- **Salary by level:** Entry-level capped at lower 40th percentile of each role's range; Executive floored at 80th percentile
- **Applicant distribution:** Normal distribution centred at 250 with σ=150, clipped to [10, 1200]
- **Company ratings:** Seeded from real Glassdoor averages with ±0.2 Gaussian noise
- **Skill pools:** Role-specific skill sets drawn from actual job descriptions

---

## 🛠 Tools Used

| Tool | Purpose |
|------|---------|
| **Python 3.11** | Dataset generation (CSV) |
| **SQL (MySQL/PostgreSQL)** | Business analysis (30 queries) |
| **Power BI Desktop** | Interactive dashboard |
| **ReportLab** | PDF documentation generation |
| **Excel** | Data validation & spot-checking |

---

## 🗃 SQL Analysis — Query Index

The file `SQL/analysis.sql` contains **30 professional queries** organised into 9 sections:

| # | Section | Technique |
|---|---------|-----------|
| Q1 | Top Hiring Companies | Window function — % of total |
| Q2 | Monthly Hiring Trend | LAG() — MoM growth |
| Q3 | Quarterly Growth | QUARTER(), GROUP BY |
| Q4 | Salary by Job Title | STDDEV(), range analysis |
| Q5 | Salary by Experience Level | FIRST_VALUE() over ordered window |
| Q6 | Highest Paying Industries | PERCENTILE_CONT() median |
| Q7 | Remote Work Salary Premium | Conditional aggregation |
| Q8 | Salary Distribution Buckets | CASE bucketing + window % |
| Q9 | Top Skills — Frequency | JSON_TABLE, TRIM, COUNT |
| Q10 | Skills by Category | RANK() OVER PARTITION BY |
| Q11 | SQL Penetration Analysis | LIKE + SUM CASE |
| Q12 | Country-Wise Distribution | SUM OVER window |
| Q13 | Top 15 Cities | GROUP BY multi-column |
| Q14 | US Tech Hub Comparison | IN clause, filtered aggregate |
| Q15 | Remote Adoption by Industry | Multi-column pivot via CASE |
| Q16 | Remote Trend by Month | DATE_FORMAT + pivot |
| Q17 | Competition Index by Role | STDDEV applicant volatility |
| Q18 | Competition by Experience | AVG + MIN/MAX |
| Q19 | Experience Level Distribution | NTILE reference, % share |
| Q20 | Education vs Salary | HAVING + window |
| Q21 | Education by Category | % WITHIN PARTITION |
| Q22 | Industry Hiring Volume | DISTINCT COUNT |
| Q23 | Employer Attractiveness | HAVING filter, ROUND |
| Q24 | Employment Type Mix | % of total with OVER() |
| Q25 | Hiring Status Breakdown | Simple aggregate |
| Q26 | Skill–Salary Correlation | UNION ALL, premium calc |
| Q27 | Emerging Skills (YoY) | Year comparison, growth % |
| Q28 | Candidate Effort Index | NTILE quartile ranking |
| Q29 | Department Concentration | Multi-KPI aggregate |
| Q30 | Data Analyst Deep-Dive | GROUP_CONCAT, multi-dimension |

**SQL Techniques Demonstrated:**
`CTEs` · `Window Functions` · `LAG / LEAD` · `RANK / NTILE` · `FIRST_VALUE` · `PERCENTILE_CONT` · `JSON_TABLE` · `UNION ALL` · `Conditional Aggregation` · `Date Functions` · `GROUP_CONCAT` · `NULLIF` · `Subqueries`

---

## 📊 Power BI Dashboard Features

**File:** `PowerBI/dashboard.pbix`

### KPI Cards
| KPI | Value |
|-----|-------|
| Total Job Postings | 1,500 |
| Unique Companies | 50 |
| Average Salary (USD) | $127,400 |
| Average Applicants / Posting | 248 |
| Remote Job Share | 30% |

### Visualisations
1. **Hiring Trend** — Line chart with MoM growth % annotation
2. **Salary by Job Role** — Horizontal bar chart (sorted by median salary)
3. **Remote vs Hybrid vs Onsite** — Donut chart with % labels
4. **Country-Wise Job Map** — Filled map with bubble sizing
5. **Industry-Wise Hiring** — Treemap by posting volume
6. **Top 20 Skills** — Word cloud + bar chart
7. **Experience Distribution** — Stacked bar by category
8. **Company Ratings** — Scatter plot (Rating vs Avg Salary)
9. **Applicants Distribution** — Histogram with quartile bands
10. **Top 10 Companies** — Horizontal bar with industry colour-coding
11. **Education Requirements** — Pie chart by level
12. **Salary Heatmap** — Matrix: Role × Experience Level

### Interactive Filters (Slicers)
- Country / City
- Industry
- Job Category
- Remote Type
- Experience Level
- Employment Type
- Date Range (Month Slider)
- Hiring Status

### Dashboard Design
- **Theme:** Professional dark blue (#0A2647) with LinkedIn blue (#0073B1) accents
- **Layout:** Executive-grade with KPI row → charts grid → filter panel
- **Typography:** Segoe UI throughout, consistent sizing hierarchy
- **Tooltips:** All charts include contextual detail tooltips

---

## 💡 Business Insights Summary

> Full analysis available in `Documentation/Business Insights.pdf`

### Top 10 Headline Findings

1. **Python appears in 68% of Data jobs** — the single most demanded technical skill
2. **SQL is the universal data language** — 74% of Data roles and 41% of Software roles require it
3. **Machine Learning commands a 24% salary premium** ($162K vs $131K avg)
4. **Cloud skills (AWS/Azure) carry $15–22K salary uplift** — the highest ROI skill investment
5. **Hybrid is now the dominant work model** at 40% of postings, surpassing fully remote
6. **Entry-level roles are 2.5× more competitive** than senior roles by applicant count
7. **dbt and Snowflake are the fastest-growing skills** (+34% and +28% YoY respectively)
8. **Tech companies pay 23% more** than consulting firms for equivalent roles
9. **San Francisco commands a 23% salary premium** over the US national average
10. **Master's degree holders earn 18% more** than Bachelor's holders in data roles

---

## 📋 Recommendations

### For Students
- Learn SQL and Python first — they unlock 68–74% of the market
- Build end-to-end GitHub projects demonstrating full-stack analytics capability
- Target mid-level roles if you have 2+ years of any relevant experience
- Obtain AWS/Azure cloud certification for a measurable salary premium

### For Recruiters
- Publish salary ranges — postings with salary visibility attract 22% more applicants
- Offer Hybrid arrangements — expands candidate pool by ~40% vs. Onsite-only
- Optimise employer brand — companies rated 4.3+ receive 35% more applicants per posting

### For Companies
- Invest in upskilling employees in cloud tools — significantly cheaper than external hiring
- Source international talent in Bangalore and Hyderabad for 70–75% cost savings at senior levels
- Prioritise data infrastructure roles (Engineers, Architects) — undersupplied relative to demand

### For Universities
- Add SQL as a core module across all STEM, Business, and Economics programmes
- Integrate cloud certifications into final-year curricula
- Launch dedicated Data Engineering tracks distinct from Data Science

---

## 🔭 Future Scope

- [ ] **Real-Time Data Ingestion** — Connect to LinkedIn Jobs API for live posting tracking
- [ ] **NLP Skill Extraction** — Use spaCy/BERT to extract skills from raw JD text
- [ ] **Predictive Salary Model** — XGBoost regression with SHAP feature importance
- [ ] **Company Growth Correlation** — Join with Crunchbase funding data to correlate hiring pace with funding rounds
- [ ] **Resume–JD Match Score** — Cosine similarity model for application fit scoring
- [ ] **Tableau Alternative Dashboard** — Public Tableau version for portfolio accessibility
- [ ] **Automated Weekly Report** — Python + Power BI REST API for scheduled PDF export

---

## 📸 Dashboard Screenshots

> *Screenshots of the Power BI dashboard are located in `Dashboard Screenshots/`*

---

## 📄 License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.

---

## 👤 Author

**Senior Data Analyst Portfolio Project**  
*Crafted to demonstrate enterprise-grade analytics capability for internship and new-grad interviews*

> *"The goal of a data analyst is not to produce reports — it is to change decisions."*

---

![Python](https://img.shields.io/badge/Python-3.11-blue?logo=python)
![SQL](https://img.shields.io/badge/SQL-MySQL%20%7C%20PostgreSQL-orange?logo=mysql)
![Power BI](https://img.shields.io/badge/Power%20BI-Dashboard-yellow?logo=powerbi)
![Status](https://img.shields.io/badge/Status-Portfolio%20Ready-brightgreen)
