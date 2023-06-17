# trivialTips
- automatically adjust column widths in excel
  - right click on the sheet --> view code --> select worksheet from the dropdown
  - paste this code before the `End Sub` line:
    - ```
      Cells.EntireColumn.AutoFit
      ```
