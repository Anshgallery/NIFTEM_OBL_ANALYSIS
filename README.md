# Customer Flavour Preference Analysis — Old Batra Lemon
## Project Demo Video

🎥 [Watch NIFTEM Exhibition Demo Video](https://github.com/Anshgallery/NIFTEM_OBL_ANALYSIS/blob/b16b5ed1f8a6808ed1b7806cbf50c164d20f8894/WhatsApp%20Video%202026-05-16%20at%2011.50.20.mp4)
![Old Batra Lemon Banner](https://github.com/Anshgallery/NIFTEM_OBL_ANALYSIS/blob/f8c3ad7d462a81f0b0038da5b6e935fbd3776ce9/Screenshot%202026-02-21%20163300.png)

## Project Overview

This project is based on my on-ground experience at the **AVNESH NIFTEM Kundli Exhibition**, held from **26 February to 28 February 2026**, where I represented **Old Batra Lemon** in a professional brand and visitor engagement role.

During the exhibition, I interacted directly with visitors, handled product-related queries, observed customer reactions, collected structured feedback, and later converted that feedback into a data analysis project using Python.

The purpose of this project is to show how real exhibition feedback can be converted into meaningful business insights using data analysis.

---

## My Role

I worked as a business/data-focused representative for Old Batra Lemon during the exhibition. My responsibilities included:

- Managing visitor interaction at the stall
- Explaining product categories and flavours
- Handling business and product-related queries
- Observing customer interest and product response
- Collecting structured visitor feedback
- Organising the collected data for analysis
- Analysing the data using Python libraries
- Converting raw feedback into business insights

This project helped me connect **business communication, customer behaviour, and data analytics** in a real-world environment.

---

## Exhibition Glimpses

### Brand Interaction at Exhibition

![Brand Interaction](https://github.com/Anshgallery/NIFTEM_OBL_ANALYSIS/blob/5828f0ba981dc9a31473b2898ac543a81d9d6981/Screenshot%202026-05-15%20171453.png)

This image represents my professional interaction environment during the exhibition. It reflects the real business setting where visitor engagement, product explanation, and brand communication were handled.



### Product Sample

![Old Batra Lemon Bottle](https://github.com/Anshgallery/NIFTEM_OBL_ANALYSIS/blob/395ea0180dc2a6b954cd46504ee169f920d280a3/Screenshot%202026-02-21%20163310.png)

The product analysis focused on customer preference, flavour response, rating behaviour, sugar preference, and purchase intent.

---

### Engagement Session

![Visitor Engagement](https://github.com/Anshgallery/NIFTEM_OBL_ANALYSIS/blob/87b9ac3e993982a3dcc78622e37a1b7357bb7ae8/Screenshot%202026-05-15%20171434.png)

## Dataset Note

The dataset used in this project is a **synthetic/reconstructed event-style survey dataset** created for analysis practice and portfolio presentation.

It is based on the structure of feedback collected during the exhibition, but it should not be treated as original raw customer data.

This ethical note is important because the project is designed for learning, portfolio building, and demonstrating data analysis skills.

---

## Problem Statement

During exhibitions, businesses receive a lot of customer feedback, but raw feedback alone does not directly support decision-making.

The main problem is:

> Which flavours are most preferred by visitors, and how can customer feedback be converted into product-level business recommendations?

This project solves that problem by analysing visitor responses and identifying:

- Most preferred milk-based flavour
- Most preferred water-based flavour
- Average rating by flavour
- Sugar vs non-sugar preference
- Purchase intent
- Feedback themes
- Final product recommendation

---

## Dataset Description

The dataset contains **245 survey responses**.

Each row represents one visitor response, and each column represents one survey attribute.

Important columns used in the project:

| Column Name | Meaning |
|---|---|
| `respondent_type` | Type of respondent such as student, visitor, or professional |
| `age_group` | Age category of respondent |
| `best_milk_based_flavor` | Preferred milk-based flavour |
| `best_water_based` | Preferred water-based flavour |
| `milk_rating` | Rating for milk-based flavour out of 10 |
| `water_rating_10` | Rating for water-based flavour out of 10 |
| `overall_experience_10` | Overall experience rating out of 10 |
| `sugar_preference` | Sugar or non-sugar preference |
| `purchase_intent` | Likelihood of purchase |
| `feedback_theme` | Main feedback category |

---

## Tools and Libraries Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- SciPy
- Jupyter Notebook

---

## Core Skills Reflected

This project reflects the following data analysis skills:

- Data loading using Pandas
- Data inspection and understanding
- Missing value checking
- Exploratory Data Analysis
- Grouping and aggregation
- Mode analysis using Pandas and SciPy
- Data visualization using Matplotlib
- Correlation analysis using Seaborn
- Business insight writing
- Customer behaviour analysis
- Product recommendation based on data

---

## Project Workflow

The project was completed in the following steps:

1. Imported required Python libraries
2. Loaded the survey dataset
3. Checked dataset shape, columns, and data types
4. Checked missing values
5. Calculated basic KPIs
6. Found most preferred flavours using mode
7. Visualised flavour preferences using bar charts
8. Compared average ratings by flavour
9. Analysed purchase intent
10. Analysed sugar vs non-sugar preference
11. Analysed customer feedback themes
12. Created a correlation heatmap
13. Prepared final business recommendations

---

## Step 1: Import Libraries

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
from scipy import stats
```

These libraries were used for data handling, numerical calculations, visualisation, and statistical analysis.

---

## Step 2: Load Dataset

```python
df = pd.read_csv("data/niftem_synthetic_flavour_survey_245_rows.csv")

df.head()
```

This step loads the dataset into a Pandas DataFrame and displays the first five rows.

---

## Step 3: Data Inspection

```python
df.shape
```

```python
df.info()
```

```python
df.columns
```

```python
df.isnull().sum()
```

This step helped me understand the size of the dataset, available columns, data types, and missing values.

---

## Step 4: Basic KPI Summary

```python
total_responses = len(df)

avg_milk_rating = df["milk_rating"].mean()
avg_water_rating = df["water_rating_10"].mean()
avg_overall_experience = df["overall_experience_10"].mean()

print("Total Responses:", total_responses)
print("Average Milk Rating:", round(avg_milk_rating, 2))
print("Average Water Rating:", round(avg_water_rating, 2))
print("Average Overall Experience:", round(avg_overall_experience, 2))
```

### Insight

This step gives a quick overview of the project by showing total responses and average ratings. These KPIs help understand the overall customer response before moving into deeper analysis.

---

## Step 5: Mode Analysis

```python
milk_mode = df["best_milk_based_flavor"].mode()[0]
water_mode = df["best_water_based"].mode()[0]
intent_mode = df["purchase_intent"].mode()[0]

print("Most preferred milk-based flavour:", milk_mode)
print("Most preferred water-based flavour:", water_mode)
print("Most common purchase intent:", intent_mode)
```

### Why Mode Was Used

Mode is useful because flavour choice is categorical data. It helps identify the most repeated customer choice.

### Insight

The mode analysis helped identify the most preferred milk-based flavour, most preferred water-based flavour, and most common purchase intent among visitors.

---

## Step 6: SciPy Mode Analysis

```python
overall_rating_mode = stats.mode(df["overall_experience_10"], keepdims=True)

print("Most common overall experience rating:", overall_rating_mode.mode[0])
print("Frequency:", overall_rating_mode.count[0])
```

### Insight

SciPy mode was used to find the most common numerical rating. This added a statistical analysis component to the project.

---

## Step 7: Milk-Based Flavour Preference

```python
milk_counts = df["best_milk_based_flavor"].value_counts()

plt.figure(figsize=(8, 5))
milk_counts.plot(kind="bar")

plt.title("Most Preferred Milk-Based Flavours")
plt.xlabel("Milk-Based Flavour")
plt.ylabel("Number of Respondents")
plt.xticks(rotation=45)
plt.tight_layout()
plt.show()
```

### Insight

This graph shows which milk-based flavour received the highest number of selections. A bar chart was used because flavour names are categories and the objective is to compare counts.

---

## Step 8: Water-Based Flavour Preference

```python
water_counts = df["best_water_based"].value_counts()

plt.figure(figsize=(8, 5))
water_counts.plot(kind="bar")

plt.title("Most Preferred Water-Based Flavours")
plt.xlabel("Water-Based Flavour")
plt.ylabel("Number of Respondents")
plt.xticks(rotation=45)
plt.tight_layout()
plt.show()
```

### Insight

This graph shows the most preferred water-based flavour. It helps identify which flavour has the strongest customer demand in the water-based category.

---

## Step 9: Average Rating by Milk-Based Flavour

```python
milk_rating_avg = df.groupby("best_milk_based_flavor")["milk_rating"].mean().sort_values(ascending=False)

plt.figure(figsize=(8, 5))
milk_rating_avg.plot(kind="bar")

plt.title("Average Rating by Milk-Based Flavour")
plt.xlabel("Milk-Based Flavour")
plt.ylabel("Average Rating out of 10")
plt.ylim(0, 10)
plt.xticks(rotation=45)
plt.tight_layout()
plt.show()
```

### Insight

Only counting votes is not enough. A flavour should be both popular and highly rated. This analysis compares average customer rating by milk-based flavour.

---

## Step 10: Average Rating by Water-Based Flavour

```python
water_rating_avg = df.groupby("best_water_based")["water_rating_10"].mean().sort_values(ascending=False)

plt.figure(figsize=(8, 5))
water_rating_avg.plot(kind="bar")

plt.title("Average Rating by Water-Based Flavour")
plt.xlabel("Water-Based Flavour")
plt.ylabel("Average Rating out of 10")
plt.ylim(0, 10)
plt.xticks(rotation=45)
plt.tight_layout()
plt.show()
```

### Insight

This analysis helps identify which water-based flavour performed best not only by popularity but also by customer satisfaction.

---

## Step 11: Purchase Intent Analysis

```python
purchase_counts = df["purchase_intent"].value_counts()

plt.figure(figsize=(7, 5))
purchase_counts.plot(kind="bar")

plt.title("Customer Purchase Intent")
plt.xlabel("Purchase Intent")
plt.ylabel("Number of Respondents")
plt.xticks(rotation=0)
plt.tight_layout()
plt.show()
```

### Insight

Purchase intent is important because it connects survey response with business potential. If most visitors show high or medium purchase intent, it indicates good market acceptance.

---

## Step 12: Sugar vs Non-Sugar Preference

```python
sugar_counts = df["sugar_preference"].value_counts()

plt.figure(figsize=(6, 6))
sugar_counts.plot(kind="pie", autopct="%1.1f%%")

plt.title("Sugar vs Non-Sugar Preference")
plt.ylabel("")
plt.tight_layout()
plt.show()
```

### Insight

This analysis helps understand whether customers prefer regular sugar-based products or non-sugar alternatives. It can support future product positioning.

---

## Step 13: Feedback Theme Analysis

```python
feedback_counts = df["feedback_theme"].value_counts()

plt.figure(figsize=(9, 5))
feedback_counts.plot(kind="bar")

plt.title("Customer Feedback Themes")
plt.xlabel("Feedback Theme")
plt.ylabel("Number of Respondents")
plt.xticks(rotation=45, ha="right")
plt.tight_layout()
plt.show()
```

### Insight

Feedback theme analysis helps convert visitor opinions into business insights. It shows what customers remembered most about the product.

---

## Step 14: Correlation Analysis

```python
rating_corr = df[["milk_rating", "water_rating_10", "overall_experience_10"]].corr()

plt.figure(figsize=(6, 4))
sns.heatmap(rating_corr, annot=True, cmap="Blues")

plt.title("Correlation Between Ratings")
plt.tight_layout()
plt.show()
```

### Insight
The correlation heatmap shows that overall customer experience has a positive relationship with both milk-based ratings and water-based ratings. Water-based rating shows a slightly stronger correlation with overall experience (0.67) compared to milk-based rating (0.63). This means both product categories contributed to customer satisfaction, with water-based flavours having a slightly higher impact.
![correlation](https://github.com/Anshgallery/NIFTEM_OBL_ANALYSIS/blob/451c626fb78ea50cc95f92e1d5d2b79a9fa45fd3/Screenshot%202026-05-19%20125201.png)


---

## Step 15: Final Flavour Recommendation

```python
milk_summary = df.groupby("best_milk_based_flavor").agg(
    total_votes=("best_milk_based_flavor", "count"),
    average_rating=("milk_rating", "mean")
).sort_values(by=["total_votes", "average_rating"], ascending=False)

water_summary = df.groupby("best_water_based").agg(
    total_votes=("best_water_based", "count"),
    average_rating=("water_rating_10", "mean")
).sort_values(by=["total_votes", "average_rating"], ascending=False)

print("Milk-Based Flavour Summary")
display(milk_summary)

print("Water-Based Flavour Summary")
display(water_summary)
```

### Insight

This final summary considers both vote count and average rating. This is better than selecting a flavour only by popularity.

---

## Key Findings

- Mango performed strongly in the milk-based category.
- Lemon performed strongly in the water-based category.
- Blueberry showed good potential as a secondary water-based flavour.
- Purchase intent was mostly positive.
- Sugar-based variants had strong demand.
- Non-sugar variants also showed opportunity.
- Feedback themes helped understand customer perception beyond ratings.

---

## Business Recommendation

Based on the analysis, Mango and Lemon should be considered the primary product focus. Mango can be positioned as the strongest milk-based flavour, while Lemon can be positioned as the strongest water-based flavour.

Blueberry can be considered as a secondary water-based option because it showed good customer interest.

The brand can also consider maintaining both sugar and non-sugar variants to serve regular customers as well as health-conscious customers.

---

## LinkedIn Milestone

![LinkedIn Post](https://github.com/Anshgallery/NIFTEM_OBL_ANALYSIS/blob/b8cb33d1afe6cc3a22a1a88095a10bb67fa3f0e3/Screenshot%202026-05-15%20171512.png)

This project is connected with my real professional milestone, where I represented Old Batra Lemon at the NIFTEM exhibition and later converted the experience into a data analytics project.

---

## Final Conclusion

This project helped me understand how real-world business interaction and customer feedback can be converted into structured data insights.

It was not only about creating charts. It was about understanding customer behaviour, identifying product opportunities, and presenting insights in a way that supports business decisions.

Through this project, I practiced Python, Pandas, NumPy, Matplotlib, Seaborn, SciPy, and business insight writing in a practical environment.

---

## Resume Project Summary

**Customer Flavour Preference Analysis | Python, Pandas, NumPy, Matplotlib, Seaborn, SciPy**

Analysed 245+ exhibition-style customer survey responses to identify top-performing flavours, customer rating patterns, sugar preference, purchase intent, and feedback themes. Used Python-based analysis to recommend Mango and Lemon as primary product flavours based on customer preference and rating behaviour.

---

## Repository Structure

```text
customer-flavour-preference-analysis/
│
├── data/
│   └── niftem_synthetic_flavour_survey_245_rows.csv
│
├── notebook/
│   └── flavour_preference_analysis.ipynb
│
├── assets/
│   ├── old_batra_product_banner.png
│   ├── exhibition_brand_interaction.png
│   ├── visitor_engagement_session.png
│   ├── old_batra_lemon_logo.png
│   ├── old_batra_lemon_bottle.png
│   ├── professional_event_photo.png
│   └── linkedin_event_post.png
│
├── README.md
└── requirements.txt
```

---

## Requirements

```text
pandas
numpy
matplotlib
seaborn
scipy
```

---

## Author

**Ansh Wadhwa**

This project represents my effort to combine business analytics, customer interaction, and Python-based data analysis into one practical portfolio project.


