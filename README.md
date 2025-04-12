

# 📊 Drug Deaths and Patient Survival Analysis

This project explores trends and patterns in drug-related deaths and patient survival data using PySpark and Python visualization libraries. It's designed as a revision-friendly resource for interviews, especially for data engineering and big data roles.

> 🧠 “Data will talk to you if you're willing to listen.”  
> — Jim Bergeson

Whether you're reviewing for an interview or brushing up your Spark skills, this hands-on project will walk you through installing the tools, processing data, and making sense of real-world healthcare patterns.

---

## 🚀 Get Started

To get up and running smoothly, follow the full guide below — from environment setup to running the analysis in Jupyter Notebook.

---

## 🛠 Installation & Setup

### ✅ Step 1: Install Python  
Download and install Python (3.8 or higher) from the official website:  
👉 [https://www.python.org](https://www.python.org)

---

### ✅ Step 2: Install Apache Spark  
Download Apache Spark (version 3.1.2 or higher) from:  
👉 [https://spark.apache.org/downloads.html](https://spark.apache.org/downloads.html)  
Follow the OS-specific instructions provided.

---

### ✅ Step 3: Install Required Python Libraries  

Run the following commands in your terminal:

```bash
pip install pyspark==3.1.2
pip install pandas==1.2.4
pip install numpy==1.20.3
pip install matplotlib==3.4.2
pip install seaborn==0.11.1
pip install jupyterlab  # optional, for notebook interface
```

---

### ✅ Step 4: Set Environment Variables for Spark

Update your shell config (`~/.bash_profile`, `~/.zshrc`, or `~/.bashrc`) with:

```bash
export SPARK_HOME=/path/to/spark
export PATH=$SPARK_HOME/bin:$PATH
```

📌 Replace `/path/to/spark` with the actual path where Spark is installed.  
After editing, reload your terminal config:

```bash
source ~/.zshrc  # or source ~/.bash_profile
```

---

### ✅ Step 5: Launch Jupyter Notebook

```bash
jupyter notebook
```

---

## 📂 Execution Guide

### 🔹 Prepare the Data

Make sure the following CSV files are available in your working directory:

- `drug_deaths.csv`
- `PatientSurvival.csv`

---

### 🔹 Initialize PySpark in Jupyter Notebook

In your notebook’s first cell, paste:

```python
import findspark
findspark.init()

from pyspark.sql import SparkSession

spark = SparkSession.builder \
    .appName("Drug Deaths and Patient Survival Analysis") \
    .config("spark.sql.debug.maxToStringFields", 1000) \
    .getOrCreate()
```

---

### 🔹 Run the Analysis

Paste the rest of your PySpark and Pandas-based logic into subsequent notebook cells. It’s best to break down the logic block-by-block (loading data, transformations, visualizations, etc.) for easier debugging and readability.

---

### 🔹 Customize Parameters (Optional)

Modify any filters, column selections, or analysis steps directly in the notebook depending on your exploration goals.

---

## 🧪 Troubleshooting Tips

| Problem | Solution |
|--------|----------|
| ❌ Spark session won't start | Double-check `SPARK_HOME` and `PATH` variables |
| ❌ Library not found | Use `pip install <package>` to install missing libraries |
| ❌ CSV file not found | Ensure files are in the same directory or provide absolute paths |
| ❌ Memory issues | Allocate more memory using the snippet below |
| ❌ Jupyter not detecting libraries | Restart the notebook and confirm environment |

### Example: Adjust Spark Memory

```python
spark = SparkSession.builder \
    .appName("DrugAnalysis") \
    .config("spark.executor.memory", "2g") \
    .config("spark.driver.memory", "2g") \
    .getOrCreate()
```

---

## ✨ Final Thoughts

This project is part of a broader collection of Python and big data notes for interview revision. While these steps give a great overview, **the best way to retain knowledge is through hands-on coding.**

> 💬 “Tell me and I forget, teach me and I may remember, involve me and I learn.”  
> — Benjamin Franklin

---

## 📁 License

This project is for educational use only.
