# Dashboard--Sales-performances-
# Source 
[Superstore Dataset](https://www.kaggle.com/datasets/vivek468/superstore-dataset-final/data)
# Metadata

<details>
<summary>Metadata</summary>
    
- **Row ID**: Unique ID for each row.
- **Order ID**: Unique Order ID for each Customer.
- **Order Date**: Order Date of the product.
- **Ship Date**: Shipping Date of the Product.
- **Ship Mode**: Shipping Mode specified by the Customer.
- **Customer ID**: Unique ID to identify each Customer.
- **Customer Name**: Name of the Customer.
- **Segment**: The segment where the Customer belongs.
- **Country**: Country of residence of the Customer.
- **City**: City of residence of the Customer.
- **State**: State of residence of the Customer.
- **Postal Code**: Postal Code of every Customer.
- **Region**: Region where the Customer belongs.
- **Product ID**: Unique ID of the Product.
- **Category**: Category of the product ordered.
- **Sub-Category**: Sub-Category of the product ordered.
- **Product Name**: Name of the Product.
- **Sales**: Sales of the Product.
- **Quantity**: Quantity of the Product.
- **Discount**: Discount provided.
- **Profit**: Profit/Loss incurred.

</details>

# 1 Cleaning data
## Finding null values
- No null values found
## Remove duplicates and missing data
- No duplicate found
- No missing data
Check to see if there are duplicates 
## Format standardisation
```vba
Sub SupprimerEspaces()
    Dim ws As Worksheet\
    Dim cell As Range\
    Dim cellValue As String\
    
    ' Boucle à travers chaque feuille de calcul\
    For Each ws In ThisWorkbook.Worksheets\
        ' Boucle à travers chaque cellule utilisée dans la feuille de calcul\
        For Each cell In ws.UsedRange\
            If cell.HasFormula = False Then\
                cellValue = cell.Value\
                ' Supprime les espaces en début et fin de texte, et réduit les espaces multiples à un seul\
                cell.Value = WorksheetFunction.Trim(cellValue)\
            End If\
        Next cell\
    Next ws\
End Sub

Standardise names
Format all the number to numbers
Additional spaces
Changing column names
Remove duplicates
# 2 Transformation
The profit column includes positive and négative profits. This column is split into two different columns: Profit and loss
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
Dispersion

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
Measures of Shape

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


## Exploration
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
- Distribution geographically
- Most common mode of shipping
- Most common mode of shipping geographicaly (region, state, city)
- Make an analysis on ordering and shipping over time geographically
- Most common shipping mode for categories, subcategories and products
- Relationships between sales/profit and shipping mode
- Relationship between sales/profit  and ordering and shipping dates
- 



