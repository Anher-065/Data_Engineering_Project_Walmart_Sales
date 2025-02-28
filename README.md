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

![image](https://github.com/user-attachments/assets/0fb4ee23-d1b1-4c53-8222-54056507e8dc)
 

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

![image](https://github.com/user-attachments/assets/d31bbf2c-2869-48b5-8ca8-686607d4d006)
 

---

## **Data Analysis and Insights**  

### **BigQuery SQL Transformations**  
- The primary transformation performed is on date formatting to ensure consistency across different formats. The transformation logic:

Converts Date from mixed formats (%m/%d/%Y and %d/%m/%Y) into a unified format using COALESCE(SAFE.PARSE_DATE(...)).
Extracts Year, Month, and Day from the formatted date for time-based analysis.
Potential Future Transformations
Although the current transformation mainly handles date standardization, additional queries can be created to extract more insights:

Total Sales per Branch: Aggregates revenue per store location.
Best-Selling Product Lines: Identifies top-performing product categories.
Customer Segmentation: Analyzes spending patterns based on gender and customer type.
Peak Sales Periods: Determines high-traffic days/times for strategic decision-making.  

![image](https://github.com/user-attachments/assets/6ace1958-16c1-4880-b688-40af57c3bed1)
  

### **Power BI Dashboard**  
This project visualizes Walmart sales data using Power BI, providing insights into sales trends, customer behavior, and payment preferences. Key features include:

📈 Total Revenue & Sales Trends: A line chart tracks sales over time.
🏆 Top 3 Selling Product Lines: The most popular categories by gender.
💳 Payment Methods Breakdown: Pie chart shows the proportion of cash, e-wallet, and credit card transactions.
🏙️ Sales by City: Pie chart displays total revenue distribution across Mandalay, Naypyitaw, and Yangon.
🛍️ Branch & Customer Type: Bar chart shows total sales categorized by branch and customer type (Member vs. Normal).
💰 Gross Income Analysis: Displays total earnings from sales.

![image](https://github.com/user-attachments/assets/4ec03bcf-8d2f-40c8-ace2-499543a301d0)


---

## **Orchestration with Docker & Cloud Run**  

### **Docker & Cloud Run**  
- **Dockerfile**: Defines the Python environment for processing Walmart sales data.  
- **Cloud Run Deployment**: Automates ELT execution.  

![image](https://github.com/user-attachments/assets/19374117-b9e0-458b-978e-37783ab814cf)


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
