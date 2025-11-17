**Methodology**



Project Overview



This document outlines the approach, tools, and assumptions used in building the Funnel Performance Dashboard.



---



### Project Objectives



1\. \*\*Visualize\*\* the complete customer conversion journey from visitor to retained customer

2\. \*\*Identify\*\* bottlenecks and leakage points in the funnel

3\. \*\*Quantify\*\* the revenue impact of conversion rate changes

4\. \*\*Enable\*\* stakeholder self-service analysis through interactive filtering

5\. \*\*Track\*\* performance trends over time to inform strategic decisions



---



**Data Source**



Dataset Description

\- Source: Fictional B2B SaaS company funnel metrics

\- Granularity: Monthly aggregated data with daily records

\- Volume: 88,000 monthly visitors tracked through 5 funnel stages



Data Structure

The dataset includes:

\- Fact Table: Funnel events (visitor actions, timestamps, stage completions)

\- Dimension Tables: 

&nbsp; - Date dimension (month, year, date hierarchies)

&nbsp; - Channel dimension (traffic source categorization)

&nbsp; - Geography dimension (country-level data)



---



**Tools \& Technologies**



Primary Tools



| Tool | Purpose | Specific Use |

|------|---------|--------------|

| Power BI Desktop| Dashboard development | Data visualization, report design, interactive elements |

| DAX| Measure creation | Calculated metrics, KPIs, period comparisons |

| Power Query | Data transformation | Data cleaning, shaping, type conversions |



Why Power BI?

\- Interactive filtering and drill-down capabilities

\- Strong DAX calculation engine for complex metrics

\- Easy sharing via Power BI Service for stakeholder access

\- Professional visualizations with minimal custom coding



---



&nbsp;Analysis Process



Phase 1: Data Preparation (Power Query)



Steps Taken:



1\. Data Import: Loaded raw funnel event data

2\. Data Cleaning:

&nbsp;  - Removed duplicate records

&nbsp;  - Handled null values in channel and country fields

&nbsp;  - Standardized date formats

3\. Data Transformation:

&nbsp;  - Created date hierarchy (Year > Month > Date)

&nbsp;  - Categorized channels into standard groups

&nbsp;  - Added calculated columns for stage identification

4\. Data Modeling:

&nbsp;  - Established relationships between fact and dimension tables

&nbsp;  - Set up one-to-many relationships with proper cardinality

&nbsp;  - Created a date table for time intelligence functions



---



\### Phase 2: Metric Development (DAX)



\*\*Key Measures Created:\*\*

```dax

// Example DAX patterns used (pseudocode)



Total Visitors = SUM(facts\_Traffic\[Visitors])



Signup Conversion Rate = 

DIVIDE(

&nbsp;   DISTINCTCOUNT(facts\_Signups\[UserID]),

&nbsp;   \[Total Visitors],

&nbsp;   0

)



Previous Month Signups = CALCULATE(\[Funnel Signups], 

&nbsp;   DATEADD('Date'\[Date], -1, MONTH))



Signup Rate Change % = 

&nbsp;   DIVIDE(

&nbsp;       \[Signup Rate] - \[Signup Rate Previous Month],

&nbsp;       \[Signup Rate Previous Month],

&nbsp;       0

&nbsp;   ) \* 100



Dropoff % = DIVIDE(

&nbsp;   \[Visitors] - \[Signups],

&nbsp;   \[Visitors],

&nbsp;   0

) \* 100

```



Measure Categories:

\- Base Counts: Visitor, signup, activation, paid conversion, retention counts

\- Conversion Rates: Stage-to-stage conversion percentages

\- Period Comparisons: Month-over-month changes

\- Dropoff Calculations: Percentage of users lost at each stage



---



&nbsp;Phase 3: Dashboard Design



Design Principles:

1\. Executive-First Layout: KPI cards at top for quick scanning

2\. Visual Hierarchy: Most important metrics (with alerts) get prominence

3\. Progressive Disclosure: High-level overview → detailed charts → interactive filters

4\. Consistent Color Coding: 

&nbsp;  

Visualization Choices:



| Chart Type | Purpose | Rationale |

|------------|---------|-----------|

| KPI Cards| Display key metrics with period comparison | Quick at-a-glance performance check |

| Funnel Chart| Show stage-by-stage progression | Standard for conversion funnel analysis |

| Horizontal Bar Chart | Display dropoff percentages | Easy comparison of stage leakage |

