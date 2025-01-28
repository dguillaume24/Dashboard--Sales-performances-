# Dashboard--Sales-performances-
# Source 
[Superstore Dataset](https://www.kaggle.com/datasets/vivek468/superstore-dataset-final/data)
# Metadata
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

# 1 Cleaning data
- Remove duplicates: No duplicate
- No missing data
Check to see if there are duplicates 
## Format standardisation
```vba
Sub SupprimerEspaces()
    Dim ws As Worksheet
    Dim cell As Range
    Dim cellValue As String
    
    ' Boucle à travers chaque feuille de calcul
    For Each ws In ThisWorkbook.Worksheets
        ' Boucle à travers chaque cellule utilisée dans la feuille de calcul
        For Each cell In ws.UsedRange
            If cell.HasFormula = False Then
                cellValue = cell.Value
                ' Supprime les espaces en début et fin de texte, et réduit les espaces multiples à un seul
                cell.Value = WorksheetFunction.Trim(cellValue)
            End If
        Next cell
    Next ws
End Sub

Standardise names
Format all the number to numbers
Additional spaces
Changing column names
Remove duplicates
# 2 EDA
### 1. Central Tendency


| Statistic | Sales       | Quantity     | Discount     | Profit       |
|-----------|-------------|--------------|--------------|--------------|
| Mean      | 113,227.11  | 3.79         | 1.75         | 180,095.71   |
| Median    | 11,088      | 3            | 2            | 36,309       |
| Mode      | 1,296       | 3            | 0            | 0            |

**Mean (Average):**
On average, each sale generates $113,227.11 in revenue, involves 3.79 items, has a discount of 1.75%, and results in a profit of $180,095.71.\
**Median**
The median values indicate that half of the sales are below $11,088, involve 3 items, have a discount of 2%, and result in a profit below $36,309.\
**Mode:**
The most frequent sales amount is $1,296, with 3 items, no discount, and no profit.
### 2. Dispersion

| Statistic                  | Sales       | Quantity     | Discount     | Profit       |
|----------------------------|-------------|--------------|--------------|--------------|
| Min                        | 3           | 1            | 0            | -383,999.04  |
| Max                        | 23,962,656  | 14           | 45           | 671,998.08   |
| Range                      | 23,962,653  | 13           | 45           | 1,055,997.12 |
| Variance (total dataset)   | 2.68941E+11 | 4.95         | 9.73         | 2.96833E+12  |
| Variance (sample)          | 2.68968E+11 | 4.95         | 9.73         | 2.96863E+12  |
| Standard Deviation         | 518,621.16  | 2.23         | 3.12         | 1,722,970.73 |

**Minimum and Maximum:**

Interpretation: The range of sales is from $3 to $23,962,656, quantities range from 1 to 14 items, discounts range from 0% to 45%, and profits range from -$383,999.04 to $671,998.08.\
**Range:**
Interpretation: The range shows the spread between the minimum and maximum values for each metric.\
**Variance:**
Interpretation: Variance measures the spread of the data points from the mean. Higher variance indicates more spread.\
**Standard Deviation:**
Interpretation: Standard deviation provides a measure of the average distance of each data point from the mean. Higher values indicate more variability.

### 3. Measures of Shape

| Statistic | Sales       | Quantity     | Discount     | Profit       |
|-----------|-------------|--------------|--------------|--------------|
| Skewness  | 19.35       | 1.28         | 6.20         | 10.15        |
| Kurtosis  | 615.27      | 1.99         | 64.23        | 473.39       |

**Skewness:**
Interpretation: Positive skewness indicates that the data is skewed to the right, with a long tail on the right side.\
**Kurtosis:**
Interpretation: High kurtosis indicates that the data has heavy tails or outliers.
### 4. Other

| Statistic | Sales       | Quantity     | Discount     | Profit       |
|-----------|-------------|--------------|--------------|--------------|
| Count     | 9,994       | 9,994        | 9,994        | 9,994        |
| Sum       | 1,131,591,720.00 | 37,873.00 | 17,536.00   | 1,799,876,538.00 |
