---
layout: post
title: Legend| OlapChart | Wpf | Syncfusion
description: Legend
platform: wpf
control: OlapChart
documentation: ug
---

# Legend

Legends are used to display the name of the data series. The ChartLegend can be added to an OlapChart by adding the ChartLegend of the Chart WPF, which is found under the Syncfusion.Windows.Chart namespace. The following code sample explain how to add a legend to an OlapChart:

{% tabs %}

{% highlight xaml %}

<syncfusion:OlapChart.Legend>
     <syncfusion:ChartLegend Background="Transparent"/>
</syncfusion:OlapChart.Legend>

{% endhighlight %}

{% highlight c# %}

this.olapChart.Legend = new ChartLegend();

{% endhighlight %}

{% highlight vbnet %}

Me.olapChart.Legend = New ChartLegend()

{% endhighlight %}

{% endtabs %}

![](Legend_images/Legend_img1.png)

## Show/Hide Legend

The ChartLegend has a **Visibility** property using which you can show or hide the ChartLegend in an OlapChart. The following code sample show how you can collapse the visibility of the ChartLegend:

{% tabs %}

{% highlight xaml %}

<syncfusion:OlapChart.Legend>
     <syncfusion:ChartLegend Visibility="Collapsed" />
</syncfusion:OlapChart.Legend>

{% endhighlight %}
 
{% highlight c# %}

this.olapChart.Legend.Visibility = System.Windows.Visibility.Collapsed;

{% endhighlight %}

{% highlight vbnet %}

Me.olapChart.Legend.Visibility = System.Windows.Visibility.Collapsed

{% endhighlight %}

{% endtabs %}

![](Legend_images/Legend_img2.png)

## Visibility Customization

The visibility of the legend check box can be toggled by using the *CheckBoxVisibility* property in the ChartLegend. The following code sample shows how to toggle the visibility of the check box in the legend of an OlapChart:

{% tabs %}

{% highlight xaml %}

<syncfusion:OlapChart.Legend>
     <syncfusion:ChartLegend CheckBoxVisibility="Collapsed" />
</syncfusion:OlapChart.Legend>

{% endhighlight %}

{% highlight c# %}

this.olapChart.Legend.CheckBoxVisibility = System.Windows.Visibility.Collapsed;

{% endhighlight %}

{% highlight vbnet %}

Me.olapChart.Legend.CheckBoxVisibility = System.Windows.Visibility.Collapsed

{% endhighlight %}

{% endtabs %}

The visibility of the legend icon can be toggled by using the *IconVisibility* property in the ChartLegend. The following code sample shows how to toggle the visibility of the icons in an OlapChart legend:

{% tabs %}

{% highlight xaml %}
    
<syncfusion:OlapChart.Legend>
     <syncfusion:ChartLegend IconVisibility="Collapsed" />
</syncfusion:OlapChart.Legend>

{% endhighlight %}

{% highlight c# %}

this.olapChart.Legend.IconVisibility = System.Windows.Visibility.Collapsed;

{% endhighlight %}

{% highlight vbnet %}

Me.olapChart.Legend.IconVisibility = System.Windows.Visibility.Collapsed

{% endhighlight %}

{% endtabs %}

## Dock Position

ChartLegend contains an enum property called ChartDock, which has the following values **Floating**, **Right**, **Left**, **Top** and **Bottom**. You can choose the required docking position to dock the legend. The following code sample explain how to set the docking position for an OlapChart legend: 

{% tabs %}

{% highlight c# %}

ChartDockPanel.SetDock(this.olapChart.Legend, ChartDock.Right);

{% endhighlight %}

{% highlight vbnet %}

ChartDockPanel.SetDock(Me.olapChart.Legend, ChartDock.Right)

{% endhighlight %}

{% endtabs %}

## Row/Column Setting

You can use the **RowsCount** and **ColumnsCount** property to create the rows or the columns of an OlapChart legend. The **RowsCount** and **ColumnsCount** will internally be used to create a Grid layout control to place the legends. The following code sample shows how to set the number of rows or columns in an legend:

{% tabs %}

{% highlight xaml %}

<syncfusion:OlapChart.Legend>
     <syncfusion:ChartLegend Background="Transparent" 
          RowsCount="2" ColumnsCount="2" />
</syncfusion:OlapChart.Legend>

{% endhighlight %}

{% highlight c# %}

this.olapChart.Legend.RowsCount = 2;
this.olapChart.Legend.ColumnsCount = 2;

{% endhighlight %}

{% highlight vbnet %}

Me.olapChart.Legend.RowsCount = 2
Me.olapChart.Legend.ColumnsCount = 2

{% endhighlight %}

{% endtabs %}

N> The **RowsCount** and **ColumnsCount** are used to create the rows and the columns in the Grid layout control, which is used to place the legends. If you give extra row or column count than the legend availability then it will display empty spaces to fill the structure of the grid. The following illustration explains this in detail.

The following chart has only one legend, but we have set RowsCount = 2 and ColumnsCount = 2. Therefore, the resultant legend will appear as follows: 

**Legend with RowsCount=2, ColumnsCount=2 and ChartDock.Top**
![](Legend_images/Legend_img3.png)
     
**Legend with RowsCount=2, ColumnsCount=2 and ChartDock.Right**
![](Legend_images/Legend_img4.png)
   
**Legend with RowsCount=2, ColumnsCount=2 and ChartDock.Left**
![](Legend_images/Legend_img5.png)
 
**Legend with RowsCount=2, ColumnsCount=2 and ChartDock.Bottom**
![](Legend_images/Legend_img6.png)
   
