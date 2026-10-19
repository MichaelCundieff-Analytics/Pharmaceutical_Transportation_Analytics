# Interview Talking Points

## 60–90 Second Project Explanation

“I wanted to apply my existing Python and analytics experience to pharmaceutical transportation, so
I built an independent project using public USAID shipment data. I analyzed 10,324 product lines
and organized them into 7,030 delivery groups.

The first challenge was making sure the results were trustworthy. Some product lines shared freight
costs, so counting every row as a shipment would distort the analysis. I verified the delivery identifiers
and first-line records, checked the cost references, and counted each delivery group once. I also kept
missing freight amounts separate and excluded ten conflicting schedules from delivery performance.

Then I built seven KPIs and eight interactive Plotly charts. The on-time rate was 88.6%.
Truck delivery groups had a higher observed late rate than air, and the highest 5% of numeric freight
amounts represented 28% of the recorded subtotal.

My recommendations were to investigate late deliveries by route and review high-value freight records
against invoices. I didn’t claim that switching modes would fix delays or that I had produced savings.
The project shows how I can validate data, communicate performance clearly, and turn findings into
practical next steps.”

## Three Findings to Discuss

1. **Recorded delivery reliability:** 88.6% on time, with 798 late groups
   out of 7,020. Late groups averaged 19.9 calendar days after schedule.
   On-time includes early delivery. It compares against the recorded scheduled date, which may have
   been revised; it is not necessarily an original-promise adherence measure.
2. **Mode differences:** Truck was 20.6% late (297/1,439)
   and air was 8.5% (388/4,539). This is a descriptive
   comparison of different delivery mixes, not evidence that mode caused the difference.
3. **Cost concentration:** 310 groups at or above the 95th percentile
   ($36,680) accounted for 28.0% of the separately recorded numeric freight subtotal.
   That creates a focused review list, not a proven savings opportunity. Numeric cost coverage was
   88.2% of delivery groups.

## Technical Skills Demonstrated

| Skill | What I did |
| --- | --- |
| Python proficiency | Used readable Pandas loading, filtering, conversion, grouping, and CSV exports |
| Data integrity | Checked missing values, duplicates, date consistency, numeric validity, first-line ownership, and shared references |
| Data visualization | Built eight interactive Plotly charts with consistent colors, labels, sample sizes, and business interpretations |
| KPI development | Defined seven headline KPIs and disclosed the different delivery and cost denominators |
| Analytical problem-solving | Distinguished product lines from delivery groups and preserved unusual observations |
| Business insight | Proposed route reviews, invoice reconciliation, and reporting controls tied to specific findings |

## Connection to the Cencora Transportation Specialist Role

This is an independent portfolio project demonstrating how I applied existing analytical skills to
pharmaceutical transportation data. It complements my professional analytics experience; it is not
professional transportation experience or work performed for Cencora.

The transferable workflow is validating operational records, monitoring delivery exceptions, making
performance visible, and explaining what deserves investigation. In a transportation team, I could
apply that approach to current shipment and invoice data after confirming the team's definitions and
operating process. The exact external job description was not available during this project, so these
are general transportation analytics connections rather than claims about specific Cencora duties.

## Five Potential Interview Questions

**1. How did you prevent double-counting?**

The raw data had multiple product lines per `ASN/DN #`. I verified one first-line record per identifier,
consistent country, mode, and actual date, and at most one numeric freight entry per group. I used the
first-line records for the group-level charts and checked shared references against the original IDs.
The group count describes reported delivery identifiers, not a count of trucks, packages, or trips.

**2. How did you handle missing costs and unusual records?**

I converted actual numeric amounts to a separate field and kept the original text. Bundled costs and
separate invoices stayed unavailable instead of becoming zero. I retained high costs and long delays.
I flagged administrative date issues and excluded only the ten conflicting schedules from delivery KPIs.

**3. Does the project show that air is better than truck?**

Air had a lower observed late rate in this dataset, but the routes, shipment sizes, years, and service
requirements differ. I would compare similar operating conditions and review milestones before
recommending a mode change. The same caution applies to the cost-quartile comparison.

**4. What operational recommendation would you prioritize?**

I would first review the late truck delivery groups by destination and period, then request carrier,
appointment, and milestone information to understand recurring issues. For costs, I would reconcile
the high-value freight list to invoices and shipment scope. Neither action assumes a specific cause.

**5. What would you improve with production data?**

I would confirm the physical shipment identifier, retain original promised dates and revision history,
reconcile all freight billing categories, and add carrier, lane, urgency, and milestone fields. That would
make route comparisons and exception monitoring more useful. This historical file cannot establish
current Cencora performance or precise shipping rates.

## Figures to Remember

| Measure | Result |
| --- | --- |
| Product lines / delivery groups | 10,324 / 7,030 |
| Delivery KPI denominator | 7,020 groups; ten conflicting schedules excluded |
| On time / late | 88.6% / 11.4% |
| Mean delay among late groups | 19.9 calendar days |
| Truck / air late rates | 20.6% / 8.5% |
| Numeric freight coverage | 88.2% |
| Upper 5% share of numeric freight subtotal | 28.0% |

Review the notebook code and practice explaining these decisions in your own words before listing
the project or discussing it in an interview.
