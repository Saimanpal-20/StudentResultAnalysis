# Student Score Analysis & Exploratory Data Analysis

A Python-based **Exploratory Data Analysis (EDA)** project that analyzes
student performance data and explores relationships between academic
scores and selected demographic/family-related factors.

The analysis is implemented in a Jupyter Notebook using **Pandas, NumPy,
Matplotlib, and Seaborn**.

------------------------------------------------------------------------

## 📌 Project Overview

This project focuses on understanding patterns in student academic
performance through data cleaning, descriptive statistics,
visualization, and group-based analysis.

The notebook analyzes:

-   Student gender distribution
-   Weekly study-hour data
-   Parent education and student scores
-   Parent marital status and student scores
-   Distribution of Math, Reading, and Writing scores
-   Distribution of ethnic groups

The project demonstrates a practical **Data Analytics / EDA workflow in
Python**.

------------------------------------------------------------------------

## 🎯 Objectives

The main objectives of this project are to:

1.  Load and inspect the student score dataset.
2.  Perform basic data cleaning.
3.  Identify missing values and understand the dataset structure.
4.  Analyze the distribution of students by gender.
5.  Examine the relationship between parent education and student
    scores.
6.  Examine the relationship between parent marital status and student
    scores.
7.  Analyze the distribution of academic scores.
8.  Visualize the distribution of ethnic groups.
9.  Extract meaningful observations from the data.

------------------------------------------------------------------------

## 🛠️ Technologies & Libraries

  Technology         Purpose
  ------------------ --------------------------------
  Python             Programming language
  Jupyter Notebook   Analysis environment
  Pandas             Data manipulation and analysis
  NumPy              Numerical operations
  Matplotlib         Data visualization
  Seaborn            Statistical visualization

### Python Libraries

``` python
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
```

------------------------------------------------------------------------

## 📂 Project Structure

``` text
Student-Score-Analysis/
│
├── Student_score.csv
├── Untitled.ipynb
└── README.md
```

> Rename `Untitled.ipynb` to something more descriptive, such as
> `Student_Score_Analysis.ipynb`, before publishing the project.

------------------------------------------------------------------------

## 📊 Dataset

The notebook uses:

``` text
Student_score.csv
```

The analysis works with fields including:

-   `Gender`
-   `WklyStudyHours`
-   `ParentEduc`
-   `ParentMaritalStatus`
-   `EthnicGroup`
-   `MathScore`
-   `ReadingScore`
-   `WritingScore`

------------------------------------------------------------------------

## 🔄 Analysis Workflow

### 1. Import Required Libraries

The project starts by importing the required Python libraries for data
analysis and visualization.

``` python
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
```

### 2. Load the Dataset

``` python
df = pd.read_csv("Student_score.csv")
print(df.head())
```

### 3. Understand the Dataset

The notebook uses:

``` python
df.describe()
```

and

``` python
df.info()
```

to inspect descriptive statistics, data types, and dataset structure.

### 4. Check Missing Values

``` python
df.isnull().sum()
```

This is used to identify missing values in the dataset.

### 5. Data Cleaning

An unnecessary `Unnamed: 0` column is removed:

``` python
df = df.drop("Unnamed: 0", axis=1)
```

The weekly study-hours value `05-Oct` is also standardized:

``` python
df["WklyStudyHours"] = df["WklyStudyHours"].str.replace("05-Oct", "5-10")
```

------------------------------------------------------------------------

## 📈 Exploratory Data Analysis

### Gender Distribution

A count plot is used to examine the number of students by gender.

``` python
sns.countplot(data=df, x="Gender")
```

The notebook observes that the number of female students is higher than
the number of male students in the analyzed data.

------------------------------------------------------------------------

### Parent Education vs Student Scores

The project groups students according to `ParentEduc` and calculates the
mean:

-   Math Score
-   Reading Score
-   Writing Score

``` python
gb = df.groupby("ParentEduc").agg({
    "MathScore": "mean",
    "ReadingScore": "mean",
    "WritingScore": "mean"
})
```

