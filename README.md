# Dashboard--Sales-performances-
# Source 
[Superstore Dataset](https://www.kaggle.com/datasets/vivek468/superstore-dataset-final/data)
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