| Line Chart | Track trends over time | Identify patterns and seasonality |



---



&nbsp;Phase 4: Interactivity Implementation



Slicers Added:

1\. Month/Year Slicer: Enables temporal analysis and period comparison

2\. Channel Slicer: Filters data by marketing/traffic source

3\. Country Slicer: Enables geographic segmentation



Cross-Filtering Behavior:

\- All visuals respond to slicer selections

\- Funnel chart filters dropoff and trend charts

\- Maintains context across all dashboard elements



---



&nbsp;Analytical Approach



Conversion Funnel Analysis



Analyzed each stage independently:

1\. Volume Analysis: How many users at each stage?

2\. Conversion Rate Analysis: What percentage move to next stage?

3\. Dropoff Analysis: Where are we losing the most users?

4\. Trend Analysis: Are rates improving or declining?



Comparative Analysis



\- Period-over-Period: Month vs previous month comparison

\- Channel Comparison: Performance across traffic sources

\- Geographic Comparison: Regional variation in conversion



&nbsp;Impact Quantification

For each insight, calculated:

\- Current vs target performance gap

\- Revenue impact of improvements

\- Prioritization based on potential ROI



---



&nbsp;Key Assumptions



&nbsp;Business Assumptions

1\. Activation Definition: User completes core product action (e.g., creates first project, invites team member)

2\. Retention Window: Measured at 30 days post-payment (not lifetime retention)

3\. Average Customer Value: Assumed $50/month for revenue impact calculations

4\. Attribution Model: Last-touch attribution for channel analysis



Technical Assumptions

1\. \*\*Data Accuracy\*\*: Assumed tracking is accurate with <5% error margin

2\. \*\*Unique Users\*\*: Visitor count represents unique individuals (not sessions)

3\. \*\*Stage Progression\*\*: Users can only move forward through stages (no backward flow)

4\. \*\*Time Lag\*\*: No consideration of time delay between stages (e.g., signup to activation duration)



\### Analytical Assumptions



1. External Factors: Analysis doesn't account for market conditions, competitor actions, or macroeconomic factors

2\.  Causation: Correlations identified don't necessarily imply causation without further testing



---



&nbsp;Limitations \& Constraints



Data Limitations

\- No User-Level Detail: Aggregated data limits cohort analysis capabilities

\- Missing Context: Don't have campaign details, product changes, or external event data



&nbsp;Analysis Limitations

\- Snapshot vs Cohort: Current analysis is snapshot-based, not true cohort retention

\- Single Attribution: Last-touch only; doesn't show full customer journey

\- No Segmentation: Limited ability to analyze user personas or behavior clusters



&nbsp;Dashboard Limitations

\- Static Benchmarks: Industry averages shown are generalized, not company-specific

\- No Predictive Analytics: Dashboard is descriptive/diagnostic, not predictive

\- Performance: Large date ranges may impact load time



---



&nbsp;Quality Assurance



&nbsp;Validation Steps

1\. Metric Verification: Cross-checked calculated rates against manual Excel calculations

2\. Logic Testing: Verified period comparisons show correct month-over-month changes

3\. Filter Testing: Confirmed slicers properly filter all visuals

4\. Edge Case Testing: Tested with null values, zero divisions, single-month selections



Review Process

1\. Self-Review: Checked for calculation errors, typos, formatting issues

2\. Stakeholder Feedback: Incorporated business user feedback on layout and metrics

3\. Iterative Refinement: Made multiple revisions based on usability testing



---







&nbsp;References \& Resources



&nbsp;Industry Benchmarks Sources

\- SaaS conversion rate benchmarks: Industry reports and analysis

\- Retention standards: B2B SaaS average metrics



&nbsp;Technical Documentation

\- Microsoft Power BI Documentation

\- DAX function reference

\- Power Query M language guide



---



&nbsp;Skills Applied



This project demonstrates proficiency in:

\- ✅ Data modeling and relationships

\- ✅ DAX measure development (aggregations, time intelligence, conditional logic)

\- ✅ Power Query data transformation

\- ✅ Dashboard UX/UI design

\- ✅ Business metrics analysis (SaaS-specific KPIs)

\- ✅ Insight generation and recommendation development

\- ✅ Stakeholder communication



---



\*For detailed metric definitions, see `DATA\_DICTIONARY.md`\*  

\*For business insights and recommendations, see `README.md`\*



---



\*Last Updated: November 2025\*

