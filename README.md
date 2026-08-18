# 📱 Google Play Store Data Analysis

## 📌 Project Overview

This project performs **Exploratory Data Analysis (EDA)** on Google Play Store application data using Python.

The analysis focuses on understanding app characteristics such as **ratings, reviews, installs, categories, prices, app types, content ratings, and other attributes**. The project also includes data cleaning and visualization to identify patterns and trends across different app categories.

---

## 🎯 Objectives

The main objectives of this project are:

* Analyze the Google Play Store dataset.
* Understand the structure and characteristics of the data.
* Identify and handle missing values.
* Detect duplicate records.
* Perform data cleaning and preprocessing.
* Analyze app ratings across different categories.
* Analyze app prices by category.
* Explore relationships between different app attributes.
* Create visualizations to identify important patterns and trends.
* Generate meaningful insights from the data.

---

## 📊 Dataset

The dataset contains **10,841 rows and 13 columns**.

### Dataset Features

| Column           | Description                        |
| ---------------- | ---------------------------------- |
| `App`            | Name of the application            |
| `Category`       | Category of the application        |
| `Rating`         | User rating of the application     |
| `Reviews`        | Number of reviews received         |
| `Size`           | Size of the application            |
| `Installs`       | Number of installations            |
| `Type`           | Whether the app is Free or Paid    |
| `Price`          | Price of the application           |
| `Content Rating` | Target audience/content rating     |
| `Genres`         | Genre of the application           |
| `Last Updated`   | Date when the app was last updated |
| `Current Ver`    | Current version of the application |
| `Android Ver`    | Minimum Android version required   |

## The notebook confirms these 13 columns and the initial dataset size.

## 🛠️ Technologies Used

* **Python**
* **Pandas** – Data manipulation and analysis
* **NumPy** – Numerical operations
* **Matplotlib** – Data visualization
* **Seaborn** – Statistical visualization
* **Jupyter Notebook**

---

## 🔄 Project Workflow

### 1. Import Libraries

The project uses the following Python libraries:

```python
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
```

The Google Play Store dataset is loaded using Pandas.

---

### 2. Data Exploration

Initial exploration is performed to understand:

* Dataset dimensions
* Column names
* Data types
* Missing values
* Duplicate records
* Statistical information

The dataset initially contains **10,841 records and 13 columns**.

---

### 3. Missing Value Analysis

Missing values were identified using:

```python
df.isnull().sum()
```

The `Rating` column contains **1,474 missing values**, while smaller numbers of missing values occur in `Type`, `Content Rating`, `Current Ver`, and `Android Ver`.

For the analysis, rows with missing `Rating` and `Type` values were removed:

```python
df = df.dropna(subset=['Rating'])
df = df.dropna(subset=['Type'])
```

---

### 4. Duplicate Data Analysis

Duplicate records were checked using:

```python
df.duplicated().sum()
```

The dataset contains **483 duplicate records** according to the notebook.

---

### 5. Rating Analysis

The rating distribution was analyzed using descriptive statistics.

After removing missing ratings:

* Number of ratings: **9,367**
* Mean rating: **4.19**
* Median rating: **4.3**
* Minimum rating: **1.0**
* Maximum rating: **19.0**

> **Note:** A maximum rating of 19.0 indicates a data-quality issue in the dataset that could be investigated further as part of data validation.

---

### 6. Category Analysis

The project analyzes application categories and their ratings.

The dataset contains categories such as:

* Family
* Game
* Tools
* Productivity
* Medical
* Communication
* Sports
* Finance
* Photography
* Lifestyle
* Business
* Social
* Shopping
* Education
* Travel & Local
* Health & Fitness
* Entertainment
* Food & Drink
* Weather
* Art & Design

and several others.

Category-level rating analysis is performed using:

```python
category_rating = (
    df.groupby('Category')['Rating']
      .sum()
      .sort_values(ascending=False)
      .reset_index()
)
```

---

### 7. Price Analysis

The `Price` column was converted from string format into a numerical format by removing the `$` symbol:

```python
df['Price'] = df['Price'].str.replace('$', '', regex=False)
df['Price'] = pd.to_numeric(df['Price'], errors='coerce')
```

The project then analyzes the total price of apps across different categories.

For example, the analysis shows higher total prices in categories such as **Finance, Family, Lifestyle, and Medical**.

---

## 📈 Data Visualization

Matplotlib and Seaborn are used to visualize the analysis.

The visualizations help understand:

* App category distribution
* Ratings across categories
* Price distribution
* Category-wise pricing
* Other relationships between application attributes

These visualizations make it easier to identify trends and patterns in the Google Play Store dataset.

---

## 🔍 Key Analysis Areas

The project investigates questions such as:

1. Which app categories are most prominent?
2. How are ratings distributed across applications?
3. Which categories have higher ratings?
4. Which categories contain more expensive applications?
5. What is the distribution of free and paid applications?
6. How do application characteristics vary across categories?
7. Are there data-quality issues such as missing values, duplicates, or invalid ratings?

---

## 📁 Project Structure

```text
Google-Play-Store-Data-Analysis/
│
├── Google Playstore Project(1).ipynb
├── googleplaystore.csv
└── README.md
```

---

## ▶️ How to Run the Project

### Step 1: Clone the Repository

```bash
git clone <your-github-repository-url>
```

### Step 2: Navigate to the Project Folder

```bash
cd Google-Play-Store-Data-Analysis
```

### Step 3: Install Required Libraries

```bash
pip install pandas numpy matplotlib seaborn jupyter
```

### Step 4: Launch Jupyter Notebook

```bash
jupyter notebook
```

### Step 5: Open the Notebook

Open:

```text
Google Playstore Project(1).ipynb
```

Make sure `googleplaystore.csv` is present in the appropriate directory before running the notebook.

---

## 💡 Skills Demonstrated

This project demonstrates practical experience with:

* Data Cleaning
* Data Preprocessing
* Exploratory Data Analysis
* Missing Value Handling
* Duplicate Detection
* Data Type Conversion
* GroupBy Operations
* Descriptive Statistics
* Data Visualization
* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn

---

## 📌 Conclusion

The Google Play Store Data Analysis project demonstrates how Python can be used to transform raw application data into meaningful insights.

The project covers the complete basic EDA workflow—from **loading and understanding the dataset to cleaning data, analyzing categories and ratings, converting numerical fields, and creating visualizations**.

It is a useful project for demonstrating practical **Data Analytics and Python skills** in a portfolio or GitHub repository.

---

## 👩‍💻 Author

**Ashwitha Gogikar**

* GitHub: [gshwitha2000-wq](https://github.com/gshwitha2000-wq)
* LinkedIn: [Ashwitha Gogikar](https://www.linkedin.com/in/ashwitha-gogikar-35839a1b5/)
