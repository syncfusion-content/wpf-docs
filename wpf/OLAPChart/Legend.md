---
layout: post
title: Legend| OLAP Chart | Wpf | Syncfusion
description: Legend
platform: wpf
control: OLAP Chart
documentation: ug
---

# Legend

Legends are used to display the name of the data series.

The following topics explain this in detail:



## How to add legend to the OlapChart

The ChartLegend can be added to an OlapChart by adding the ChartLegend of the Essential Chart WPF, which is found under the Syncfusion.Windows.Chart namespace. The following code snippets explain how to add a legend to an OlapChart:
{% tabs %}
  {% highlight xml %}

   

       <syncfusion:OlapChart.Legend>
            <baseChart:ChartLegend Background="Transparent"/>
       </syncfusion:OlapChart.Legend>

    {% endhighlight %}



  {% highlight c# %}



       this.olapChart.Legend = new ChartLegend();

    {% endhighlight %}


  {% highlight vbnet %}

   



      Me.olapChart.Legend = New ChartLegend()

    {% endhighlight %}
{% endtabs %}


## How to Show/Hide chart legend?

The ChartLegend has a visibility property using which you can show or hide the ChartLegend in an OlapChart. The following code snippets show how you can collapse the visibility of the ChartLegend:
{% tabs %}
  {% highlight xml %}

    



<syncfusion:OlapChart.Legend>

        <baseChart:ChartLegend Visibility="Collapsed" />
</syncfusion:OlapChart.Legend>

    {% endhighlight %}
 


  {% highlight c# %}

 



this.olapChart.Legend.Visibility = System.Windows.Visibility.Collapsed;

    {% endhighlight %}







  {% highlight vbnet %}

   



Me.olapChart.Legend.Visibility = System.Windows.Visibility.Collapsed

    {% endhighlight %}
{% endtabs %}



## How to toggle the visibility of the legend check box?

The visibility of the legend check box can be toggled by using the CheckBoxVisibility property in the ChartLegend. The following code snippet shows how to toggle the visibility of the check box in the legend of an OlapChart:
{% tabs %}
  {% highlight xml %}

    



<syncfusion:OlapChart.Legend>
    <baseChart:ChartLegend CheckBoxVisibility="Collapsed" />
</syncfusion:OlapChart.Legend>

    {% endhighlight %}




  {% highlight c# %}

    



this.olapChart.Legend.CheckBoxVisibility = System.Windows.Visibility.Collapsed;

    {% endhighlight %}





  {% highlight vbnet %}

    



Me.olapChart.Legend.CheckBoxVisibility = System.Windows.Visibility.Collapsed

    {% endhighlight %}

{% endtabs %}



## How to toggle the visibility of the legend icon?

The visibility of the legend icon can be toggled by using the IconVisibility property in the ChartLegend. The following code snippet shows how to toggle the visibility of the icons in an OlapChart legend:

  {% highlight xml %}

    


<syncfusion:OlapChart.Legend>
    <baseChart:ChartLegend IconVisibility="Collapsed" />
</syncfusion:OlapChart.Legend>

    {% endhighlight %}




  {% highlight c# %}

   



this.olapChart.Legend.IconVisibility = System.Windows.Visibility.Collapsed;

    {% endhighlight %}





  {% highlight vbnet %}

   



Me.olapChart.Legend.IconVisibility = System.Windows.Visibility.Collapsed

    {% endhighlight %}





## How to set the dock position of the legend?

ChartLegend contains an enum property called ChartDock, which has the following values Floating, Right, Left, Top, and Bottom. You can choose the required docking position to dock the chart. The following code snippets explain how to set the docking position for an OlapChart legend: 

  {% highlight c# %}

    



ChartDockPanel.SetDock(this.olapChart.Legend, ChartDock.Right);

    {% endhighlight %}




  {% highlight vbnet %}

    



ChartDockPanel.SetDock(Me.olapChart.Legend, ChartDock.Right)

    {% endhighlight %}





## How to set the rows/columns in a legend?

You can use the RowsCount and ColumnsCount property to create the rows or the columns of an OlapChart legend. The RowsCount and ColumnsCount will internally be used to create a Grid layout control to place the legends. The following code snippet shows how to set the number of rows or columns in an OlapLegend:

  {% highlight xml %}

    



<syncfusion:OlapChart.Legend>
    <baseChart:ChartLegend Background="Transparent" 

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



N> The RowsCount and the ColumnsCount is used to create the rows and the columns in the Grid layout control, which is used to place the legends. If you give extra row or column count than the legend availability then it will display empty spaces to fill the structure of the grid. The following illustration explains this in detail.

The following chart has only one legend, but we have set RowsCount = 2 and ColumnsCount = 2. Therefore, the resultant legend will appear as follows: 

![](Core-Features_images/Core-Features_img12.png)


![](Core-Features_images/Core-Features_img13.png)


![](Core-Features_images/Core-Features_img14.png)


![](Core-Features_images/Core-Features_img15.png)
