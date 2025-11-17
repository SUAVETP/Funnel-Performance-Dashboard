Raw Data



Overview

This folder contains the raw dataset used to build the Funnel Performance Dashboard. The data tracks a B2B SaaS customer journey from initial website visit through retention.



---



File Description



File: `saas\_funnel\_dataset\_2024\_2025.xlsx` 



Contents: 

\- B2B SaaS customer funnel data across 5 tables

\- Tracks visitors through signup, activation, subscription, and retention stages



---



Data Structure



The Excel file contains 5 separate tables representing different stages of the customer funnel:



Table 1: Traffic

Tracks all visitors to the website/platform.



| Column | Data Type | Description | Example Values |

|--------|-----------|-------------|----------------|

| Date | DateTime | Date of the visit | 2024-01-01 00:00:00 |

| Source | Text | Marketing/traffic channel | Organic, Paid Ads, Referral, Social |

| Visitors | Integer | Number of unique visitors from that source on that date | 2154, 1028, 756 |



Purpose: Represents the top of the funnel - all users who land on the platform.



---



Table 2: Signups

Tracks users who completed account registration.



| Column | Data Type | Description | Example Values |

|--------|-----------|-------------|----------------|

| UserID| Text | Unique identifier for each user | U1000, U1001, U1002 |

| SignupDate | DateTime | Date user created account | 2024-01-03 00:00:00 |

| Channel | Text | Source that brought the user | Paid Ads, Social, Organic, Referral |

| Country | Text | User's geographic location | UK, CA, US, NG |



Purpose: Users who converted from visitors to registered accounts.



---



Table 3: ActivationLogs

Tracks users who completed the activation action (e.g., first key product use).



| Column | Data Type | Description | Example Values |

|--------|-----------|-------------|----------------|

| UserID | Text | Unique user identifier (links to Signups table) | U1000, U1001, U1002 |

| FirstActionDate | DateTime | Date user completed activation action | 2024-01-10 00:00:00 |

| Activated| Text (Y/N) | Whether user successfully activated | Y, N |



Purpose: Identifies which signed-up users actually engaged with the core product.



Note: Some users have blank `FirstActionDate` and `Activated = N`, indicating they signed up but never activated.



---



&nbsp;Table 4: Subscriptions

Tracks users who converted to paid customers.



| Column | Data Type | Description | Example Values |

|--------|-----------|-------------|----------------|

| UserID| Text | Unique user identifier (links to Signups/ActivationLogs) | U1000, U1001, U1002 |

| Plan| Text | Subscription plan chosen | (appears blank in sample - may include Basic, Pro, Enterprise) |

| TrialStart | DateTime | Date free trial began | 2024-01-03 00:00:00 |

| TrialEnd | DateTime | Date free trial ended | 2024-01-17 00:00:00 |

| PaymentDate | DateTime | Date user made first payment | (blank if never paid) |

| Status| Text | Current subscription status | Churned, Active, Trial |



Purpose: Tracks which activated users became paying customers and their subscription lifecycle.



Note: Sample data shows churned users with no `PaymentDate`, indicating they tried but didn't convert to paid.



---



&nbsp;Table 5: Retention

Tracks whether paying customers remained active over time.





| Column | Data Type | Description | Example Values |

|--------|-----------|-------------|----------------|

| UserID | Text | Unique user identifier (links to Subscriptions) | U1000, U1001, U1002 |

| Status | Text | Retention status | Churned, Active |

| ChurnDate | DateTime | Date user stopped using the product | 2024-01-17 00:00:00 |

| RenewalCount| Integer | Number of times user renewed subscription | 0, 1, 2, 3+ |



Purpose: Measures long-term customer retention and churn patterns.



Note: Sample shows churned users with `RenewalCount = 0`, meaning they didn't renew after initial trial/payment period.



---



Table Relationships



The tables are connected via UserID:

```

Traffic (Date + Source) 

&nbsp;   ↓

Signups (UserID created)

&nbsp;   ↓

ActivationLogs (UserID activates or not)

&nbsp;   ↓

Subscriptions (UserID subscribes or churns)

&nbsp;   ↓

Retention (UserID retained or churned)

```



Data Flow:

1\. Visitors arrive via different sources (Traffic table)

2\. Some visitors sign up (Signups table)

3\. Some signups activate (ActivationLogs table)

4\. Some activated users subscribe (Subscriptions table)

5\. Some subscribers are retained (Retention table)



---



&nbsp;Data Characteristics



\- Multiple countries tracked (US, UK, CA, NG, and others)

\- Country data available from signup stage onward



&nbsp;Marketing Channels

\- Organic: Direct/organic traffic

\- Paid Ads: Paid advertising campaigns

\- Social: Social media sources

\- Referral: Referral traffic from other sites



---



&nbsp;Data Processing in Power BI



This raw data was transformed in Power BI using Power Query:



Transformations Applied

1\. Date Formatting: Standardized all date columns to proper DateTime format

2\. Data Type Corrections: Set appropriate types (integers for counts, text for categorical data)

3\. Relationship Modeling: Created relationships between tables based on UserID

4\. Calculated Columns: Added month/year columns for time-based filtering

5\. Aggregations: Calculated funnel stage totals and conversion rates using DAX



&nbsp;Key DAX Measures Created

\- Total Visitors (from Traffic table)

\- Signup Count (COUNT of UserID in Signups)

\- Activation Rate (% of Signups with Activated = Y)

\- Paid Conversion (COUNT of UserID in Subscriptions with PaymentDate)

\- Retention Rate (% of paid users with Status = Active)

\- Period-over-period comparisons

\- Dropoff percentages at each stage



See `METHODOLOGY.md` for detailed analysis approach.



---





&nbsp;How to Use This Data



&nbsp;Option 1: Explore in Excel

1\. Open `saas\_funnel\_dataset\_2024\_2025.xlsx`

2\. Navigate between the 5 sheet tabs

3\. Use Excel pivot tables for basic analysis



&nbsp;Option 2: Load into Power BI

1\. Open Power BI Desktop

2\. Get Data → Excel

3\. Select all 5 tables

4\. Load and create relationships on UserID

5\. Build visuals and measures



&nbsp;Option 3: Replicate the Dashboard

1\. Follow steps in `METHODOLOGY.md`

2\. Or open `SaaS\_funnel\_analysis.pbix` to see the completed analysis



---





\## 📚 Related Documentation



\- See `DATA\_DICTIONARY.md` for detailed metric definitions

\- See `METHODOLOGY.md` for analysis approach and DAX formulas

\- See main `README.md` for business insights and recommendations



---



\*This data represents a fictional B2B SaaS company for portfolio demonstration purposes.\*



\*Last Updated: November 2025\*

