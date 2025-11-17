Funnel Performance Dashboard - SaaS Conversion Analysis

![Dashboard Preview](dashboard_screenshot.png)

 Project Overview

Analyzed customer conversion funnel for a B2B SaaS company tracking 88,000 monthly visitors through a 5-stage journey: Visit → Signup → Activation → Payment → Retention. Built an interactive Power BI dashboard to identify conversion bottlenecks, quantify revenue leakage, and provide data-driven recommendations for optimization.

 Business Problem

The company was experiencing significant customer dropoff throughout their conversion funnel but lacked visibility into:

- Where potential customers were leaving the journey

- Which stages had the biggest impact on revenue

- How conversion rates were trending over time

- Whether performance varied across channels and regions

Without clear insights, marketing and product teams couldn't effectively prioritize their optimization efforts or allocate resources to the highest-impact areas.

 Tools & Technologies

- Power BI Desktop: Interactive dashboard design, data modeling, cross-filtering visualizations

- DAX (Data Analysis Expressions): Calculated measures for conversion rates, period-over-period comparisons, dropoff percentages

- Power Query: Data transformation, cleaning, and preparation across 5 source tables

 Key Metrics Tracked

| Metric | Current Value | Change vs Previous Period |

|--------|---------------|---------------------------|

| Total Visitors | 88K | -8% 📉 |

| Signup Rate | 12.5% | ↓ 5.9% 📉 |

| **Activation Rate** | 71.0% | ↑ 2.1% 📈 |

| **Paid Conversion Rate** | 58.4% | ↓ 10.2% 📉 |

| **Retention Rate** | 70.0% | ↑ 0.2% 📈 |

### Funnel Stage Counts

- Visitors: 88,000

- Signups: 11,000 (12.5% conversion)

- Activated: 8,000 (71.0% conversion)

- Paid Customers: 5,000 (58.4% conversion)

- Retained: 3,500 (70.0% retention)

 Key Insights & Recommendations

 CRITICAL ISSUE #1: Massive Signup Bottleneck

What I Found:

Only 12.5% of 88K visitors convert to signups, with this rate declining 5.9% from the previous period. The signup stage has an 87.5% dropoff rate - meaning 77,000 potential customers leave without even creating an account.

Business Impact:

This is the largest leakage point in the entire funnel. Even a modest 2-percentage-point improvement in signup rate would generate:

- +1,760 additional signups per month

- 1,250 additional activated users (at 71% activation rate)

- 730 additional paid customers (at 58.4% paid conversion)

- Estimated $438K in additional annual recurring revenue (assuming $50/month average customer value)

Root Cause Hypotheses:

- Unclear value proposition on landing pages

- Lengthy or confusing signup form

- Lack of social proof or trust signals

- Poor mobile signup experience

- Aggressive signup requirements

Recommendations:

1. Conduct user research - Exit surveys and session recordings to identify friction points

2. A/B test simplified signup flows - Reduce required fields from current state to email + password only

3. Analyze traffic quality by source - Identify which channels bring high-intent visitors (use Channel slicer)

4. Implement exit-intent popups with compelling value propositions and testimonials

5. Add trust indicators - Display user count, company logos, security badges near signup CTA

6. Optimize mobile experience - 40-60% of traffic is likely mobile; ensure seamless mobile signup

 CRITICAL ISSUE #2: Paid Conversion Rate Decline

What I Found:

Paid conversion rate dropped 10.2 percentage points to 58.4%, meaning 41.6% of activated users** (3,328 users monthly) are using the product but not converting to paid customers despite finding enough value to activate.

Business Impact:

This 10.2% decline represents significant revenue loss:

- 3,328 users monthly are engaging with the product but not paying

- If this decline is sustained, annual impact could be ~$2M in lost ARR (assuming $50/month average)

- The gap between activation (71%) and payment (58.4%) suggests a pricing or value perception issue, not a product quality problem

Root Cause Hypotheses:

- Trial period too short to demonstrate full value

- Pricing perceived as too high relative to value delivered

- Missing features in paid tiers that free users expect

- Unclear differentiation between free and paid tiers

- Competitors offering better pricing

- Poor in-app upsell messaging

Recommendations:

1. Implement behavior analysis - Identify what activated non-payers do differently (feature usage, engagement frequency)

