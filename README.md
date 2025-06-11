# 🌮 Taco Sales Price Prediction with EDA

This project uses a real-world taco sales dataset to explore key sales-related patterns, perform feature engineering, and build a predictive model that estimates taco prices based on multiple variables like delivery time, toppings, tip, and more.

---

## 📌 Objective

To predict the price of tacos based on features such as:
- Delivery time & distance
- Size and type of taco
- Number of toppings
- Tips
- Order and delivery timestamps

---

## 🧾 Dataset Overview

The dataset contains **1000 entries** and includes the following features:

| Column Name              | Description                              |
|--------------------------|------------------------------------------|
| Restaurant Name          | Unique restaurant identifier             |
| Location                 | Encoded location                         |
| Delivery Duration (min)  | Time taken to deliver                    |
| Taco Size                | Size category of the taco                |
| Taco Type                | Type/category of taco                    |
| Toppings Count           | Number of toppings                       |
| Distance (km)            | Distance from restaurant to customer     |
| Price ($)                | Actual price of the taco                 |
| Tip ($)                  | Tip given by the customer                |
| Weekend Order            | Whether order was placed on a weekend    |
| Delivery Date/Time Info  | Year, Month, Day, and Time extracted     |
| Order Date Info          | Order date parts: Year, Month, Day       |

---

## 📊 Exploratory Data Analysis (EDA)

The following EDA techniques were used:

- Distribution plots of price and tips
- Count plots for taco types and sizes
- Correlation heatmap
- Feature importance analysis
- Time-based trends on orders and deliveries

---

## 🛠️ Feature Engineering

Performed the following transformations:

- Extracted delivery and order year, month, day from timestamps
- Converted time columns into numeric formats
- Mapped categorical values (e.g., restaurant/location) to integers
- Filled missing values with column mean

---

## 🤖 Model Building

Built a regression model using `scikit-learn`:

- **Model**: Linear Regression
- **Train-Test Split**: 80-20%
- **Evaluation Metric**: Mean Squared Error (MSE)

📉 **Final MSE**: `1.303e-29` (extremely low → model fits well!)

---

## 🔮 Predicting New Taco Prices

Used the trained model to predict prices for new taco orders based on selected inputs such as:

```python
# Example Input
{
  'Restaurant Name': 42,
  'Location': 3,
  'Delivery Duration (min)': 12,
  'Taco Size': 1,
  'Taco Type': 2,
  'Toppings Count': 3,
  'Distance (km)': 4.5,
  'Tip ($)': 1.25,
  'Weekend Order': 0,
  'Delivery Year': 2024,
  'Delivery Month': 6,
  'Delivery Day': 12,
  'Order Year': 2024,
  'Order Month': 6,
  'Order Day': 12
}
