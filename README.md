# Movie Industry Correlation Analysis 🎬📈

This repository contains a Python-based data analytics project exploring the core factors that drive a movie's financial success. Utilizing a historical movie dataset, the project primarily focuses on thorough **Data Cleaning** and **Correlation Analysis** to uncover what variables impact global gross revenue the most.

## 📌 Project Objectives
The main question this project aims to answer is: **"Which factors have the strongest correlation with a movie's gross revenue?"** 

The project evaluates and tests multiple hypotheses regarding the influence of:
* Production budget (`budget`)
* Audience rating score (`score`)
* Number of user reviews/votes (`votes`)
* Production companies (`company`)

## 📊 Dataset Overview
The dataset encompasses a comprehensive list of movies spanning several decades, containing the following attributes:
* `name`: Name of the movie
* `rating`: Motion picture rating (R, PG-13, PG, etc.)
* `genre`: Main genre of the movie
* `year`: Release year
* `released`: Official release date and country
* `score`: Audience rating score (1-10 scale)
* `votes`: Number of user votes
* `director`, `writer`, `star`: Core creative talent involved
* `country`: Country of origin
* `budget`: Total financial budget to produce the movie
* `gross`: Global gross revenue generated
* `company`: Production company
* `runtime`: Duration of the movie in minutes

## 🛠️ Data Pipeline & Methodology

### 1. Data Cleaning & Preparation
Before diving into analysis, data integrity was ensured through the following preprocessing steps:
* **Missing Data Assessment:** Checked for null percentages across all columns (discovering `budget` missed around 28% of values).
* **Data Type Standardization:** Casted `budget` and `gross` into the `Int64` type to eliminate unnecessary decimal points and handle large numbers elegantly.
* **Deduplication:** Screened the dataset to ensure no duplicate entries warped the statistical counts.
* **Release Year Alignment:** Fixed inconsistency between the `year` column and the actual year inside the `released` string by extracting a clean 4-digit year into a new column called `yearcorrect` using Regular Expressions (Regex).
* **Cleaned Data Export:** Exported the finalized dataframe into a clean file called `movies_clean.csv`.

### 2. Exploratory Data Analysis (EDA)
Several insights and data distributions were captured through visualization:
* Visualized distribution of `budget` and `gross` using histograms.
* Evaluated outlier boundaries for `gross` revenue through boxplots.
* Plotted top 10 historical genres and producing countries.
* Tracked the historical trajectory of gross revenue over the years (`yearcorrect`).
* Identified the top 10 highest-grossing movies and top 10 highest-rated movies by audience score.

### 3. Correlation Analysis (Core Hypothesis Testing)
* **Correlation Matrix:** Calculated Pearson correlation coefficients for numerical variables (`budget`, `gross`, `score`, `votes`, `runtime`) using Pandas and visualized via a Seaborn heatmap.
* **Regression Modeling:** Plotted the linear trend between `budget` and `gross` revenue using `sns.scatterplot` and `sns.regplot` to evaluate the directional slope.

## 💡 Key Findings & Conclusions
1. **Budget vs. Gross Revenue:** Production budget exhibits a strong, positive correlation with overall gross revenue. High-budget blockbusters systematically correlate with larger box office earnings.
2. **Votes vs. Gross Revenue:** The number of user votes on a movie also shows a high correlation with gross revenue, signifying that audience popularity, engagement, and viral word-of-mouth correspond heavily with commercial success.
3. **Studio Dominance:** Major entertainment conglomerates like *Warner Bros.*, *Universal Pictures*, and *Columbia Pictures* historically dominate cumulative worldwide gross statistics within this dataset.

## 🚀 Technologies Used
* **Programming Language:** Python 3
* **Data Manipulation:** Pandas, NumPy
* **Data Visualization:** Matplotlib, Seaborn

## 💻 How to Run the Project

1. Clone this repository to your local machine:
   ```bash
   git clone https://github.com/your-username/movie-correlation-project.git
   ```
2. Ensure you have Jupyter Notebook, JupyterLab, or VS Code configured.
3. Install the required dependencies:
   ```bash
   pip install pandas numpy matplotlib seaborn
   ```
4. Place the source `movies.csv` file into your root directory or update the file path in the first few cells of the notebook.
5. Execute the `Movie Portfolio Project-Final.ipynb` file sequentially from top to bottom.

---
*This project is part of my professional Data Analytics Portfolio.*
