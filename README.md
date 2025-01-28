# Dashboard--Sales-performances-
# Source 
[Superstore Dataset](https://www.kaggle.com/datasets/vivek468/superstore-dataset-final/data)
# Metadata
Row ID => Unique ID for each row.
Order ID => Unique Order ID for each Customer.
Order Date => Order Date of the product.
Ship Date => Shipping Date of the Product.
Ship Mode=> Shipping Mode specified by the Customer.
Customer ID => Unique ID to identify each Customer.
Customer Name => Name of the Customer.
Segment => The segment where the Customer belongs.
Country => Country of residence of the Customer.
City => City of residence of of the Customer.
State => State of residence of the Customer.
Postal Code => Postal Code of every Customer.
Region => Region where the Customer belong.
Product ID => Unique ID of the Product.
Category => Category of the product ordered.
Sub-Category => Sub-Category of the product ordered.
Product Name => Name of the Product
Sales => Sales of the Product.
Quantity => Quantity of the Product.
Discount => Discount provided.
Profit => Profit/Loss incurred.

# 1 Cleaning data
- Remove duplicates: No duplicate
- No missing data
Check to see if there are duplicates 
## Format standardisation
Remove extra space use of macro
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
1. Measures of Central Tendency
Mean (Average):

Sales: 113,227.11
Quantity: 3.79
Discount: 1.75
Profit: 180,095.71
Interpretation: On average, each sale generates $113,227.11 in revenue, involves 3.79 items, has a discount of 1.75%, and results in a profit of $180,095.71.
Median:

Sales: 11,088
Quantity: 3
Discount: 2
Profit: 36,309
Interpretation: The median values indicate that half of the sales are below $11,088, involve 3 items, have a discount of 2%, and result in a profit below $36,309.
Mode:

Sales: 1,296
Quantity: 3
Discount: 0
Profit: 0
Interpretation: The most frequent sales amount is $1,296, with 3 items, no discount, and no profit.
2. Measures of Dispersion
Minimum and Maximum:

Sales: Min = 3, Max = 23,962,656
Quantity: Min = 1, Max = 14
Discount: Min = 0, Max = 45
Profit: Min = -$383,999.04, Max = $671,998.08
Interpretation: The range of sales is from $3 to $23,962,656, quantities range from 1 to 14 items, discounts range from 0% to 45%, and profits range from -$383,999.04 to $671,998.08.
Range:

Sales: 23,962,653
Quantity: 13
Discount: 45
Profit: 1,055,997.12
Interpretation: The range shows the spread between the minimum and maximum values for each metric.
Variance:

Sales: 2.68941E+11 (total dataset), 2.68968E+11 (sample)
Quantity: 4.950617729 (total dataset), 4.951113138 (sample)
Discount: 9.727277231 (total dataset), 9.72825064 (sample)
Profit: 2.96833E+12 (total dataset), 2.96863E+12 (sample)
Interpretation: Variance measures the spread of the data points from the mean. Higher variance indicates more spread.
Standard Deviation:

Sales: 518,621.16
Quantity: 2.23
Discount: 3.12
Profit: 1,722,970.73
Interpretation: Standard deviation provides a measure of the average distance of each data point from the mean. Higher values indicate more variability.
3. Measures of Shape
Skewness:

Sales: 19.35
Quantity: 1.28
Discount: 6.20
Profit: 10.15
Interpretation: Positive skewness indicates that the data is skewed to the right, with a long tail on the right side.
Kurtosis:

Sales: 615.27
Quantity: 1.99
Discount: 64.23
Profit: 473.39
Interpretation: High kurtosis indicates that the data has heavy tails or outliers.
4. Other Statistics
Count:

Sales: 9,994
Quantity: 9,994
Discount: 9,994
Profit: 9,994
Interpretation: There are 9,994 entries in the dataset for each metric.
Sum:

Sales: 1,131,591,720.00
Quantity: 37,873.00
Discount: 17,536.00
Profit: 1,799,876,538.00
Interpretation: The total sales amount is $1,131,591,720.00, with a total quantity of 37,873 items, total discounts of 17,536%, and total profit of $1,799,876,538.00.
