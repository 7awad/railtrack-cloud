
# 🚆 RailTrack Cloud: Data Pipeline & Dashboard using Microsoft Azure  

### 🎯 Project Purpose  
RailTrack Cloud is a student-level data-engineering project that demonstrates how to build an **end-to-end cloud data pipeline** using **Microsoft Azure**.  
It simulates railcar operations data, processes it through Azure services, and visualizes performance insights in **Power BI**.  

This project mirrors real-world enterprise workflows, showcasing skills in **data ingestion, transformation, storage, and visualization**.

---

### 🧩 Architecture Overview  

```text
[Jupyter Notebook: Data Simulation (.csv)]
        ↓
[Azure Blob Storage → railtrack-raw container]
        ↓
[Azure Data Factory → Copy Pipeline (CSV → SQL Database)]
        ↓
[Azure SQL Database → railcar_data table]
        ↓
[Power BI Dashboard → KPI & Visual Insights]
````

---

### ⚙️ Tech Stack

| Category            | Tools & Services         |
| ------------------- | ------------------------ |
| **Data Simulation** | Python (pandas, NumPy)   |
| **Cloud Storage**   | Azure Blob Storage       |
| **ETL Pipeline**    | Azure Data Factory (ADF) |
| **Database**        | Azure SQL Database       |
| **Visualization**   | Power BI Desktop         |
| **Languages**       | Python, SQL, DAX         |

---

### 🧠 Project Stages

| Stage                       | Tool                         | Description                                                                                                                  |
| --------------------------- | ---------------------------- | ---------------------------------------------------------------------------------------------------------------------------- |
| **1️⃣ Data Simulation**     | **Jupyter Notebook**         | Generated synthetic daily railcar data (distance km, fuel used, temperature °C, maintenance flag) for 15 railcars × 60 days. |
| **2️⃣ Data Storage**        | **Azure Blob Storage**       | Uploaded `railcar_data.csv` into the `railtrack-raw` container for centralized data storage.                                 |
| **3️⃣ Data Pipeline**       | **Azure Data Factory (ADF)** | Created a Copy Data pipeline that moves CSV data from Blob Storage → Azure SQL Database.                                     |
| **4️⃣ Data Transformation** | **Azure SQL Database**       | Verified schema and cleaned data (`date`, `railcar_id`, `distance_km`, `fuel_used_l`, `temperature_c`, `maintenance_flag`).  |
| **5️⃣ Visualization**       | **Power BI**                 | Built interactive dashboard to monitor fleet performance and maintenance trends.                                             |

---

### 📊 Power BI Dashboard

**Key Visuals:**

* **Sum of Distance by Year** (Trend Line)
* **Sum of Fuel Used by Year** (Bar Chart)
* **Maintenance Distribution** (Donut Chart)
* **KPI Cards:** Total Railcars | Average Temperature | Average Fuel Efficiency | Maintenance Rate (%)

**KPIs Displayed:**

| Metric                     | Formula                                        | Value (Example) |
| -------------------------- | ---------------------------------------------- | --------------- |
| Total Railcars             | COUNT(railcar_id)                              | 15              |
| Avg Operating Temp (°C)    | AVERAGE(temperature_c)                         | 27.75           |
| Avg Fuel Efficiency (km/L) | SUM(distance_km) / SUM(fuel_used_l)            | 1.43            |
| Maintenance Rate (%)       | (COUNT(maintenance_flag = 1) / COUNT(*)) × 100 | 3 %             |

📸 **Screenshot:** `powerbi/dashboard_screenshot.png`
📁 **PBIX File:** `powerbi/dashboard.pbix`

---

### 🧱 Repository Structure

```text
RailTrack-Cloud/
│
├── notebooks/
│   └── RailTrack_Stage1_DataSimulation.ipynb      ← Python simulation code
│
├── data/
│   └── railcar_data.csv                           ← Generated dataset
│
├── azure/
│   ├── blob_container.png                         ← Uploaded CSV in Blob Storage
│   ├── adf_pipeline.png                           ← ADF pipeline view
│   ├── adf_run_success.png                        ← Pipeline run success log
│   ├── sql_table.png                              ← Preview of SQL table rows
│   └── sql_schema.png                             ← Schema visual
│
├── powerbi/
│   ├── dashboard.pbix                             ← Power BI project file
│   └── dashboard_screenshot.png                   ← Final dashboard image
│
└── README.md
```

---

### 📈 Results & Insights

* Simulated > 900 records of daily railcar data across 15 vehicles.
* Automated data flow from Blob Storage → SQL Database via ADF.
* Computed average operating temperature (27.75 °C) and fuel efficiency (1.43 km/L).
* Visualized 3 % maintenance rate and fleet distance > 120 000 km.

---

### 📚 Learning Outcomes

* Hands-on experience with Azure Data Factory pipelines and Linked Services.
* Practical use of Azure SQL Database for data storage and querying.
* Integration of Power BI with Azure SQL for real-time dashboards.
* Strong understanding of ETL concepts and data engineering workflow.

---

### 👤 Author

**Jawad Almatar**
📧 [almatm2@mcmaster.ca](mailto:almatm2@mcmaster.ca)
🔗 [LinkedIn](https://linkedin.com/in/jawadalmatar) | [GitHub](https://github.com/7awad)

---

`````

