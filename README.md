Objective

The goal of this task is to use **SQL within Python** to extract basic population summaries from an SQLite database created using district-level population data of India. This task simulates how a data analyst pulls and visualizes aggregated information from raw datasets.

---

## 📊 Dataset

The dataset contains the following fields:

- `District`: Name of the district
- `State`: Name of the state
- `Area_km2`: Area of the district in square kilometers (with commas)
- `Population`: Population of the district (with commas)

> Dataset source: Provided Excel file `Dataset2.xls`

---

## 🛠 Tools Used

- **Python** (pandas, sqlite3, matplotlib)
- **SQLite** (built-in with Python)
- **Jupyter Notebook / Python Script**
- **Excel (.xls)** as the original data format

---

## 🔍 Steps Performed

1. **Loaded the Excel file** into a pandas DataFrame.
2. **Cleaned the data**: Removed commas from `Population` and `Area_km2` and converted them to integers.
3. **Created a SQLite database** and inserted the cleaned data.
4. **Ran SQL queries** to:
   - Calculate total population per state.
   - Sort states by total population.
5. **Visualized** the top 10 most populous states using a bar chart.

---

## 🧾 SQL Query Used

```sql
SELECT State, 
       SUM(Population) AS total_population 
FROM population 
GROUP BY State 
ORDER BY total_population DESC
