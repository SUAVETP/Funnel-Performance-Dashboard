**-Data Dictionary**



&nbsp;Overview

This document defines all metrics, dimensions, and calculations used in the Funnel Performance Dashboard.



---



 **📊 Key Metrics**



Funnel Stage Counts



| Metric | Definition |

|--------|------------|

| \*\*Funnel Visitors\*\* | Total unique visitors who entered the top of the funnel |

| \*\*Funnel Signups\*\* | Visitors who completed account registration | 

| \*\*Funnel Activated\*\* | Signups who completed initial activation action |

| \*\*Funnel Paid\*\* | Activated users who converted to paying customers |

| \*\*Funnel Retained\*\* | Paid customers still active after 30 days |



---



&nbsp;Conversion Rates



| Metric | Definition | Formula | Business Meaning |

|--------|------------|---------|------------------|

| \*\*Signup Rate\*\* | Percentage of visitors who create accounts | `(Signups / Visitors) × 100` | Measures top-of-funnel conversion effectiveness |

| \*\*Activation Rate\*\* | Percentage of signups who complete activation | `(Activated / Signups) × 100` | Indicates onboarding quality and time-to-value |

| \*\*Paid Conversion Rate\*\* | Percentage of activated users who become paying customers | `(Paid / Activated) × 100` | Measures monetization effectiveness |

| \*\*Retention Rate\*\* | Percentage of paid customers retained after 30 days | `(Retained / Paid) × 100` | Indicates product stickiness and customer satisfaction |



---



&nbsp;Period Comparisons



| Metric | Definition | Calculation |

|--------|------------|-------------|

| \*\*Previous Month Value\*\* | Metric value from prior period | `CALCULATE(\[Metric], DATEADD(Date\[Date], -1, MONTH))` |

| \*\*Change %\*\* | Percentage change vs previous period | `(\[Current Value] - \[Previous Value]) / \[Previous Value] × 100` |



---



Dropoff Metrics



| Metric | Definition | Formula | Interpretation |

|--------|------------|---------|----------------|

| \*\*Signup Dropoff %\*\* | Percentage of visitors who don't sign up | `((Visitors - Signups) / Visitors) × 100` | Higher = more friction at signup |

| \*\*Activation Dropoff %\*\* | Percentage of signups who don't activate | `((Signups - Activated) / Signups) × 100` | Indicates onboarding issues |

| \*\*Paid Conversion Dropoff %\*\* | Percentage of activated users who don't pay | `((Activated - Paid) / Activated) × 100` | Suggests pricing or value perception gaps |

| \*\*Retention Dropoff %\*\* | Percentage of paid customers who churn | `((Paid - Retained) / Paid) × 100` | Measures customer satisfaction and product fit |



---



&nbsp;Dimensions



| Field | Description | Values | Use Case |

|-------|-------------|--------|----------|

| \*\*Month/Year\*\* | Time period of measurement | Jan 2024, Feb 2024, etc. | Trend analysis, period comparison |

| \*\*Date\*\* | Specific date | YYYY-MM-DD format | Daily granularity analysis |







| Field | Description | Example Values | Use Case |

|-------|-------------|----------------|----------|

| \*\*Channel\*\* | Marketing/traffic source | Organic Search, Paid Social, Email, Direct, Referral | Channel performance comparison, budget optimization |

| \*\*Country\*\* | User's geographic location | United States, United Kingdom, Canada, Nigeria, etc. | Geographic analysis, localization decisions |



---



&nbsp;Funnel Stages Explained



Stage 1: Visitors

\- \*\*Definition\*\*: Unique users who land on the website/app

\- \*\*Entry Point\*\*: Any page visit, tracked via analytics

\- \*\*Success Metric\*\*: High traffic volume from quality sources



Stage 2: Signups  

\- \*\*Definition\*\*: Visitors who complete account registration

\- \*\*Entry Criteria\*\*: Submit registration form with valid email

\- \*\*Success Metric\*\*: Signup rate >15% (industry benchmark)



Stage 3: Activated

\- \*\*Definition\*\*: Users who complete a key activation action

\- \*\*Activation Criteria\*\*: Complete onboarding, use core feature, or reach "aha moment"

\- \*\*Success Metric\*\*: Activation rate >60%



Stage 4: Paid

\- \*\*Definition\*\*: Activated users who become paying customers

\- \*\*Conversion Criteria\*\*: Complete payment and subscribe to paid plan

\- \*\*Success Metric\*\*: Paid conversion >50%



Stage 5: Retained

\- \*\*Definition\*\*: Paying customers still active after retention period

\- \*\*Retention Period\*\*: 30 days from initial payment

\- \*\*Success Metric\*\*: Retention rate >70%



---



Benchmarks \& Targets



| Metric | Current | Industry Average | Target |

|--------|---------|------------------|--------|

| Signup Rate | 12.5% | 10-15% | 15% |

| Activation Rate | 71.0% | 40-60% | 75% |

| Paid Conversion | 58.4% | 50-70% | 65% |

| Retention Rate | 70.0% | 60-80% | 75% |



---



&nbsp;Data Quality Notes



\- \*\*Data Freshness\*\*: Updated monthly

\- \*\*Historical Range\*\*: January 2024 - sept 2025

\- \*\*Data Source\*\*: Fictional B2B SaaS company dataset

\- \*\*Known Limitations\*\*: 

&nbsp; - Activation definition may vary by use case

&nbsp; - Channel attribution uses last-touch model



---



Related Documentation



\- See `METHODOLOGY.md` for analysis approach and assumptions

\- See `README.md` for key insights and business recommendations



---



\*Last Updated: November 2025\*

