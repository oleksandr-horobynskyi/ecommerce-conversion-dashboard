# E-commerce Conversion Dashboard

## Project Overview
Full-stack e-commerce analytics project analyzing user conversion funnel on a 3-month dataset from Google Analytics 4.

**Status:** Completed ✅

## Key Results
- **354,857 unique sessions**
- **4,745 purchases**
- **1.34% purchase conversion rate**
- **$353,027 total revenue**

## Critical Insights

### 🔴 Biggest Drop-off: View Item → Add to Cart (73% loss)
This is the major conversion bottleneck. Users view products but don't add them to cart.

### 📊 Traffic Drivers
- **Google (Direct):** 127,023 sessions (highest)
- **Direct:** 82,362 sessions
- **Google Merchandise:** 28,043 sessions

### 💻 Device Distribution
- **Web/Desktop:** 2,768 orders (dominates)
- **iOS:** 560 orders
- **Android:** 407 orders

### 📍 Landing Page Impact
- Homepage (`/`): 159,195 sessions
- Strong correlation between landing page and funnel progression

## Funnel Analysis

| Stage | Sessions | CR from Previous |
|-------|----------|-----------------|
| Session Start | 354,856 | 100.0% |
| View Item | 75,271 | 21.2% |
| Add to Cart | 14,909 | 19.8% |
| Begin Checkout | 10,853 | 72.8% |
| Add Shipping | 10,853 | 100.0% |
| Add Payment | 6,663 | 61.4% |
| Purchase | 4,745 | 71.2% |

## Technical Implementation

### BigQuery SQL Pipeline
**Features used:**
- `CONCAT()` — Creating unique user_session_id from user_pseudo_id + ga_session_id
- `PARSE_DATE()` — Converting YYYYMMDD format to DATE
- `REGEXP_EXTRACT()` — Parsing landing_page from page_location URL
- `LEFT JOIN` — Combining traffic dimensions (source, medium, campaign) with device dimensions
- Funnel event filtering and sessionization

**Data Source:**
- BigQuery public dataset: `bigquery-public-data.ga4_obfuscated_sample_ecommerce`
- Period: 3 months of real Google Analytics 4 data

### Tableau Visualization
**Dashboard Components:**
1. **Funnel Visualization** — Step-by-step conversion rates
2. **KPI Cards** — Sessions, Orders, Revenue, CR to Purchase
3. **Trend Analysis** — Sessions and CR dynamics over time
4. **Traffic Analysis** — Source, Medium, Campaign breakdown
5. **Landing Page Performance** — Top 10 pages by sessions
6. **Device OS / Purchase Segmentation** — Cross-tabulation analysis

## Key Recommendations

1. **Urgent:** Investigate why 73% of users don't add items to cart
   - A/B test product page layout
   - Simplify "Add to Cart" button
   - Reduce friction in early funnel

2. **High Priority:** Optimize mobile experience
   - Mobile has lower conversion than desktop
   - Test mobile-specific checkout flow

3. **Medium Priority:** Analyze landing page quality
   - Some landing pages drive better funnel progression
   - Replicate successful patterns across other pages

## Files

### SQL
- `sql/ecommerce_conversion_query.sql` — Full BigQuery query with all logic

### Data
- `data/sample_data_description.md` — Dataset schema and field descriptions

### Documentation
- `docs/CASE_STUDY.md` — Detailed methodology and findings

## Visualization

**Tableau Public Dashboard:** [Add your Tableau link here]

## Tech Stack
- **BigQuery** — SQL data processing
- **Tableau** — Interactive dashboards
- **Google Analytics 4** — Data source
- **SQL** — Data engineering (CONCAT, PARSE_DATE, REGEXP_EXTRACT, JOINs)

## Author
Oleksandr Horobynskyi — Data Analyst  
LinkedIn: linkedin.com/in/oleksandr-horobynskyi  
Tableau: public.tableau.com/app/profile/oleksandr.horobinskyi
