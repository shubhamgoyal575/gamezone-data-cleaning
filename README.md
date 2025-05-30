# 🧹 Virtual Data GameZone - Data Cleaning Project

This project focuses on cleaning and documenting the data from the **Virtual Data GameZone** dataset, which includes:

- 📄 **Orders Sheet** with `21,864` records  
- 🌍 **Regions Sheet** with `192` records

The goal was to prepare the data for meaningful analysis by applying industry-standard data cleaning techniques and principles.

---

## 📁 Dataset Overview

### 1. Orders Sheet (`orders`)

| Column Name                | Description                         |
|---------------------------|-------------------------------------|
| `USER_ID`                 | Unique ID of the customer           |
| `ORDER_ID`                | Unique ID of the order              |
| `PURCHASE_TS`             | Timestamp of purchase               |
| `SHIP_TS`                 | Timestamp of shipping               |
| `PRODUCT_NAME`            | Name of the purchased product       |
| `PRODUCT_ID`              | Unique ID of the product            |
| `USD_PRICE`               | Price of the product in USD         |
| `PURCHASE_PLATFORM`       | Platform used for purchase          |
| `MARKETING_CHANNEL`       | Marketing channel used              |
| `ACCOUNT_CREATION_METHOD` | Account sign-up method              |
| `COUNTRY_CODE`            | Country code of the user            |

### 2. Regions Sheet (`regions`)

| Column Name     | Description                |
|----------------|----------------------------|
| `COUNTRY_CODE` | Country code reference     |
| `REGION`       | Associated region          |

---

## 🛠️ Cleaning Approach (C.L.E.A.N Framework)

We followed the **C.L.E.A.N** methodology for structured and thoughtful cleaning:

### ✅ C - Conceptualize the Data
- Understood what each row represents (one product order).
- Identified key metrics: `USD_PRICE`, `SHIP_TS - PURCHASE_TS` (delivery time).
- Identified key dimensions: `PRODUCT_NAME`, `COUNTRY_CODE`, `MARKETING_CHANNEL`, etc.

### ✅ L - Locate Solvable Issues
Addressed solvable issues such as:
- Inconsistent date formats
- Null values in categorical fields
- Duplicate `ORDER_ID`s
- Inconsistent `COUNTRY_CODE`s

### ✅ E - Evaluate Unsolvable Issues
- Missing values without a source of truth
- Preserved legitimate outliers after business context review
- Checked business logic (e.g., `SHIP_TS` should not precede `PURCHASE_TS`)

> 🧠 *Imputation is avoided unless there’s a reliable source or strong business logic.*

### ✅ A - Augment the Data
- Added derived columns:
  - `SHIP_TIME_DAYS` (Shipping duration)
  - `PURCHASE_YEAR`, `PURCHASE_MONTH`
- Merged region information using `COUNTRY_CODE`

### ✅ N - Note and Document
Created an **Issue Log Sheet** with columns:

| Table | Column | Issue | Row_Count | Row_PCT | Solvable? | Resolution |
|-------|--------|-------|-----------|---------|-----------|------------|

---

## 📄 Deliverables

- ✅ `orders_cleaned` – Cleaned & augmented orders data  
- ✅ `region_cleaned` – Cleaned regions reference data  
- ✅ `issue_log` – Full documentation of identified & resolved issues  

---

## 📌 Data Cleaning Philosophy

> **We are not aiming for perfect data — only data that is good enough to analyze, share, and iterate on.**

---

## 📊 Tools Used

- Microsoft Excel / Google Sheets  
- Formulas, filters, date-time functions  
- Manual inspection and logical validation

---

## 🤔 Final Thoughts

Before jumping into analysis, thoughtful data analysts ask:

> *What am I looking at? What story could this data help me tell?*

This project ensures that the dataset is ready to answer those questions effectively and reliably.

---

## 📬 Contact

For suggestions or feedback, feel free to open an [issue](../../issues) or connect via LinkedIn.
