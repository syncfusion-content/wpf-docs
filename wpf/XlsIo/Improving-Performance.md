---
layout: post
title: Improving Performance | XlsIO | WPF | Syncfusion
description: improving performance
platform: wpf
control: Xlsio
documentation: ug
---

# Improving Performance

Essential XlsIO can create large reports in a few seconds. 

Tips to improve the Performance

* Use default styles, to apply styles for a whole column instead of applying to each cell.
* Minimize AutoFit manipulations.
* Get UsedRange globally. It is recommended to get the UsedRange in loops as follows.



{% highlight C# %} 


int lastRow = sheet.UsedRange.LastRow

for(int i=0;i<lastRow;i++)

{

//Codes.

}



//Do not use the following.

for(int i = 0;i<sheet.UsedRange.LastRow;i++)

{

//codes.

}

 {% endhighlight %}

* Use IMigrantRange to optimize performance while dealing with large data.
* Use global styles, rather than using different cell styles for each cell/range.
* Use Begin and End call when more than one global style for a worksheet is used.
* Use Value and Value2 property only when the data type is unknown. Value/Value2 property checks the data type of the given string and so this consumes time.
* Files parsing can be optimized by setting IApplication.UseFastRecordParsing = false or true (true-fast mode, but less error checks and false-slower, but more reliable).
* To extract values little faster, use Unsafe code option of IApplication interface as follows.







application.DataProviderType = ExcelDataProviderType.Unsafe;



* Make use of GetText, SetText, GetNumber, and SetNumber methods from worksheet object that enable you to get/set values without range object.
* Set IWorkbook.DetectDateTimeInValue property to false with Value2 property, if you are sure that the given value is not of DateTime data type that improves time performance.
* Use of BeginUpdate and EndUpdate methods for large blocks of Data Validation greatly improve the performance.
* Use DataProvider.Unsafe option to increase performance while deleting large number of rows or columns. 
* Use CompressionLevel to reduce the size of the file. 



## Filling large data by using IMigrantRange

The IMigrantRange interface can be used to access and manipulate worksheet range. This is an optimal method of writing values with better memory performance. The following code example illustrates how the IMigrantRange is accessed.

{% tabs %}

{% highlight C# %} 


IMigrantRange migrantRange = workbook.Worksheets[0].MigrantRange; 

// Writes Data.
for (int row = 1; row <= rowCount; row++)
{
 for (int column = 1; column <= colCount; column++)
   {
// Writes values.
        migrantRange.ResetRowColumn(row, column);


//Sets Boolean value.
migrantRange.SetValue(true);


//Sets DateTime value.

        migrantRange.SetValue(DateTime.Now);


//Sets double value.

        migrantRange.SetValue(5.5);


//Sets int value.

        migrantRange.SetValue(5);


//Sets string value.

        migrantRange.SetValue("Syncfusion");
   }
}

 {% endhighlight %}

{% highlight vbnet %} 

'Writes Data.
Dim row As Integer 
Dim migrantRange As IMigrantRange = workbook.Worksheets(0).MigrantRange
For row = 1 To rowCount Step row + 1
    Dim column As Integer
    For column = 1 To colCount Step column + 1 
'Writes values.
         migrantRange.ResetRowColumn(row, column)

'Sets Boolean value.
         migrantRange.SetValue(true)

'Writes DateTimevalue.
                     migrantRange.SetValue(DateTime.Now)

'Writes double value.                     
migrantRange.SetValue(5.5)

'Writes int value.
                     migrantRange.SetValue(5)


'Writes string value.
                     migrantRange.SetValue("Syncfusion");
        Next
Next



{% endhighlight %} 

{% endtabs %}