2. Create targeted nurture campaigns - Email sequences highlighting premium features activated users haven't tried

3. Test limited-time discount offers - "Upgrade within 7 days and get 20% off for 3 months"

4. Review pricing strategy- Consider adding a lower-priced tier to capture price-sensitive users

5. Add in-app prompts - Showcase premium features contextually when free users hit usage limits

6. Conduct user interviews - Talk to 10-15 activated non-payers to understand objections (price, features, competition)

7. Implement usage-based triggers - If user performs high-value action, immediately show upgrade prompt

8. Add social proof - Show testimonials from similar users who upgraded and saw specific benefits

 SUCCESS #3: Strong Activation Rate Validates Product-Market Fit

What I Found:

71% activation rate (up 2.1%) significantly exceeds B2B SaaS industry benchmarks (typically 40-60%). This means once users sign up, they quickly find value and engage with the core product.

Business Impact:

- High activation proves strong product-market fit - The product delivers on its promise

- Users who try the product, use it - this validates product quality

- The problem isn't the product itself; it's getting people to sign up and converting them to paid

- This high activation rate is a competitive advantage and strong signal for investors/stakeholders

Strategic Implications:

- Product team is doing excellent work - maintain current onboarding flow

- Marketing should emphasize activation success: "71% of users complete setup in their first session"

- Focus optimization resources on top-of-funnel (signup) and monetization (paid conversion), not product changes

- Activation rate could potentially reach 75-80% with minor tweaks

Recommendations:

1. Document the onboarding flow - Capture what's working so well and replicate across other touchpoints

2. Use as marketing proof point - "Join 8,000+ activated users" in campaigns

3. Leverage power users - Activated users are your best advocates; create referral program

4. Reduce time-to-activation further- If 71% activate now, analyze what prevents the other 29%

5. Create case studies - Interview highly-activated users about their "aha moment"

6. Shift investment upstream - Reallocate product resources to signup optimization and paid conversion

 OPPORTUNITY #4: Retention Optimization Potential

What I Found:

70% retention rate is solid and stable over time, but **30% of paying customers still churn**. With 5,000 paid users monthly, that's **1,500 customers leaving** each period.

Business Impact:

At $50/month average customer value:

- $75,000 in monthly recurring revenue lost to churn

- $900,000 in annual recurring revenue that could potentially be recovered

- Each 5 percentage point improvement in retention = $225K additional ARR

- Retention improvement compounds over time (retained customers have higher LTV)

Churn Patterns to Investigate:

- When does churn happen? (First 30 days vs later?)

- Which features do churned users NOT use?

- Are there early warning signals (decreased login frequency, support tickets, etc.)?

- Do certain customer segments churn more (country, channel, plan type)?

Recommendations:

1. Build churn prediction model - Use usage patterns, support interactions, feature adoption to identify at-risk customers

2. Implement proactive retention campaigns - Auto-triggered when user shows churn signals

3. Create win-back sequences - Automated emails to recently churned users with incentives to return

4. Conduct exit surveys - Understand why the 30% leave; categorize reasons (price, features, competition, no longer needed)

5. Develop customer health score - Combine product usage + support tickets + feature adoption into single metric

6. Offer annual plans with discount - Lock in longer commitments (e.g., "Pay annually, save 20%")

7. Implement success check-ins - Proactive outreach at 7, 30, 90 days to ensure customer success(seen this work quite a number of time)

8. Create community/forum - Increase product stickiness through peer connections

 

## 🔍 Interactive Analysis Capabilities

The dashboard includes Month/Year, Channel, and Country slicers enabling stakeholders to drill down into specific segments for deeper analysis. This self-service functionality empowers teams to answer their own questions without analyst support.

Channel Performance Analysis

By filtering the Channel slicer, users can:

- Compare full-funnel performance by traffic source (Organic, Paid Ads, Social, Referral)

- Identify which channels bring high-quality leads (high activation + payment rates vs just high volume)

- Optimize marketing budget allocation based on ROI, not just top-of-funnel metrics

- Example insight: "Organic search may have lower volume but 2x higher paid conversion than paid social"

Geographic Analysis

The Country slicer enables:

- Regional comparison of conversion behavior

- Identification of high-potential markets for expansion