A heatmap is then used to visualize the relationship between parent
education categories and average student scores.

The notebook's interpretation indicates an association between parent
education and student academic performance.

> **Note:** This analysis shows patterns/associations in the dataset and
> should not by itself be interpreted as proof of causation.

------------------------------------------------------------------------

### Parent Marital Status vs Student Scores

The notebook also calculates average scores by `ParentMaritalStatus`.

``` python
gb1 = df.groupby("ParentMaritalStatus").agg({
    "MathScore": "mean",
    "ReadingScore": "mean",
    "WritingScore": "mean"
})
```

A heatmap is used to compare the resulting averages.

The notebook's conclusion is that parent marital status shows no or
negligible difference in the analyzed student scores.

------------------------------------------------------------------------

### Score Distribution

Box plots are created separately for:

-   Math Score
-   Reading Score
-   Writing Score

Example:

``` python
sns.boxplot(data=df, x="MathScore")
plt.show()
```

These visualizations help inspect the distribution and spread of student
scores.

------------------------------------------------------------------------

### Ethnic Group Distribution

The notebook identifies the available ethnic groups and visualizes their
distribution using a pie chart.

Groups analyzed:

``` text
Group A
Group B
Group C
Group D
Group E
```

The visualization provides a percentage-based view of the representation
of each group in the dataset.

------------------------------------------------------------------------

## 🔍 Key Observations

Based on the analysis performed in the notebook:

-   The dataset contains more female students than male students.
-   Parent education shows an association with average student academic
    scores.
-   Parent marital status shows no/negligible difference in the analyzed
    student scores.
-   Math, Reading, and Writing scores were examined using box plots to
    understand their distributions.
-   The dataset contains five identified ethnic groups: A, B, C, D, and
    E.
-   The `Unnamed: 0` column was removed as part of data cleaning.
-   The weekly study-hours value `05-Oct` was standardized to `5-10`.

------------------------------------------------------------------------

## 🚀 How to Run the Project

### Step 1: Clone the Repository

``` bash
git clone <your-repository-url>
```

### Step 2: Open the Project

``` bash
cd Student-Score-Analysis
```

### Step 3: Install Required Libraries

``` bash
pip install numpy pandas matplotlib seaborn jupyter
```

### Step 4: Start Jupyter Notebook

``` bash
jupyter notebook
```

### Step 5: Open the Notebook

Open:

``` text
Student_Score_Analysis.ipynb
```

Make sure `Student_score.csv` is located in the same project directory
as the notebook.

### Step 6: Run the Cells

Run the notebook cells from top to bottom to reproduce the analysis and
visualizations.

------------------------------------------------------------------------

## 💡 Future Improvements

The project can be extended by adding:

-   Correlation analysis between numerical variables
-   Study-hours vs academic-score analysis
-   Subject-wise performance comparison
-   Interactive dashboards using Power BI
-   More advanced statistical analysis
-   Outlier analysis and treatment
-   Automated data-cleaning functions
-   Additional visualizations
-   A machine-learning model for student performance prediction
-   A polished project dashboard

------------------------------------------------------------------------

## 📌 Skills Demonstrated

This project demonstrates practical experience with:

-   Python for Data Analytics
-   Pandas
-   NumPy
-   Data Cleaning
-   Data Inspection
-   Exploratory Data Analysis
-   GroupBy Analysis
-   Descriptive Statistics
-   Matplotlib
-   Seaborn
-   Heatmaps
-   Count Plots
-   Box Plots
-   Pie Charts
-   Data Interpretation

------------------------------------------------------------------------

## 👨‍💻 Author

**Saiman Pal**

B.Tech Computer Science Engineering Student

Interested in **Data Analytics, Data Engineering, Python, SQL, and
Business Intelligence**.

------------------------------------------------------------------------

## ⭐ Project Purpose

This project was created as a practical Data Analytics / EDA project to
demonstrate the process of taking a raw dataset, cleaning it, exploring
its characteristics, visualizing patterns, and documenting observations
using Python.

If you find this project useful, consider giving the repository a ⭐ on
GitHub.
