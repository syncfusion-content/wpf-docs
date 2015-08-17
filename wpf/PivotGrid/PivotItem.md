---
layout: post
title: PivotItem
description: pivotitem
platform: wpf
control: PivotGrid
documentation: ug
---

## PivotItem

A pivot item is an item in a PivotTable field. PivotItem provides the information needed to define a pivot item for either a row or column 
pivot. It consists of the following fields.

_Property Table_

<table>
<tr>
<th>
Property Name</th><th>
Description</th><th>
Type</th><th>
Value it Accepts</th><th>
Reference link</th></tr>
<tr>
<td>
Comparer</td><td>
Gets or sets the IComparer object used for sorting. If this value is null, then sorting will be performed under the assumption that this 
field is IComparable.</td><td>
IComparer</td><td>
-</td><td>
-</td></tr>
<tr>
<td>
FieldHeader</td><td>
Gets or sets the title you want to see in the header for this pivot item.</td><td>
string</td><td>
-</td><td>
-</td></tr>
<tr>
<td>
FieldMappingName</td><td>
Gets or sets the property's mapping name.</td><td>
string</td><td>
-</td><td>
-</td></tr>
<tr>
<td>
Format</td><td>
Gets or sets the format item for the specified field.</td><td>
string</td><td>
-</td><td>
-</td></tr>
<tr>
<td>
TotalHeader</td><td>
Gets or sets the string you want appended to the pivot item's summary cells.</td><td>
string</td><td>
-</td><td>
-</td></tr>
</table> 


### Defining PivotItem in XAML and Code-Behind

PivotItem can be defined in XAML or in code-behind.

{% highlight xml %} 

 [XAML]



  <!--Defining Pivot Rows-->

  <syncfusion:PivotGridControl.PivotRows>

     <!--Adding PivotItem to PivotRows-->

     <syncfusion:PivotItem FieldMappingName="Product" FieldHeader="Product" 

     TotalHeader="Total"/>                    

  </syncfusion:PivotGridControl.PivotRows> 

{% endhighlight %}

or

{% highlight C# %}  

[C#]



// Defining PivotItem

PivotItem m_PivotItem = new PivotItem() { FieldHeader="Product", FieldMappingName ="Product", TotalHeader ="Total" };            

// Adding PivotItem to PivotRows

this.PivotGridControl1.PivotRows.Add(m_PivotItem);

{% endhighlight %} 



{% highlight vbnet %} 

[VB]



' Defining PivotItem

Dim m_PivotItem As PivotItem = New PivotItem() With {.FieldHeader="Product", .FieldMappingName ="Product", .TotalHeader ="Total"}

' Adding PivotItem to PivotRows

Me.PivotGridControl1.PivotRows.Add(m_PivotItem)

{% endhighlight %} 


### Sorting Using PivotItem

By default, PivotGrid will sort data in ascending order. The sorting order can be changed using the Comparer field of PivotItem.

{% highlight C# %}

[C#]

// Adding Pivot Rows to Grid with FieldMappingName, TotalHeader and Comparer

this.PivotGridControl1.PivotRows.Add(new PivotItem { FieldMappingName = "Product", TotalHeader = "Total", Comparer = new ReverseOrderComparer() });



/// <summary>

/// Reverse Order Comparer for Descending sort order

/// </summary>

public class ReverseOrderComparer : IComparer

{

   #region IComparer Members



   public int Compare(object x, object y)

   {

      if (x == null && y == null)

        return 0;

      else if (y == null)

        return 1;

      else if (x == null)

        return -1;

      else

        return -x.ToString().CompareTo(y.ToString());

   }



   #endregion  

}

  {% endhighlight %} 



{% highlight vbnet %} 

[VB]

' Adding Pivot Rows to Grid with FieldMappingName, TotalHeader and Comparer

Me.PivotGridControl1.PivotRows.Add(New PivotItem With {.FieldMappingName = "Product", .TotalHeader = "Total", .Comparer = New ReverseOrderComparer()})



''' <summary>

''' Reverse Order Comparer for Descending sort order

''' </summary>

public class ReverseOrderComparer : IComparer

'   #Region "IComparer Members"



   public Integer Compare(Object x, Object y)

If x Is Nothing AndAlso y Is Nothing Then

Return 0

ElseIf y Is Nothing Then

Return 1

ElseIf x Is Nothing Then

Return -1

Else

Return -x.ToString().CompareTo(y.ToString())

End If



'   #End Region  

{% endhighlight %} 


