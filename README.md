
# 🌍 Travel Destination Sentiment Analysis

## 🔍 Overview
This project analyzes tourist reviews to understand sentiment patterns and highlight insights across various global destinations using:
- **Python (NLP & Sentiment Analysis)**
- **MySQL (Data Storage & Queries)**
- **Power BI (Interactive Dashboard & Visualizations)**

---

## 📁 Project Structure

```
📂 Travel-Destination-Sentiment-Analysis/
├── data/
│   └── synthetic_travel_reviews.csv
├── scripts/
│   ├── clean_data.py
│   ├── sentiment_analysis.py
│   ├── mysql_queries.py
│   └── visualizations.py
├── dashboard/
│   └── reviews_analysis.pbix
├── README.md
└── requirements.txt
```

---

## 🧰 Technologies Used
- **Python**: Pandas, TextBlob, NLTK, Seaborn, Matplotlib, WordCloud
- **MySQL**: Data warehousing and querying insights
- **Power BI**: Dashboards and sentiment visualization
- **Power BI Custom Visuals**: Word Cloud, Map, KPI Cards

---

## 📌 Features

### ✅ Python
- Scrape or load reviews
- Clean and tokenize text
- Perform sentiment analysis with TextBlob
- Generate 8+ types of visualizations (line, bar, heatmap, pie, donut, word cloud)

### ✅ MySQL
- Store review data
- Run DAX-like SQL queries (monthly trends, top cities, average ratings)
- Connect Power BI for live query insights

### ✅ Power BI

- **Page 1: Executive Summary**
  - KPI Cards: Total Reviews, Avg Rating, % Positive
  - Donut Chart: Sentiment Distribution
  - Word Cloud: Frequent keywords
- **Page 2: Location Analysis**
  - Map: Destinations by Sentiment
  - Bar Chart: Top Cities by Ratings
- **Page 3: Temporal Analysis**
  - Line Chart: Monthly Sentiment Trends
  - Heatmap: Month vs Year frequency
- **Page 4: Detailed Reviews**
  - Table: User feedback with sentiment
  - Buttons: Toggle filters, slicers by date/location

---

## 📊 DAX Measures Used
```dax
Positive Sentiment % = 
DIVIDE(
    CALCULATE(COUNTROWS(Reviews), Reviews[Sentiment] = "Positive"),
    COUNTROWS(Reviews)
)

Average Rating = AVERAGE(Reviews[Rating])

Review Month = FORMAT(Reviews[Review_Date], "MMMM")
Review Year = YEAR(Reviews[Review_Date])
```

---

## 🗺️ Map Configuration in Power BI
To map reviews:
- Use **Location** or **City** column
- Set **data category** as *City*, *Country*, or *Place*
- Add to a **Map** visual or **Filled Map**

---

## 📦 Setup Instructions

### Python Environment
```bash
pip install -r requirements.txt
```

### Required NLTK Files
```python
import nltk
nltk.download('punkt')
nltk.download('stopwords')
nltk.download('wordnet')
```

### MySQL Setup
- Import CSV to MySQL using `LOAD DATA` or `pandas.to_sql()`
- Sample Query:
```sql
SELECT Location, COUNT(*) AS ReviewCount, 
       AVG(Rating) AS AvgRating 
FROM Reviews 
GROUP BY Location 
ORDER BY AvgRating DESC;
```

---

## 📁 Requirements
```
pandas
matplotlib
seaborn
textblob
wordcloud
nltk
mysql-connector-python
```

---

## 📌Conclusion

This project demonstrates how NLP, SQL, and BI tools can be combined to derive actionable insights from user-generated content in the travel industry.

Built with ❤️ by Akash Singh Rathour
