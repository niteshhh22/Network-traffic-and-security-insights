# NETWORK TRAFFIC & SECURITY INSIGHTS DASHBOARD

📌 Project Overview

This project is a beginner-level Data Analysis project made using Python.
The main goal of this project is to analyze network traffic logs and find security-related insights like:

* Suspicious IP addresses
* Blocked requests
* Threat labels
* Protocol usage
* Network activity patterns

This project helps in understanding how network security data can be analyzed using Python.

# 🛠️ Technologies Used
* Python
* Pandas
* Matplotlib
* Seaborn
* Jupyter Notebook

📂 Dataset Used

The dataset used in this project is:
`logs.csv`

The dataset contains information related to:
* Source IP
* Destination IP
* Protocol
* Action (allowed/blocked)
* Threat Label
* Network Traffic Details

📚 Python Libraries Used

import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns


### 1. Pandas
Used for:
* Reading dataset
* Cleaning data
* Data analysis

### 2. Matplotlib
Used for:
* Creating charts and graphs

### 3. Seaborn
Used for:
* Better visualization and attractive graphs


⚙️ Project Steps

## Step 1: Import Libraries
First, we imported all required Python libraries.

import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

## Step 2: Load Dataset
The CSV file is loaded using Pandas.
rf = pd.read_csv("logs.csv")

## Step 3: Data Cleaning
Data cleaning is very important before analysis.
In this project:
* Duplicate values were removed
* Missing values were removed

rf = rf.drop_duplicates()
rf = rf.dropna()

## Step 4: Dataset Information
Basic dataset information was checked.
rf.info()
rf.shape
rf.head()

This helps to understand:
* Number of rows and columns
* Data types
* Sample records

## Step 5: Threat Analysis
Threat labels were analyzed to identify dangerous traffic.
rf["threat_label"].value_counts()

## Step 6: Blocked Requests Analysis
Blocked requests were counted.

blocked_requests = rf[rf["action"] == "blocked"]
This helps in identifying suspicious activities.

## Step 7: Suspicious IP Detection
A function was created to find suspicious IP addresses.

def find_suspicious_ips(data):
    blocked = data[data["action"] == "blocked"]
    suspicious = blocked["source_ip"].value_counts()
    return suspicious

This function checks:
* Which IPs are blocked most frequently
* Which IPs may be suspicious

## Step 8: Protocol Analysis
Protocols used in network traffic were analyzed.

def show_protocols(data):
    protocols = data["protocol"].value_counts()
    return protocols

Common protocols:
* TCP
* UDP
* ICMP
  

📊 Visualizations Used
Different visualizations were created to understand data better.

Examples:
* Bar Charts
* Count Plots
* Threat Distribution Graphs
* Protocol Usage Graphs

Visualization helps to:
* Understand patterns easily
* Detect suspicious behavior
* Improve analysis readability


🔍 Key Insights From Project
Some important findings from this project:

* Certain IP addresses generated many blocked requests.
* Some threat labels appeared more frequently.
* Specific protocols were used more than others.
* Blocked traffic can indicate suspicious network activity.
  

🚀 How to Run This Project

## Step 1
Install Python.

## Step 2
Install required libraries.

```bash
pip install pandas matplotlib seaborn
```

## Step 3

Open Jupyter Notebook.

```bash
jupyter notebook
```

## Step 4

Run the notebook file:

`NETWORK TRAFFIC & SECURITY INSIGHTS DASHBOARD.ipynb`


💡 Future Improvements
This project can be improved further by:

* Using Streamlit for dashboard creation
* Adding real-time data monitoring
* Creating interactive charts
* Adding machine learning for threat prediction
* Using advanced data cleaning techniques


📈 Use of Streamlit in This Project

Streamlit can be used to convert this notebook into a web dashboard.

With Streamlit, users can:
* View graphs interactively
* Upload datasets
* Filter data easily
* Create a professional dashboard

Example command:

```bash
streamlit run app.py
```

---

🎯 Learning Outcome

By completing this project, I learned:
* Data Cleaning
* Data Analysis
* Data Visualization
* Python Basics
* Network Security Analysis
* Working with CSV datasets


👨‍💻 Conclusion
This beginner-level project demonstrates how Python can be used for analyzing network traffic and security data.

The project helps in understanding:
* Suspicious activities
* Threat patterns
* Network protocols
* Security monitoring basics

