# Technical Documentation: BI & Data Mining System "Comptoir"

## 1. Project Overview

This project involves the development of a complete **Business Intelligence (BI) ecosystem** and **Advanced Data Mining** implementation based on the "Comptoir" (Northwind) legacy system. The primary objective was to transition from an operational (OLTP) environment to an analytical (OLAP) system to optimize supply chain logistics and marketing strategies.

## 2. Technical Stack

* **Database Management:** SQL Server (Storage of the `comptoirDW` Data Warehouse).
* **Data Engineering:** Talend Open Studio (ETL development).
* **Predictive Analytics:** Python (Scientific libraries: `pandas`, `scikit-learn`, `mlxtend`, `networkx`).
* **Business Intelligence:** Power BI (Interactive reporting and KPI tracking).

## 3. Data Architecture & ETL

The system architecture is based on a **Star Schema** designed to minimize query complexity and maximize performance for high-volume analysis.

### Core Components:

* **Fact Table (`Fact_Ventes`):** Stores sales metrics, including calculated fields such as `Delai_Livraison` (Delivery Delay) and net revenue.
* **Dimensions:** Provides analytical context through `Dim_Client`, `Dim_Produit`, and a generated `Dim_Temps` (Time Dimension).
* **ETL Quality Gates:** * Filtering of "Time Travel" data (records where `ShippedDate < OrderDate`).
* Exclusion of orders with missing shipment dates to maintain statistical integrity.



## 4. Advanced Data Mining Implementation

The project integrates two specific machine learning models to extract non-obvious patterns from the data warehouse.

### A. Customer Segmentation (K-Means)

* **Methodology:** Application of the **Elbow Method** to determine the optimal cluster count ().
* **Segments Identified:**
* **Cluster 0 (High-Risk):** Clients experiencing an average delay of >22 days.
* **Cluster 1 (Standard):** Standard logistical performance (~10 days).
* **Cluster 2 (Performant):** Optimized logistics (~6 days).



### B. Market Basket Analysis (Apriori)

* **Constraint:** Redefinition of a "Basket" as (Client + Purchase Date) to capture true shopping sessions.
* **Key Discovery:** Strong association between **Sir Rodney's Scones** and **Maple Syrup** with a **Lift of 7.03**, indicating high cross-selling potential.

## 5. Key Business Insights

* **Financial Scope:** The system analyzes a total revenue of **1.27M€** across 91 clients and 69 cities.
* **Market Dominance:** Identification of the USA and Germany as primary revenue drivers.
* **Logistical Warning:** Significant goulots d'étranglement (bottlenecks) identified within the "High-Risk" segment requiring immediate supply chain intervention.

---

**Academic Framework:** Master in Data Analytics and AI 
