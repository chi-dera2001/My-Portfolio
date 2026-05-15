# Data Cleaning & Transformation Log
**Project:** Hospital Revenue & Patient Analysis
**Tool(s) Used:** SQL Server, Excel (Power Query), Power BI
**Dataset Source:** Kaggle (Healthcare Operations Dataset)

---

## 1. Initial Data Assessment
* **Total Records:** 50,000 rows.
* **Missing Values:** Identified nulls in `Discharge_Date` and `Insurance_Provider`.
* **Data Types:** `Billing_Amount` detected as 'Text'; `Admission_Date` had inconsistent formatting.

## 2. Cleaning Steps (The "Process")

| Issue Identified | Action Taken | Tool Used |
| :--- | :--- | :--- |
| **Duplicates** | Removed 142 redundant patient records using `ROW_NUMBER()`. | SQL |
| **Missing Revenue** | Replaced null `Billing_Amount` with the median for the specific medical condition. | Excel |
| **Outliers** | Deleted records where `Age` was negative or greater than 115. | SQL |
| **Standardization** | Converted all 'Medical Condition' strings to Title Case for consistency. | Power Query |

## 3. Data Transformation for Power BI
* **Age Bucketing:** Grouped ages into `0-18 (Minor)`, `19-64 (Adult)`, and `65+ (Senior)`.
* **Calculated Metrics:** Created `Length_of_Stay` (Discharge - Admission).
* **Schema Design:** Developed a Star Schema connecting `Fact_Admissions` to `Dim_Patients`.

## 4. Final Validation
- [x] Primary Keys verified as unique.
- [x] No nulls in critical calculation columns.
- [x] Relationships in Power BI established (1:Many).
