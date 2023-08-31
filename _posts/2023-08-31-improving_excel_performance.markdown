---
layout: post
title:  "Improving Excel Performance"
date:   2023-08-31 13:36:00 -0500
categories: technology blog
---

See the end of the page if you want the "blog" part. I will typically list methods here from most impactful to least impactful, considering both performance and the end result of your spreadsheet.

# Performance (CPU and RAM)

## Consolidate Pivot Tables
If two tables will reference the same data, copy the initial pivot table instead of creating a new one. This allows the tables to share a Pivot Cache.

This macro will de-duplcate exisiting pivot tables. Be sure to create a backup. Credit to [https://www.contextures.com/xlpivot11.html](https://www.contextures.com/xlpivot11.html).

```
Sub CheckCaches()
' Developed by Contextures Inc.
' www.contextures.com
Dim pc As PivotCache
Dim wsList As Worksheet
Dim lRow As Long
Dim lRowPC As Long
Dim pt As PivotTable
Dim ws As Worksheet
Dim lStart As Long
lStart = 2
lRow = lStart

Set wsList = Worksheets.Add
For Each pc In ActiveWorkbook.PivotCaches
  wsList.Cells(lRow, 1).Value = pc.Index
  wsList.Cells(lRow, 2).Value = pc.SourceData
  wsList.Cells(lRow, 3).FormulaR1C1 = _
    "=INDEX(R1C[-2]:R[-1]C[-2],MATCH(RC[-1],R1C[-1]:R[-1]C[-1],0))"
  lRow = lRow + 1
Next pc

For lRowPC = lRow - 1 To lStart Step -1
  With wsList.Cells(lRowPC, 3)
    If IsNumeric(.Value) Then
      For Each ws In ActiveWorkbook.Worksheets
      Debug.Print ws.Name
        For Each pt In ws.PivotTables
        Debug.Print .Offset(0, -2).Value
          If pt.CacheIndex = .Offset(0, -2).Value Then
            pt.CacheIndex = .Value
          End If
        Next pt
      Next ws
    End If
  End With
Next lRowPC

'uncomment lines below to delete the temp worksheet
'Application.DisplayAlerts = False
'wsList.Delete

exitHandler:
Application.DisplayAlerts = True
Exit Sub

errHandler:
MsgBox "Could not change all pivot caches"
Resume exitHandler

End Sub
```

## Seperate Instances
**Benefit**: Opening workbooks in separate instances can bypass memory limits and prevent everything from crashing if a single sheet does.

**Drawback**: You cannot use certain "Paste Special" features between workbooks (Formulas, Values, Formats, Comments).

The most reliable way is to run the command `Excel.exe /x`. [Other methods](https://exceloffthegrid.com/how-to-open-multiple-instances-of-excel/) typically involve holding "Alt" while opening Excel.

## Remove Cell Formatting
 * Do not format whole columns or rows. [The Cell Formatting Cleaning Tool](https://support.microsoft.com/en-us/office/clean-excess-cell-formatting-on-a-worksheet-e744c248-6925-4e77-9d49-4874f7474738?ui=en-us&rs=en-gb&ad=gb) can remove extra formatting.
 * Remove unnecessary conditional formatting.

## Replace Inefficient Formulas
 * Avoid functions like `LOOKUP, INDIRECT, OFFSETS, INDEX, MATCH`.
 * Instead of referencing entire rows or columns, limit references to set ranges.
 * Avoid using "Defined Names" for ranges.
 * Avoid repeating volatile functions like `TODAY` and `NOW`. Instead, calculate the value once and reference that cell.

## Little Things
 * Limit the number of Macros, Charts, and Shapes used.
 * Disable unnecessary COM add-ins.
 * Disable hardware graphics acceleration.
 * Remove unused custom styles.

# File Size Management

## Save as a .xlsb file.
**Benefit**: Significant file size reduction.

**Drawback**: Other applications may not be able to open the file

## Do not save Pivot Table Source Data
**Benefit**: Decent file size reduction.

**Drawback**: Pivot Tables need to be refreshed before they can be used.

This needs to be applied to all pivot tables in a workbook individually. The following macro can apply this to all existing Pivot Tables. Credit to [https://excelribbon.tips.net/T008669_Reducing_File_Sizes_for_Workbooks_with_PivotTables.html](https://excelribbon.tips.net/T008669_Reducing_File_Sizes_for_Workbooks_with_PivotTables.html).

```
Sub PTReduceSize()
    Dim wks As Worksheet
    Dim PT As PivotTable

    For Each wks In ActiveWorkbook.Worksheets
        For Each PT In wks.PivotTables
            PT.RefreshTable
            PT.CacheIndex = 1
            PT.SaveData = False
        Next
    Next
End Sub
```

# Sources
[https://learn.microsoft.com/en-us/office/troubleshoot/excel/clean-workbook-less-memory](https://learn.microsoft.com/en-us/office/troubleshoot/excel/clean-workbook-less-memory)  
[https://learn.microsoft.com/en-GB/office/troubleshoot/excel/available-resources-errors](https://learn.microsoft.com/en-GB/office/troubleshoot/excel/available-resources-errors)  
[https://learn.microsoft.com/en-us/archive/blogs/the_microsoft_excel_support_team_blog/top-10-list-of-performance-issues-in-excel-workbooks](https://learn.microsoft.com/en-us/archive/blogs/the_microsoft_excel_support_team_blog/top-10-list-of-performance-issues-in-excel-workbooks)  
[https://learn.microsoft.com/en-US/office/troubleshoot/excel/memory-usage-32-bit-edition-of-excel](https://learn.microsoft.com/en-US/office/troubleshoot/excel/memory-usage-32-bit-edition-of-excel)  
[https://exceloffthegrid.com/how-to-open-multiple-instances-of-excel/](https://exceloffthegrid.com/how-to-open-multiple-instances-of-excel/)  
[https://www.contextures.com/xlpivot11.html#removedups](https://www.contextures.com/xlpivot11.html#removedups)  
[https://support.microsoft.com/en-us/office/clean-excess-cell-formatting-on-a-worksheet-e744c248-6925-4e77-9d49-4874f7474738?ui=en-us&rs=en-gb&ad=gb](https://support.microsoft.com/en-us/office/clean-excess-cell-formatting-on-a-worksheet-e744c248-6925-4e77-9d49-4874f7474738?ui=en-us&rs=en-gb&ad=gb)  
[https://support.microsoft.com/en-us/office/reduce-the-file-size-of-your-excel-spreadsheets-c4f69e3a-8eea-4e9d-8ded-0ac301192bf9#ID0EBDF=Office_2013\_-_2016](https://support.microsoft.com/en-us/office/reduce-the-file-size-of-your-excel-spreadsheets-c4f69e3a-8eea-4e9d-8ded-0ac301192bf9#ID0EBDF=Office_2013_-_2016)  

# The Blog Part
In my role as a Workforce Management Analyst, we use Excel a lot. Sure, there are probably better tools out there for the data that we handle. But those tools have learning curves, and Excel works. See [https://xkcd.com/2180/](https://xkcd.com/2180/). My team was regularly maxing out the RAM that 32 bit Excel could handle, and our IT department refused to install the 64 bit version (for some unexplained reason). We were constantly running up against memory errors, crashing systems, and various errors. To combat this, we would start copying data out of one sheet and into another one. Now we are now bloating all of our sheets and causing even more memory issues if we try to open multiple at once.

I initially put together this document in the team's shared OneNote to help everyone manage their Excel experience. But I know that I'll use this information later, and what is a blog for if not this? It's not like I'm using it anyways.
