
# 🧺 Web Scraping & Exploratory Data Analysis – Washing Machines (Flipkart)

## 📘 Project Overview
This project focuses on **web scraping washing machine data from Flipkart** and performing **Exploratory Data Analysis (EDA)** to uncover insights about pricing, ratings, and performance.  
It demonstrates **data collection, cleaning, visualization, and business analysis** using Python.

## 🎯 Objectives
- Reduce manual effort and washing time  
- Introduce **energy-efficient and water-saving** technologies  
- Make washing machines **affordable and user-friendly**  
- Promote **smart washing solutions** for every household  

---

## 🕸️ Web Scraping Process
- **Data Source:** Flipkart official website  
- **Tools Used:** `BeautifulSoup`, `Requests`, `pandas`  

### Steps:
1. Used browser **Inspect Element** to identify relevant HTML elements  
2. Extracted data such as `Product Name`, `Brand`, `Price`, `Rating`, and `Reviews`  
3. Cleaned and consolidated multiple product pages  
4. Saved structured data for further analysis and visualization  

---

## 🧹 Data Cleaning
- Removed **duplicates and irrelevant** records  
- Fixed inconsistent **date/time** and **product format**  
- Filled **missing values** (price, cycle duration, etc.)  
- Standardized categorical columns (brand, wash type, energy rating)  
- Verified data integrity before visualization  

---

## 📊 Data Visualization & Analysis

### 🔹 Univariate Analysis
- Most machines use **1.2–1.6 kWh** power and **40–60 L** water per wash  
- Cycle durations range between **20–30 minutes**, showing efficiency  

### 🔹 Bivariate Analysis
- Analyzed **Brand vs Rating** using bar and error plots  
- Identified brands with **higher customer satisfaction**  

### 🔹 Multivariate Analysis
- Explored relationships between **Price, Ratings, and Reviews**  
- Found:
  - Strong correlation between `no_of_reviews` and `no_of_ratings` (1.00)  
  - Moderate correlation between `original_price` and `processor_name` (0.20)  

---

## ❓ Key Business Questions
- Which washing programs use the most power and water?  
- Which brands perform best in terms of ratings and efficiency?  
- What factors influence washing machine pricing?  
- How can performance and cost be optimized?  

---

## 📈 Key Insights
1. **Consistent Usage Patterns:** Usage is steady with clear peak times  
2. **Efficient Models:** Some brands use less power/water  
3. **Top-Performing Brands:** Maintain strong ratings and reliability  
4. **Usage Settings:** Quick Wash affects energy consumption  
5. **Optimization:** Insights help reduce costs and improve performance  

---

## ⚙️ Tools & Libraries
- **Python**
- **BeautifulSoup**
- **Requests**
- **Pandas**
- **Matplotlib**
- **Seaborn**

---

## 📁 Folder Structure
```

Web_Scraping_WashingMachine/
│
├── data/
│   ├── washing_machine_raw.csv
│   └── washing_machine_clean.csv
│
├── notebooks/
│   └── washing_machine_EDA.ipynb
│
├── scripts/
│   └── web_scraper.py
│
├── visuals/
│   ├── univariate_analysis.png
│   ├── bivariate_analysis.png
│   └── correlation_heatmap.png
│
└── README.md

````

---

## 💡 Sample Code – Web Scraping
```python
import requests
from bs4 import BeautifulSoup
import pandas as pd

url = "https://www.flipkart.com/search?q=washing+machine"
response = requests.get(url)
soup = BeautifulSoup(response.text, "html.parser")

names, prices, ratings = [], [], []

for product in soup.find_all('div', {'class': '_1AtVbE'}):
    name = product.find('a', {'class': 'IRpwTa'})
    price = product.find('div', {'class': '_30jeq3'})
    rating = product.find('div', {'class': '_3LWZlK'})
    
    if name and price:
        names.append(name.text)
        prices.append(price.text)
        ratings.append(rating.text if rating else 'N/A')

df = pd.DataFrame({'Name': names, 'Price': prices, 'Rating': ratings})
df.to_csv('washing_machine_data.csv', index=False)
````

---

## 🧠 Challenges Faced

* Changing Flipkart webpage structures
* Handling **missing or duplicate** product details
* Avoiding **request blocking** during scraping
* Selecting clear and meaningful visuals

---

## 🏁 Conclusion

This project shows how **real-world e-commerce data** can be collected, cleaned, and analyzed to reveal valuable business insights.
It demonstrates practical skills in **Python, web scraping, EDA, and data visualization**, forming a strong foundation for **data analytics and AI roles**.

---

## ✨ Experience Gained

* End-to-End workflow: *Scraping → Cleaning → EDA → Visualization → Insights*
* Improved analytical and storytelling skills using real-world datasets

---

## 📬 Contact

If you found this project helpful, feel free to connect or contribute!

**LinkedIn:** [Lakshmi Sampathi](https://linkedin.com/in/lakshmi-sampathi-6b10ba305)
**GitHub:** [sampathilakshmi959](https://github.com/sampathilakshmi959

Would you like me to **add badges (like Python, Pandas, BeautifulSoup, Flipkart Dataset)** and a **project thumbnail image** section to make your GitHub page more attractive?
