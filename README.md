# Dashboard--Sales-performances-

# 1 Cleaning data

### Finding null values
- No null values found : Using filtering options
- Finding missing data: using the  =COUNTBLANK() function, we get 0 blank cell.

### Remove duplicates and missing data
- No duplicate found
- No missing data
Check to see if there are duplicates

### Format standardisation

- Standardise names
- Remove all extra spaces
- Format: numbers, dates,...
- Additional spaces
- Changing column names
- Remove duplicates
# 2 Transformation
- Date format: dates are in the US format mm/dd/yyyy, they are changed in the format dd/mm/yyyy
- The profit column includes positive and negative profits. This column is split into two different columns: Profit and loss

# 3 EDA
## Statistics
### 1. Central Tendency

| Measure | SALES       | Quantity    | Discount    | Profit      |
|---------|-------------|-------------|-------------|-------------|
| Mean    | 229.8580008 | 3.789573744 | 0.156202722 | 28.65689631 |
| Median  | 54.49       | 3           | 0.2         | 8.6665      |
| Mode    | 12.96       | 3           | 0           | 0           |

Interpretation:

Mean: The average values for sales, quantity, discount, and profit. For example, the average sales amount is approximately 229.86.
Median: The middle value when the data is ordered. For instance, the median sales amount is 54.49, indicating that half of the sales are below this value and half are above.
Mode: The most frequently occurring value in the dataset. For example, the most common sales amount is 12.96.

### 2. Dispersion

| Measure                  | SALES       | Quantity    | Discount    | Profit      |
|--------------------------|-------------|-------------|-------------|-------------|
| MIN                      | 0.444       | 1           | 0           | -6599.978   |
| MAX                      | 22638.48    | 14          | 0.8         | 8399.976    |
| Range                    | 22638.036   | 13          | 0.8         | 14999.954   |
| Variance (total dataset) | 388395.5885 | 4.950617729 | 0.04261815  | 54872.30698 |
| Variance (sample)        | 388434.4553 | 4.951113138 | 0.042622415 | 54877.79806 |
| Standard deviation       | 623.2451005 | 2.225109691 | 0.206451968 | 234.2601077 |

Interpretation:

MIN and MAX: The smallest and largest values in the dataset. For example, the smallest sales amount is 0.444, and the largest is 22638.48.
Range: The difference between the maximum and minimum values. For instance, the range of sales is 22638.036.
Variance: A measure of how much the values in the dataset vary. Higher variance indicates more spread out data. For example, the variance in sales is 388395.5885.
Standard deviation: The square root of the variance, showing the average distance of each data point from the mean. For example, the standard deviation of sales is 623.2451005.

### 3. Measures of Shape

| Measure  | SALES       | Quantity    | Discount    | Profit      |
|----------|-------------|-------------|-------------|-------------|
| Skewness | 12.97275234 | 1.278544753 | 1.684294747 | 7.561431562 |
| Kurtosis | 305.3117532 | 1.991889366 | 2.409546123 | 397.1885146 |

Interpretation:

Skewness: Indicates the asymmetry of the data distribution. Positive skewness means the data is skewed to the right. For example, sales have a high positive skewness of 12.97275234, indicating a long right tail.
Kurtosis: Measures the "tailedness" of the data distribution. Higher kurtosis indicates more outliers. For example, sales have a very high kurtosis of 305.3117532, suggesting many extreme values.
Other

| Measure | SALES       | Quantity | Discount | Profit      |
|---------|-------------|----------|----------|-------------|
| Count   | 9994        | 9994     | 9994     | 9994        |
| SUM     | 2297200.86  | 37873    | 1561.09  | 286397.0217 |

Interpretation:

Count: The number of observations in the dataset. For example, there are 9994 records for sales, quantity, discount, and profit.
SUM: The total sum of all values in the dataset. For example, the total sales amount is 2297200.86.

### 4. Outliers
Identify any outliers in sales and profits.
Any value outside Q1 - 1.5*IQR or Q3 + 1.5*IQR is an outlier.
The Interquartile Range (IQR) is a common method for finding outliers. Outliers are values that fall below Q1 - 1.5*IQR or above Q3 + 1.5*IQR.