- Localization prioritization based on volume + conversion quality

- Example insight: "US visitors convert to paid at 65% vs 45% global average - consider US-focused campaigns"

Temporal Analysis

The Month/Year slicer supports:

- Month-over-month performance tracking for regular reporting

- Seasonal pattern identification for forecasting

- Campaign impact measurement (before/after analysis)

- Year-over-year growth comparisons

Cross-Filtering Functionality

All visuals interact with each other:

- Click a stage in the funnel chart → dropoff and trends update to show that cohort

- Select a time period → all metrics recalculate for that window

- Choose a channel → see full funnel performance for that traffic source

 

 Business Impact Summary

| Opportunity Area | Current State | Target State | Potential Impact | Priority |

|------------------|---------------|--------------|------------------|----------|

| Improve signup rate| 12.5% | 15% (+2.5pp) | +$625K ARR | 🔴 CRITICAL |

| Recover paid conversion | 58.4% | 65% (+6.6pp) | +$660K ARR | 🔴 CRITICAL |

| Reduce churn rate | 30% | 25% (-5pp) | +$225K ARR | 🟡 HIGH |

| Optimize channel mix | Mixed performance | Focus on high-ROI | +$150K efficiency | 🟡 MEDIUM |

Total Addressable Opportunity: $1.66M+ in annual recurring revenue

Return on Investment:

If implementing these recommendations costs $100K (analyst salary + tools + campaigns), the ROI is 16.6x within 12 months.

 Skills Demonstrated

This project showcases proficiency in:

✅ Funnel Analysis - Multi-stage conversion tracking, bottleneck identification, cohort behavior

✅ Business Metrics Expertise - Deep understanding of SaaS KPIs (CAC, LTV, MRR, churn, activation)

✅ Data Visualization - Clean, intuitive dashboard design optimized for executive audiences

✅ DAX Proficiency - Complex calculated measures, time intelligence, period comparisons

✅ Data Modeling - Relationships across 5 tables, proper star schema implementation

✅ Strategic Thinking - Translating data insights into prioritized, actionable business recommendations

✅ Revenue Impact Quantification - Tying every finding directly to dollar amounts and ROI

✅ Stakeholder Communication - Clear, concise presentation of technical findings to non-technical audiences

✅ Self-Service BI - Building tools that empower others to explore data independently

 Project Files

- README.md - This comprehensive analysis document

- dashboard\_screenshot.png - Full dashboard preview image

- funnel\_dashboard.pbix - Power BI source file with all measures and visuals

- DATA\_DICTIONARY.md - Detailed metric definitions, formulas, and business logic

- METHODOLOGY.md - Analysis approach, assumptions, and technical implementation details

- data/ - Folder containing raw Excel source data and data documentation

 How to Use This Project

 For Recruiters/Hiring Managers

1. Review this README for business insights and strategic thinking

2. Check DATA\_DICTIONARY.md to see technical depth (metric definitions, DAX logic)

3. Open funnel\_dashboard.pbix in Power BI Desktop to explore interactively

4. View METHODOLOGY.md to understand analytical approach

 For Fellow Analysts

1. Download data/funnel\_data.xlsx to see raw data structure

2. Follow steps in METHODOLOGY.md to understand transformation process

3. Open .pbix file to examine DAX measures and data model

4. Adapt this framework for your own funnel analysis projects

 To Replicate This Analysis

1. Prepare data in similar format (5 tables: Traffic, Signups, Activation, Subscriptions, Retention)

2. Load into Power BI and create relationships on UserID

3. Build DAX measures following patterns in DATA\_DICTIONARY.md

4. Design visuals following layout in dashboard screenshot

5. Add interactivity with slicers

 Connect With Me

This analysis demonstrates my ability to:

- Build production-ready BI dashboards that drive business decisions

- Identify high-impact optimization opportunities that directly affect revenue

- Communicate complex technical findings to non-technical stakeholders clearly

- Think strategically about business problems, not just execute technical tasks

- Quantify value - every recommendation tied to dollars and ROI

Let's talk about how I can bring this same analytical rigor to your team.

*Built with Power BI Desktop | Analysis Period: January 2024 - August 2025 | Last Updated: November 2025*

*This project analyzes a fictional B2B SaaS dataset created for portfolio demonstration purposes.*
