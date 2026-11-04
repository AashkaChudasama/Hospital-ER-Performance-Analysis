# Hospital-ER-Performance-Analysis
An interactive **Power BI** project analyzing emergency room (ER) operations using historical patient-visit data. The dashboard helps hospital stakeholders monitor patient volume, waiting times, satisfaction, admission status and department referrals to support operational planning and resource allocation.

## Project Objective

The goal is to provide a clear, data-driven view of ER performance and help answer questions such as:

- How does patient volume change over time?
- What are the average wait times, and when are patient arrivals busiest?
- What proportion of patients are seen within the 30-minute target?
- How are visits distributed across admission status and patient demographics?
- Which departments receive the most referrals?
- How do satisfaction scores vary across the reporting period?

## Dataset

The project uses a historical emergency room dataset covering **1 April 2023 to 30 October 2024**.

| Attribute | Details |
|---|---|
| Records | 9,216 ER visits |
| Raw dataset | 12 columns |
| Prepared Power BI source | 14 columns |
| Reporting period | April 2023 – October 2024 |
| Main data areas | Patient demographics, visit details, wait time, admission status, department referral and satisfaction score |

Each row represents an ER visit. The report records 9,216 unique Patient IDs in the supplied dataset.

## Tools & Technologies

- **Power BI** – Data modelling, DAX measures and interactive dashboard development
- **Power Query** – Data preparation, transformation and calculated columns
- **CSV** – Source data format

## Project Workflow

### 1. Data Preparation – Power Query

The dataset was prepared in Power BI before building the report.

Key steps:
- Imported the ER dataset and reviewed its structure and data types.
- Standardized data types for patient identifiers, demographics, visit details and performance fields.
- Checked duplicate rows and Patient IDs; no duplicates were found.
- Replaced blank department referral values with `None` to represent visits without a referral.
- Retained missing satisfaction scores as blank rather than imputing them.
- Validated age, wait time, satisfaction score and admission date ranges.
- Created reporting fields including Patient Date, Patient Admission Time, Admission Hour, Full Gender, Admission Status, Age Group, Waittime Status and Waittime Interval.
- Created a Calendar Table to support date filters and monthly trend analysis.

### 2. KPI Development – DAX

Measures were developed to track the core operational metrics:

- **No. of Patients:** Distinct count of Patient IDs.
- **Average Wait Time:** Average patient wait time, displayed in minutes.
- **Patient Satisfaction Score:** Average of recorded satisfaction scores.
- **No. of Patients Referred:** Count of visits with a department referral.
- **Seen Within 30 Minutes:** Count or percentage of visits with a wait time of 30 minutes or less.
- **Admission Status:** Admitted versus Not Admitted patient counts and percentages.

### 3. Dashboard Development – Power BI

The interactive report contains four pages, accessible through the navigation menu.

| Dashboard page | Purpose |
|---|---|
| Monthly View | Tracks KPIs and daily trends for a selected month, with admission status, wait-time target, demographics, referrals and day/hour patterns |
| Consolidated View | Shows the same operational metrics over a selected date range, with monthly trends |
| Patient Details | Provides a row-level table for detailed investigation of visit records |
| Key Takeaways | Summarizes descriptive findings, operational patterns and recommendations |

## Dashboard Preview

Add the dashboard screenshots to the repository's `images/` folder and use the filenames below, or update the paths to match your files.

**Monthly View**

![Hospital ER Performance Dashboard – Monthly View](images/monthly-view.png)

**Consolidated View**

![Hospital ER Performance Dashboard – Consolidated View](images/consolidated-view.png)

**Key Takeaways**

![Hospital ER Performance Dashboard – Key Takeaways](images/key-takeaways.png)

## Key Findings

- **Patient volume was relatively steady:** The ER recorded **9,216 visits** across 19 months, averaging approximately 485 visits per month. The report found no statistically significant monthly variation in patient volume.
- **The 30-minute wait target was frequently missed:** Average wait time was **35.3 minutes**. Only **40.7% (3,749 visits)** were within 30 minutes, while 59.3% exceeded the target.
- **Satisfaction data was limited:** The average recorded satisfaction score was **4.99**, but only 2,517 visits (27.3%) had a recorded score. This result should be interpreted with caution.
- **Referrals were concentrated in two departments:** Of 3,816 referred visits, General Practice received 1,840 and Orthopedics received 995. Together, they accounted for 74.3% of referrals.
- **Admissions were evenly split:** 4,612 visits (50.0%) were admitted and 4,604 (50.0%) were not admitted.
- **Arrival-time patterns showed some variation:** The report found significantly different average wait times by arrival period, with the longest averages in the 22:00–23:59 and 02:00–03:59 periods.

## Business Recommendations

- Review triage and patient-flow processes to improve the proportion of patients seen within 30 minutes.
- Assess staffing coverage during late-evening and overnight periods with longer average waits.
- Improve satisfaction data collection so that feedback is available for a larger share of visits.
- Review referral capacity and hand-off processes in General Practice and Orthopedics.
- Plan inpatient bed and admission capacity around the steady flow of admitted ER patients.
- Investigate months with comparatively longer waits and lower within-target performance.

## Data Quality & Limitations

- The dataset is a historical extract, not a live hospital feed.
- Satisfaction scores are missing for **6,699 visits (72.7%)**. The average satisfaction score is calculated from the 2,517 recorded responses only; missing values were not imputed.
- Blank department referral values were represented as `None`, indicating no referral.
- The report notes that the dataset's near-uniform distributions may indicate simulated or sampled data. Findings should be validated against live operational data before making staffing or care decisions.
- The dashboard is an operational reporting and descriptive analysis tool; it does not establish causes of delays or assess clinical outcomes.

## How to Use

1. Clone or download the repository.
2. Open `dashboard/Hospital Emergency Room.pbix` in Power BI Desktop.
3. If prompted, update the source connection to your authorized local dataset.
4. Refresh the report.
5. Use the Month & Year slicer or date-range filter and the left-side navigation to explore the dashboard pages.

## Project Deliverables

- Raw ER dataset (retain privately or share only in an appropriately anonymized form)
- Power BI dashboard (`.pbix`)
- Business Requirements Document
- Project report
- Dashboard screenshots suitable for public display

---

**Project:** Hospital ER Performance Analysis  
**Domain:** Healthcare Analytics  
**Focus:** Power BI | Power Query | DAX | KPI Reporting | Operational Performance Analysis
