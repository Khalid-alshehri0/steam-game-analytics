# 🎮 Steam Game Analytics

An end-to-end data analytics project built with **Power BI** to explore Steam games from multiple perspectives, including game popularity, player engagement, pricing, genres, and tags.

The project takes a raw Steam games dataset through a complete analytics workflow — from **data cleaning and transformation**, to **data modeling and DAX measures**, and finally to an interactive three-page Power BI dashboard.

---

## 📌 Project Overview

The goal of this project was to transform raw Steam game data into a structured analytical report that allows users to move from the **overall Steam landscape**, to **individual game performance**, and finally to **genre and tag-level patterns**.

The dashboard was intentionally divided into three pages, with each page answering a different analytical question.

### 1. Steam Overview

**"What does the Steam games dataset look like overall?"**

This page provides the high-level picture of the dataset, including:

* Total games
* Positive review rate
* Positive reviews
* Average Metacritic score
* Average game price
* Games released over time
* Genre distribution
* Top games by Peak CCU

The purpose of this page is to give users a quick understanding of the dataset before moving into deeper analysis.

![Steam Overview](images/steam-overview.png)

---

### 2. Game Analysis

**"How do individual games perform and how engaged are their players?"**

The second page focuses on game-level performance and player engagement.

It explores:

* Average playtime
* Average Peak CCU
* Total recommendations
* Estimated maximum owners
* Free vs paid games
* Price vs playtime
* Playtime vs Peak CCU
* Top games by recommendations

The page also includes filters for:

* Year
* Genre
* Price status

This page moves from the overall dataset into understanding **differences in popularity, pricing, and player engagement between games**.

![Game Analysis](images/game-analysis.png)

---

### 3. Genres / Tags Analysis

**"How do genres and tags shape the Steam games landscape?"**

The final page shifts the analysis from individual games to groups of games.

It explores:

* Total genres
* Top genre
* Average games per genre
* Total tags
* Average Peak CCU by genre
* Genre distribution
* Genre by price status
* Most common tags by game count

The purpose is to identify patterns across genres and tags and understand how different categories of games are represented and engaged with on Steam.

![Genres / Tags Analysis](images/genres-tags-analysis.png)

---

# 🔄 Data Analytics Workflow

The project followed a complete analytics workflow:

```text
Raw Steam Dataset
       ↓
Data Cleaning & Transformation
       ↓
Data Modeling
       ↓
DAX Measures
       ↓
Dashboard Design
       ↓
Interactive Analysis
```

This workflow was designed to turn the raw dataset into a structured and reusable analytical model rather than building visualizations directly from an unprepared table.

---

## 🧹 Data Cleaning & Transformation

The raw dataset contained game-level information such as:

* Game name
* App ID
* Price
* Reviews
* Recommendations
* Playtime
* Peak CCU
* Estimated owners
* Release date
* Genres
* Tags
* Metacritic score

The data was cleaned and transformed before being used in the analytical model.

Key preparation work included:

* Cleaning inconsistent values
* Handling missing and unavailable values
* Preparing date fields
* Separating multi-value genre information
* Preparing genre relationships
* Creating structures suitable for Power BI analysis

![Cleaned Data](images/cleaned-data.png)

The cleaned data represents the prepared dataset used as the foundation for the analytical model.

---

# 🧩 Data Model

After preparing the data, a dimensional model was created to make the dataset easier to analyze and to avoid relying on a single flat table.

The model includes structures such as:

* `DIM_GAME`
* `STEAM_GAME`
* `BRIDGE_GAME_GENRS`
* Dedicated Measures table

The bridge table was used to handle the relationship between games and genres, allowing genre-level analysis without unnecessarily duplicating game-level data.

![Data Model](images/data-model.png)

The data model provides the structure required for the dashboard's calculations, filtering, and genre-level analysis.

---

# 🧮 DAX & Measures

Reusable DAX measures were created to power the dashboard and allow calculations to respond dynamically to filters and user selections.

Examples include:

* Total Games
* Positive Review Rate
* Total Positive Reviews
* Average Metacritic Score
* Average Price
* Average Playtime Hours
* Average Peak CCU
* Total Recommendations
* Total Owners Max
* Total Genres
* Top Genre
* Average Games per Genre
* Total Tags
* Paid Games
* Paid Games %

For example:

```DAX
Total Games =
DISTINCTCOUNT(Dim_Game[app_id])
```

Using measures rather than manually calculated values allows the dashboard to update dynamically when users interact with filters.

---

# 📊 Key Dataset Statistics

The final dataset used in the dashboard contains:

| Metric                   | Value |
| ------------------------ | ----: |
| Total Games              |   292 |
| Paid Games               |   278 |
| Free Games               |    13 |
| Unavailable Price Status |     1 |
| Total Genres             |    11 |
| Total Tags               |   353 |

---

# 🔍 Key Analytical Questions

The dashboard was designed around practical analytical questions rather than simply displaying individual metrics.

### Overall Steam Landscape

* How many games are included in the dataset?
* How has game release activity changed over time?
* Which genres contain the most games?
* Which games have the highest Peak CCU?

### Game Performance

* How does player engagement differ between games?
* Is there a relationship between price and playtime?
* Is higher playtime associated with higher Peak CCU?
* Which games receive the most recommendations?
* How do free and paid games compare?

### Genre & Tag Analysis

* Which genres dominate the dataset?
* Which genres have the highest average Peak CCU?
* How are free and paid games distributed across genres?
* Which tags appear most frequently?

---

# 🛠️ Tools & Technologies

* **Power BI**
* **Power Query**
* **DAX**
* **Data Modeling**
* **Data Cleaning & Transformation**
* **Data Visualization**
* **GitHub**

---

# 🎯 Final Outcome

The final result is an interactive Power BI report that transforms raw Steam game data into a structured analytical experience.

The project demonstrates the complete process of turning raw data into a usable business intelligence solution:

**Cleaning → Modeling → DAX → Visualization → Analysis**

Each dashboard page has a distinct analytical role, allowing the user to move from the **overall Steam landscape**, to **game-level performance**, and finally to **genre and tag-level insights**.