Steps to Identify Outliers in Excel:
Calculate Q1 (25th percentile) and Q3 (75th percentile):
Use =QUARTILE(range,1) for Q1
Use =QUARTILE(range,3) for Q3
Calculate IQR:
=Q3 - Q1
Calculate Lower and Upper Boundaries:
Lower Bound = Q1 - 1.5 * IQR
Upper Bound = Q3 + 1.5 * IQR

|            | SALES   | Quantity | Discount | Profit |
|------------|---------|---------|---------|---------|
| Q1         | 17,28   | 2       | 0       | 1,72875  |
| Q2         | 54,49   | 3       | 0,2     | 8,6665   |
| Q3         | 209,94  | 5       | 0,2     | 29,364   |
| Q3-Q1      | 192,66  | 3       | 0,2     | 27,63525 |
| lower_bound| -271,71 | -2,5    | -0,3    | -39,724125 |
| upper_bound| 498,93  | 9,5     | 0,5     | 70,816875 |

## Exploration

### 1. Sales and Profit Overview
Sales and Profit Trends Over Time → Identify seasonal patterns and growth trends.
Sales and Profit by Category, Subcategory, and Product → Find top-selling and least-selling items.
Sales and Profit by Region, State, and City → Discover regional differences.
Profit Margins Across Categories and Subcategories → Identify high-margin vs. low-margin products.








# 1. Sales and Profit Overview
Sales and Profit Trends Over Time → Identify seasonal patterns and growth trends.
Sales and Profit by Category, Subcategory, and Product → Find top-selling and least-selling items.
Sales and Profit by Region, State, and City → Discover regional differences.
Profit Margins Across Categories and Subcategories → Identify high-margin vs. low-margin products.






1. Sales and profits
- How do have they evolved over time
- What is the distribution geographically
- What are the best selling categories, subcategories, products
- Display for each region, state, city the best selling categories, subcategories, products
- Display the worst selling categories, subcategories, products
- Display for each region, state, city the worst selling categories, subcategories, products
- Display the sales per client, make a top ten
- Show distribution of best customers geographically

2. Ordering and Shipping
- Look at seasonality of shipping and ordering
- difference in shipping and ordering dates
- Distribution geographically
- Most common mode of shipping
- Most common mode of shipping geographicaly (region, state, city)
- Make an analysis on ordering and shipping over time geographically
- Most common shipping mode for categories, subcategories and products
- Relationships between sales/profit and shipping mode
- Relationship between sales/profit  and ordering and shipping dates
3. Geographical analysis
- Sales
- Profit
- Shiping
- Order dates
- Shipping dates
- Customers
- Categorie, subcategories, products









# Source 
Kaggle dataset : [Superstore Dataset](https://www.kaggle.com/datasets/vivek468/superstore-dataset-final/data)

| Field          | Description                           |
|----------------|---------------------------------------|
| **Row ID**     | Unique ID for each row.               |
| **Order ID**   | Unique Order ID for each Customer.    |
| **Order Date** | Order Date of the product.            |
| **Ship Date**  | Shipping Date of the Product.         |
| **Ship Mode**  | Shipping Mode specified by the Customer. |
| **Customer ID**| Unique ID to identify each Customer.  |
| **Customer Name** | Name of the Customer.              |
| **Segment**    | The segment where the Customer belongs. |
| **Country**    | Country of residence of the Customer. |
| **City**       | City of residence of the Customer.    |
| **State**      | State of residence of the Customer.   |
| **Postal Code**| Postal Code of every Customer.        |
| **Region**     | Region where the Customer belongs.    |
| **Product ID** | Unique ID of the Product.             |
| **Category**   | Category of the product ordered.      |
| **Sub-Category** | Sub-Category of the product ordered. |
| **Product Name** | Name of the Product.                |
| **Sales**      | Sales of the Product.                 |
| **Quantity**   | Quantity of the Product.              |
| **Discount**   | Discount provided.                    |
| **Profit**     | Profit/Loss incurred.                 |



