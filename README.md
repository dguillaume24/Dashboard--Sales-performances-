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
