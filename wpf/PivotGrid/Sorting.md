---
layout: post
title: Sorting | PivotGrid | Wpf | Syncfusion
description: sorting 
platform: wpf
control: PivotGrid
documentation: ug
---


# Sorting

Sorting data enables you to quickly visualize and understand your data better, organize and find the data that you want, and ultimately make more effective decisions. By default, PivotGrid will populate the data in ascending order. Sorting order can be changed using the Comparer field of PivotItem.

{% tabs %}
{% highlight C# %} 



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

{% endtabs %}