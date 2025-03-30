# Redfin-BigData-Analytics-AWS-EMR

A Big-data project that processes over 5.7 million Redfin real estate records using AWS EMR and PySpark. This pipeline harnesses the power of distributed computing to perform complex transformations and analyses at scale, delivering actionable insights for the real estate market.

## Overview

This project demonstrates how to use AWS EMR with PySpark to process and analyze large-scale real estate data stored in Amazon S3. The final analysis was performed interactively via EMR Studio (Jupyter notebook).



## Architecture

<img width="1021" alt="Screenshot 2025-03-29 at 9 40 08 PM" src="https://github.com/user-attachments/assets/f21b58b7-bf39-4c24-ac48-1bbef2739c33" />

**Key Components:**

- **Amazon S3** – Stores raw and processed Redfin data  
- **AWS EMR** – Cluster used for distributed computing with Spark  
- **EMR Studio (Jupyter)** – Interactive PySpark development environment  
- **IAM & VPC** – Secure access and network isolation  
- **PySpark** – Data cleaning, transformation, and aggregation


## Repository Contents

```bash
.
├── README.md
├── notebooks/
│   └── redfin_emr_analysis.ipynb       # Jupyter notebook with PySpark code
└── docs/
    └── architecture_diagram.png        # System architecture diagram
```

---

## Getting Started

### 1. Launch EMR Cluster via AWS Console
- Use EMR with Spark application
- Configure networking with VPC and default subnet
- Enable EMR Studio and attach appropriate IAM role

### 2. Upload Redfin Data to S3 / Setup API integration
- Create an S3 bucket (or use existing one)
- Upload your raw dataset to a folder like: `s3://your-bucket/redfin/raw/`

### 3. Open EMR Studio (Jupyter)
- Open your linked EMR Studio workspace
- Upload and run `notebooks/redfin_emr_analysis.ipynb`

## Sample Insights

The project included in-depth, production-grade data analysis to extract meaningful trends and market intelligence from over 5.7 million real estate records. Key analyses include:

1. **Median Sale Price Trends by State**  
   Calculated average median sale prices per year for each state, highlighting temporal pricing trends and enabling year-over-year market comparisons.

2. **Top Cities by Price per Square Foot**  
   Utilized window functions to rank cities within each state based on average price per square foot (`median_ppsf`), identifying top-performing real estate markets.

3. **Days on Market Progression**  
   Investigated states where the average median days on market (`median_dom`) has increased over the past three years, signaling potential shifts in buyer behavior or market saturation.

4. **Categorization of Housing Supply Levels**  
   Created a categorical classification of housing supply levels (Low, Medium, High) based on the `months_of_supply` metric for the most recent reporting period. This helped assess inventory health across cities.

5. **Market Competitiveness via Over-Listing Analysis**  
   Determined cities with the highest frequency of months where more than 50% of homes sold above list price, offering insights into hyper-competitive housing environments.

These analyses showcase the application of distributed data processing to derive actionable insights, supporting strategic decisions in housing market evaluation, regional investment, and pricing strategy.
