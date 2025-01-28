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
Here are the tables in Markdown syntax:

### 1. Central Tendency

```markdown
| Statistic | Sales       | Quantity     | Discount     | Profit       |
|-----------|-------------|--------------|--------------|--------------|
| Mean      | 113,227.11  | 3.79         | 1.75         | 180,095.71   |
| Median    | 11,088      | 3            | 2            | 36,309       |
| Mode      | 1,296       | 3            | 0            | 0            |
```

### 2. Dispersion

```markdown
| Statistic                  | Sales       | Quantity     | Discount     | Profit       |
|----------------------------|-------------|--------------|--------------|--------------|
| Min                        | 3           | 1            | 0            | -383,999.04  |
| Max                        | 23,962,656  | 14           | 45           | 671,998.08   |
| Range                      | 23,962,653  | 13           | 45           | 1,055,997.12 |
| Variance (total dataset)   | 2.68941E+11 | 4.95         | 9.73         | 2.96833E+12  |
| Variance (sample)          | 2.68968E+11 | 4.95         | 9.73         | 2.96863E+12  |
| Standard Deviation         | 518,621.16  | 2.23         | 3.12         | 1,722,970.73 |
```

### 3. Measures of Shape

```markdown
| Statistic | Sales       | Quantity     | Discount     | Profit       |
|-----------|-------------|--------------|--------------|--------------|
| Skewness  | 19.35       | 1.28         | 6.20         | 10.15        |
| Kurtosis  | 615.27      | 1.99         | 64.23        | 473.39       |
```

### 4. Other

```markdown
| Statistic | Sales       | Quantity     | Discount     | Profit       |
|-----------|-------------|--------------|--------------|--------------|
| Count     | 9,994       | 9,994        | 9,994        | 9,994        |
| Sum       | 1,131,591,720.00 | 37,873.00 | 17,536.00   | 1,799,876,538.00 |
```

You can copy these tables directly into your Markdown file, and they will be properly formatted as tables. If you need any further assistance or additional analysis, feel free to ask!
