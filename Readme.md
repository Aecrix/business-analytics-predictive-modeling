# Business Analytics & Predictive Modeling Suite

A portfolio of three applied data analytics and machine learning projects covering **business analysis, exploratory analysis, forecasting, and recommendation systems**.

## Projects

### 1. Walmart Sales Analysis & Forecasting

**Objective:** Analyze historical Walmart sales, identify store-level and temporal patterns, and forecast future sales for selected stores.

**Key Work**
- Performed exploratory analysis of Walmart sales data.
- Analyzed sales patterns across stores and time periods.
- Segregated individual stores for deeper analysis.
- Applied time-series forecasting to selected stores.
- Applied **ARIMA/SARIMA time-series models** to forecast sales for selected stores.
- Generated forecast outputs and visualizations.

**Techniques:** `Python` · `Pandas` · `NumPy` · `Matplotlib` · `Seaborn` · `Time-Series Analysis` · `ARIMA/SARIMA`

---

### 2. COVID-19 Data Analysis

**Objective:** Analyze global COVID-19 data to identify country-level and temporal patterns in confirmed cases, recoveries, and deaths.

**Key Work**
- Cleaned and prepared the COVID-19 dataset.
- Performed exploratory data analysis.
- Examined country-level and temporal trends.
- Aggregated relevant COVID-19 indicators.
- Used visualizations to communicate patterns in the dataset.

**Techniques:** `Python` · `Pandas` · `NumPy` · `Matplotlib` · `Seaborn` · `Exploratory Data Analysis`

---

### 3. Netflix-Style Movie Recommendation Engine

**Objective:** Build a recommendation engine that analyzes user ratings and movie genres to:

1. Find the **most popular and most liked genres**.
2. Build a model that recommends the **best-suited movie for a user in every genre**.
3. Identify the **best- and worst-rated genres**.

#### Dataset Processing

The ratings data is provided in a Netflix-style format where each movie is represented by a movie-ID marker:

```text
1:
1488844,3,2005-09-06
822109,5,2005-05-13

2:
...
```

The data is parsed into:

```text
movieId | userId | rating
```

Movie metadata is joined using `movieId`:

```text
movieId | title | genres
```

#### Genre Analysis

Movies containing multiple genres are expanded so that each genre can be analyzed independently.

The analysis measures:

- **Popularity** → total number of ratings received by a genre.
- **Liked** → average user rating for a genre.

Results:

- **Most popular:** Drama — 11,450,961 ratings
- **Highest average rating:** IMAX — 3.8264 / 5
- **Lowest average rating:** Documentary — 3.5138 / 5

#### Recommendation Model

The recommendation component uses **item-based collaborative filtering with K-Nearest Neighbors (KNN)**.

```text
User Ratings
     ↓
Movie–User Sparse Matrix
     ↓
Cosine Similarity
     ↓
Nearest Movie Neighbors
     ↓
Similarity-Weighted Recommendation Scores
     ↓
Unseen Movie Candidates
     ↓
Best Recommendation per Genre
```

The model uses movies rated **4 or 5** by the selected user as preference signals, finds similar movies using cosine similarity, removes movies the user has already rated, and ranks the remaining candidates using a **recommendation score**.

A sparse matrix representation is used to handle the large ratings dataset efficiently.

---

## Technology Stack

### Programming & Analysis
- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn

### Machine Learning
- Scikit-learn
- K-Nearest Neighbors
- Cosine similarity
- Collaborative filtering

### Forecasting
- Time-series analysis
- ARIMA/SARIMA

### Development
- Jupyter Notebook
- VS Code
- Git
- GitHub

---

## Repository Structure

```text
business-analytics-predictive-modeling/
│
├── data/
│   ├── covid_19_clean_complete.csv
│   ├── movies.csv
│   └── Walmart DataSet.csv
│
├── notebooks/
│   ├── covid19_analysis.ipynb
│   ├── Netflix_recommendation_engine.ipynb
│   └── walmart_analysis.ipynb
│
├── outputs/
│   ├── figures/
│   └── forecasts/
│
├── .gitignore
└── README.md
```

The large raw `ratings.txt` file used by the Netflix recommendation engine is excluded from version control because of its size. The `movie_titles.csv` file is also not required by the final recommendation workflow, which uses `movies.csv` for movie metadata and genres.

The notebooks are organized as documented analysis workflows; datasets excluded from version control must be obtained separately to reproduce those analyses.


## Project Focus

The suite demonstrates a progression from:

**Descriptive Analytics → Exploratory Analysis → Predictive Modeling → Forecasting → Recommendation Systems**

It focuses on applying practical data analysis and machine learning techniques to different real-world-style datasets and business problems.

---

## Author

**Vihan Sharma**

B.Tech — Electronics & Communication Engineering  
Minor — Artificial Intelligence & Data Science
