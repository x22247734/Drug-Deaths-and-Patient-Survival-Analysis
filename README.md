Project Title: Drug Deaths and Patient Survival Analysis
1. Installation Requirements
To execute the code, the following software, libraries, and dependencies are required:

Python: Version 3.8 or higher
Apache Spark: Version 3.1.2 or higher
PySpark: Version 3.1.2 or higher
Pandas: Version 1.2.4 or higher
NumPy: Version 1.20.3 or higher
Matplotlib: Version 3.4.2 or higher
Seaborn: Version 0.11.1 or higher
Jupyter Notebook: Version 6.4.0 or higher
2. Setup Instructions
Step 1: Install Python
Ensure that Python is installed on your system. You can download and install it from the official Python website.

Step 2: Install Apache Spark
Download and install Apache Spark from the official Spark website. Follow the instructions for your operating system.

Step 3: Install Required Python Libraries
You can install the necessary Python libraries using pip. Open your terminal and run the following commands:

bash
Copy code
pip install pyspark==3.1.2
pip install pandas==1.2.4
pip install numpy==1.20.3
pip install matplotlib==3.4.2
pip install seaborn==0.11.1
pip install jupyterlab  # optional, for Jupyter Notebook
Step 4: Set Up Your Environment
Ensure that Apache Spark is correctly set up by configuring the environment variables. Add the following lines to your ~/.bash_profile or ~/.zshrc file (depending on your shell):

bash
Copy code
export SPARK_HOME=/path/to/spark
export PATH=$SPARK_HOME/bin:$PATH
Replace /path/to/spark with the actual path where Spark is installed.

Step 5: Start a Jupyter Notebook
We will use Jupyter Notebook to set up PySpark and execute the code. Start it by running:

bash
Copy code
jupyter notebook
3. Execution Guide
Step 1: Prepare Your Data
Ensure that the following CSV files are available in your working directory:

drug_deaths.csv
PatientSurvival.csv
Step 2: Setup PySpark in Jupyter Notebook
Open a new Jupyter Notebook and set up PySpark by adding the following lines to the first cell:

python
Copy code
import findspark
findspark.init()

from pyspark.sql import SparkSession

spark = SparkSession.builder \
    .appName("Drug Deaths and Patient Survival Analysis") \
    .config("spark.sql.debug.maxToStringFields", 1000) \
    .getOrCreate()
Step 3: Run the Code
You can copy and paste the provided Python code into the cells of your Jupyter Notebook. Ensure each logical block of code is placed in separate cells to make debugging easier.

Step 4: Modify Parameters (if needed)
The script includes various parameters and columns to select and analyze. You can modify these directly in the Jupyter Notebook cells as needed.

4. Troubleshooting Tips
Common Issues and Solutions
Spark Session Not Starting

Ensure that the SPARK_HOME environment variable is correctly set.
Check that the path to Spark binaries is correctly added to your PATH.
Missing Library Errors

Ensure all required libraries are installed using pip.
Verify that the Python environment being used to run the script has access to all installed libraries.
CSV File Not Found

Ensure that the CSV files (drug_deaths.csv and PatientSurvival.csv) are in the correct directory.
Verify the file paths in the script.
Memory Issues

If running into memory errors, try increasing the memory allocated to Spark. This can be done by adding the following configuration to the Spark session initialization:
python
Copy code
spark = SparkSession.builder \
    .appName("YourAppName") \
    .config("spark.executor.memory", "2g") \
    .config("spark.driver.memory", "2g") \
    .getOrCreate()
Jupyter Notebook Issues

Ensure the notebook is running in the same Python environment where dependencies are installed.
Restart the Jupyter Notebook server if necessary.
