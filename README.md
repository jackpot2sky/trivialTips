# trivialTips
- automatically adjust column widths in excel
  - right click on the sheet --> view code --> select worksheet from the dropdown
  - paste this code before the `End Sub` line: `Target.EntireColumn.AutoFit`
    - ```
      Private Sub Worksheet_Change(ByVal Target As Range)
        Cells.EntireColumn.AutoFit
      End Sub
      ```
