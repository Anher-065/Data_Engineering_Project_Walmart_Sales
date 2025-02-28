# **Data Engineering Project: Walmart Sales Dashboard**  

## **Project Overview**  
This project focuses on building a **data pipeline** to process and analyze Walmart sales data. It involves **extracting, loading, and transforming (ELT)** the data, which is then visualized using **Power BI**. The workflow is orchestrated using **Google Cloud Storage, BigQuery, Docker, and Cloud Run** to automate the ELT process.  

---

## **Problem Statement**  
Walmart requires a **sales analytics platform** to track revenue, customer trends, and product performance across different stores. The objective is to **ingest, process, and visualize** Walmart sales data efficiently to support business decision-making.  

---

## **Project Structure**  

📂 **Google Cloud Storage**: Stores the raw CSV sales data.  
📂 **BigQuery**: Serves as the data warehouse, where raw data is ingested and transformed.  
📂 **Cloud Run (Dockerized Python Script)**: Automates the ELT pipeline by fetching data from Cloud Storage and loading it into BigQuery.  
📂 **Power BI Dashboard**: Visualizes sales trends, revenue insights, and customer behavior.  

📌 **![image](https://github.com/user-attachments/assets/aaf97e28-ea11-4a7b-8e30-803857832ae5)
**  

---

## **Data Collection and Storage**  

### **Raw Data**  
The dataset consists of Walmart sales data stored in CSV format, containing columns like:  
- **Invoice ID**  
- **Branch & City**  
- **Customer Type & Gender**  
- **Product Line, Quantity, and Unit Price**  
- **Total Sales & Tax Amount**  
- **Date & Time of Purchase**  
- **Payment Method & Rating**  

![image](https://github.com/user-attachments/assets/db6b7e9d-2272-482e-ae00-8fd298595854)
  

### **Google Cloud Storage**  
The raw CSV file is uploaded to a **Google Cloud Storage** bucket for processing.  

📌 **[INSERT A SCREENSHOT OF GOOGLE CLOUD STORAGE BUCKET HERE]**  

---

## **Data Processing and Transformation**  

### **Cloud Run (Automated ELT Process)**  
A **Dockerized Python script** is deployed to **Google Cloud Run**, automating the ELT process:  
1. Extracts CSV data from **Google Cloud Storage**.  
2. Loads raw data into **BigQuery** without transformations.  
3. Transforms data in **BigQuery using SQL**, including:  
   - Cleaning null values.  
   - Converting date/time formats.  
   - Calculating **total revenue, tax, and sales metrics**.  

📌 **[INSERT A SCREENSHOT OF CLOUD RUN DEPLOYMENT HERE]**  

---

## **Data Analysis and Insights**  

### **BigQuery SQL Transformations**  
- **Total Revenue per Store**: Aggregates sales by branch.  
- **Top-Selling Products**: Identifies best-performing product lines.  
- **Customer Demographics**: Analyzes sales by gender and customer type.  
- **Peak Sales Hours**: Determines high-traffic shopping times.  

📌 **[INSERT A SCREENSHOT OF BIGQUERY TABLES AND SQL QUERY RESULTS HERE]**  

### **Power BI Dashboard**  
The processed data is visualized in **Power BI**, featuring:  
✅ **Total Revenue & Sales Trends**  
✅ **Top Products & Customer Segments**  
✅ **Geographical Sales Performance**  
✅ **Payment Methods & Customer Ratings**  

📌 **[INSERT A SCREENSHOT OF THE FINAL POWER BI DASHBOARD HERE]**  

---

## **Orchestration with Docker & Cloud Run**  

### **Docker & Cloud Run**  
- **Dockerfile**: Defines the Python environment for processing Walmart sales data.  
- **Cloud Run Deployment**: Automates ELT execution.  

📌 **[INSERT A SCREENSHOT OF DOCKERFILE CONTENT OR CLOUD RUN EXECUTION HERE]**  

---

## **Getting Started**  

### **Prerequisites**  
✅ **Google Cloud SDK & gcloud CLI**  
✅ **Docker & Docker Compose**  
✅ **Python 3.8+**  
✅ **Google Cloud Account (BigQuery & Cloud Storage)**  

### **Installation**  

#### 1️⃣ **Clone the Repository**  
```sh
git clone https://github.com/your-github-username/Walmart_Sales_Dashboard.git
cd Walmart_Sales_Dashboard
```

#### 2️⃣ **Build & Run Docker Containers**  
```sh
docker-compose up --build
```

#### 3️⃣ **Deploy to Google Cloud Run**  
```sh
gcloud builds submit --tag gcr.io/your-project-id/walmart-sales-pipeline
gcloud run deploy walmart-sales-service --image gcr.io/your-project-id/walmart-sales-pipeline --platform managed
```

#### 4️⃣ **Check BigQuery Data**  
- Open **BigQuery UI** and check if the tables have been updated.  

#### 5️⃣ **View the Power BI Dashboard**  
- Access the Power BI report embedded in `index.html`.  

---

## **Usage**  

🚀 **Automated Sales Data Processing**  
📊 **Real-Time Sales Dashboard in Power BI**  
📈 **Business Insights for Decision-Making**  

---
