# Insurance-Data-Analysis
## Report Link

https://app.powerbi.com/links/RYTMa_XOb5?ctid=5bcca112-41e4-4d5e-a805-c5ba21ed65b6&pbi_source=linkShare

## Problem Statement

This project helps the insurance company analyze policy performance, premium income, claim patterns, and customer demographics. It addresses key business questions such as:

- Which policy types generate the highest premium revenue?

- What is the distribution of claims (Approved, Pending, Rejected) across policies?

- Which customer segments (by Age, Gender, Policy Type) file the most claims?

- How do premiums compare with claim payouts?

- What is the claim ratio (claims vs. coverage/premium) across policies?

- How does policy performance vary across time (monthly, quarterly, yearly)?

- How does customer sentiment from feedback reflect service quality?

- By analyzing these factors, decision-makers can optimize premium pricing, assess risk exposure, improve claim processing, and target profitable customer groups.

## Steps Followed

**Step 1:** Loaded dataset (InsuranceData.csv) into Power BI Desktop.

**Step 2:** Data cleaning in Power Query

Checked column distributions & quality.

Converted date fields (PolicyStartDate, PolicyEndDate, ClaimDate) into Date format.

Handled missing values in ClaimDate (no claim filed).

**Step 3:** Built relationships

Fact Table: Policies & Claims.

Dimension Tables: Customers (Age, Gender), Policy Types.

**Step 4:** Created DAX Measures

Total Premiums

Total Claims Paid

Claim Ratio

Average Premium per Policy

Number of Active Policies

Number of Claims (Approved, Rejected, Pending)

**Step 5:** Designed visuals

Top/Bottom Policy Types by Premiums & Claims.

Trend charts (Monthly & Yearly Premiums and Claims).

Claim Status distribution (Pie/Donut Chart).

Demographic analysis (Age vs. Claim Amount, Gender vs. Claim Count).

KPI Cards (Total Premiums, Total Coverage, Total Claims, Claim Ratio).

**Step 6:** Published interactive report to Power BI Service

## DAX Measures Used

Total Premiums = SUM(FactInsurance[PremiumAmount])

Total Claims Paid = SUM(FactInsurance[ClaimAmount])

Claim Ratio = DIVIDE([Total Claims Paid], [Total Premiums], 0)

Active Policies = DISTINCTCOUNT(FactInsurance[PolicyNumber])

Avg Premium = AVERAGE(FactInsurance[PremiumAmount])

Approved Claims = CALCULATE([Total Claims Paid], FactInsurance[ClaimStatus] = "Approved")


## Insights
### Policy Performance

Health & Auto policies contribute the maximum premium income.

Travel policies have high claim frequency but lower premium contributions.

### Claim Patterns

Around 55% claims are approved, 25% pending, 20% rejected.

Some policies have high claims-to-premium ratios, indicating higher risk.

### Customer Demographics

30–50 age group files the most claims.

Male customers contribute slightly higher premiums, but females show higher claim frequency.

### Premiums vs. Claims

Overall claim ratio is ~65%, meaning the company retains ~35% as underwriting profit.

Certain policy types (e.g., Travel) have claim ratios exceeding 80%, indicating risk.

### Time Trends

Q1 and Q4 show spikes in policy sales (renewal + festive offers).

Claims peak in monsoon season for Auto policies and winter for Health policies.

### Customer Feedback

Word Cloud sentiment analysis shows frequent words like “quick settlement”, “supportive”, “expensive”, “delay”.

<img width="461" height="570" alt="Image" src="https://github.com/user-attachments/assets/d9b35868-9bee-4f94-b278-08ec1300889e" />

Positive feedback highlights good claim settlement process, while negative feedback points to delays and high premium costs.

## Conclusion

This Insurance Dashboard provides a comprehensive view of policy, premium, and claim performance. With strong DAX measures and visuals, insurance managers can:

- Identify profitable vs. risky policy types.

- Optimize premium pricing models.

- Improve claim settlement efficiency.

- Target the right customer segments for business growth.
