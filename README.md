# Gym Membership Churn & Retention Dashboard (Power BI)

An interactive Power BI dashboard that analyzes customer churn and retention for a gym membership business. 
It identifies which members are leaving, why they leave, how much revenue is at risk, and which active members should be contacted first.

## Business Problem

Gyms lose a large share of members each year, and acquiring a new member costs more than keeping an existing one. This project answers:

- What is the overall churn and retention rate?
- Which membership types, payment plans and customer groups churn the most?
- Does visit frequency or satisfaction predict churn?
- Why are members leaving?
- Which active members are at risk and should be contacted now?

- ## Dataset

- **Records:** 20,233 members
- **Columns:** 21
- **Period:** Jan 2022 to Oct 2026
- **Currency:** INR

| Group | Columns |
|---|---|
| Member | MemberID, Gender, Age, City, JoinDate, TenureMonths |
| Membership | MembershipType, PaymentPlan, MonthlyFee, TotalPaid |
| Services | PersonalTrainer, GroupClasses |
| Behavior | AvgVisitsPerWeek, LastVisitDaysAgo, DistanceFromGymKm |
| Experience | SatisfactionScore, Complaints, ReferredByFriend |
| Target | Churn, ChurnDate, ChurnReason |


## Tools Used

- **Power BI Desktop:** data modeling and visualization
- **Power Query:** data cleaning and column creation
- **DAX:** measures and calculated columns

- ## Data Model

- A `Members` fact table connected to a `Date` calendar table.
- Active relationship: `Date[Date]` → `Members[JoinDate]`.
- Inactive relationship: `Date[Date]` → `Members[ChurnDate]`, used in measures with `USERELATIONSHIP`.

- ## Key KPIs

| KPI | Description |
|---|---|
| Total Members | Count of all members |
| Churn Rate | Churned members ÷ total members |
| Retention Rate | Not churned members  ÷ Total members |
| Monthly Revenue Lost | Monthly fees of churned members |
| Avg Satisfaction | Mean satisfaction score (1–5) |
| At-Risk Members | Active members with no visit in 14+ days |

## Dasboard
<a href="https://github.com/Jaseel7012/Retention-and-Churn-Analysis-Dashboard/blob/main/Screenshot%20(91).png">Dashboard</a>
## Key Insights
**20K members**, **27.8% churn**, **72.2% retention**, about **6M monthly revenue lost**
- Average satisfaction is **3.77 / 5**
- **121 active members** are at risk (no visit in 14+ days)
- Joins spike every **January** and **September**, but monthly churn keeps rising, so net growth is slowing
- Top churn reasons: **Lost Motivation** and **Lack of Time** (about 43% of churn), then **Too Expensive**
- Members with **0-1 visits per week** churn the most (~71%), against ~41% for 1-3 visits and almost none at 3-5 visits
## Recommendations
- Run 30/60/90-day onboarding and motivation programs for new members
- Offer flexible, short workouts and easy booking for members short on time
- Set up inactivity alerts and contact members after 14 days without a visit
- Push January and September joiners toward quarterly or yearly plans
- Offer freeze or lower-cost plans instead of blanket discounts
