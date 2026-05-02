# 🌍 End-to-End Earthquake Data Engineering Project (Databricks)

## 📌 Overview

This project demonstrates a **complete Data Engineering pipeline** built on **Databricks Lakehouse** using real-time earthquake data from the USGS API.

The pipeline ingests raw data, processes it through **Bronze → Silver → Gold layers**, and serves insights via dashboards.

---

## 🧠 Architecture

```
USGS API → Bronze (Raw JSON) → Silver (Cleaned Data) → Gold (Aggregations) → Dashboard
```

### 🔁 Workflow

1. Extract earthquake data from API
2. Store raw data in Bronze layer
3. Transform and clean data in Silver layer using DLT
4. Build aggregated insights in Gold layer
5. Visualize using Databricks Dashboard

---

## ⚙️ Tech Stack

* 🧱 **Databricks Lakehouse**
* 🔄 **Delta Live Tables (DLT)**
* ⚡ **PySpark**
* 🗂️ **Delta Lake**
* 🌐 **USGS Earthquake API**
* 📊 **Databricks SQL Dashboard**
* 🚀 **Databricks Asset Bundles (DAB)**
* 🔁 **CI/CD (GitHub Actions - optional)**

---

## 📁 Project Structure

```
Databricks_DE_Project/
│
├── src/
│   ├── notebooks/
│   │   ├── Ingestion_Bronze.py
│   │
│   ├── dlt/
│   │   ├── Bronze_Silver_Earthquake.py
│   │
│   ├── dashboard/
│   │   ├── USGS Earthquakes Data.lvdash.json
│
├── resources/
│   ├── jobs.yml
│   ├── dashboards.yml
│
├── databricks.yml
├── README.md
```

---

## 🚀 Pipeline Details

### 🥉 Bronze Layer (Raw Ingestion)

* Fetch data from USGS API
* Store JSON files in volume storage
* Incremental ingestion

---

### 🥈 Silver Layer (DLT Pipeline)

* Parse nested JSON structure
* Flatten schema
* Apply data cleaning:

  * Remove invalid values
  * Convert timestamps
* Apply **SCD Type 1 (Upserts)**

---

### 🥇 Gold Layer (Analytics)

* Magnitude-based categorization
* Country-wise earthquake counts
* Aggregations for reporting

---

## 🧾 Job Orchestration

The pipeline is orchestrated using **Databricks Jobs**:

1. **Ingestion_Bronze** → Fetch API data
2. **DLT Pipeline** → Transform Bronze → Silver
3. **Dashboard Refresh** → Update visualizations

---

## 📺 Dashboard

The dashboard provides:

* 📊 Earthquake magnitude distribution
* 🌍 Country-wise earthquake analysis
* 📈 Trends and insights

---

## ⚙️ Deployment (Databricks Asset Bundle)

### Deploy:

```bash
databricks bundle deploy
```

### Run:

```bash
databricks bundle run E2E_EarthQuake_Project
```

---

## 🔐 Configuration

Set variables in `databricks.yml`:

```yaml
variables:
  catalog_name: EarthQuake_dev
  warehouse_id: <your_warehouse_id>
```

---

## ⚠️ Data Quality Checks

* Removed null/invalid magnitudes
* Handled missing location values
* Converted epoch timestamps

---

## 🚀 Future Improvements

* Real-time streaming ingestion
* Alert system for high magnitude earthquakes
* Machine Learning for prediction
* Geo-spatial visualization
* Multi-region analysis

---

## 👤 Author

**Fairooz Baig**
🔗 https://github.com/fairooz-baig

---

## ⭐ If you like this project

Give it a ⭐ on GitHub and feel free to contribute!
