---
layout: post
title: Appearance in WPF Olap Chart | Syncfusion®
description: Appearance in the WPF OLAP Chart allows you to customize chart elements, colors, styles, and visual settings for improved presentation.
platform: wpf
control: OLAP Chart
documentation: ug
appliesto: UI Component Suite, Chart SDK
---

# Appearance in WPF Olap Chart

The WPF OLAP Chart supports customizing the appearance of charts. You can customize the chart style, legend style, border and background style, point label style, and label style of the primary and secondary axes.

## Chart style and legends

The WPF OLAP Chart provides options to set the chart type, chart color, chart legend position, chart legend, and legend check box visibility:

* [ChartType](https://help.syncfusion.com/cr/wpf/Syncfusion.Olap.Reports.ChartAppearanceSettings.html#Syncfusion_Olap_Reports_ChartAppearanceSettings_ChartType): Sets the chart type for the OLAP chart control.
* **ColorModel.Palette**: Specifies the chart color for the OLAP chart control.
* **Legend.Visibility**: Specifies the visibility of the chart legend.
* **Legend.CheckBoxVisibility**: Specifies the visibility of the chart legend check box.
* **ChartDockPanel.SetDock**: Specifies the position of the chart legend.

The following code sample illustrates how to customize the chart style and legends.

{% tabs %}

{% highlight c# %}
 
//Â SetÂ theÂ ChartÂ Type.
this.olapChart.ChartTypeÂ =Â ChartTypes.Column;
//Â SetÂ theÂ ChartÂ Series Color.
this.olapChart.ColorModel.PaletteÂ =Â ChartColorPalette.Colorful;
//Â SetÂ theÂ ChartÂ LegendÂ andÂ LegendÂ CheckÂ BoxÂ Visibility.
this.olapChart.Legend.VisibilityÂ =Â Visibility.Visible;
this.olapChart.Legend.VisibilityÂ =Â Visibility.Collapsed;
this.olapChart.Legend.CheckBoxVisibilityÂ =Â Visibility.Visible;
this.olapChart.Legend.CheckBoxVisibilityÂ =Â Visibility.Collapsed;
//Â SetÂ theÂ ChartÂ LegendÂ Position.
ChartDockPanel.SetDock(this.olapChart.Legend,Â ChartDock.Right);
ChartDockPanel.SetDock(this.olapChart.Legend,Â ChartDock.Left);
ChartDockPanel.SetDock(this.olapChart.Legend,Â ChartDock.Top);
ChartDockPanel.SetDock(this.olapChart.Legend,Â ChartDock.Bottom);
ChartDockPanel.SetDock(this.olapChart.Legend,Â ChartDock.Floating);

{% endhighlight %}

{% highlight vbnet %}
  
'Â SetÂ theÂ ChartÂ Type.
Me.olapChart.ChartTypeÂ =Â ChartTypes.Column
'Â SetÂ theÂ ChartÂ SeriesÂ Color.
Me.olapChart.ColorModel.PaletteÂ =Â ChartColorPalette.Colorful
'Â SetÂ theÂ ChartÂ LegendÂ andÂ LegendÂ CheckÂ BoxÂ Visibility.
Me.olapChart.Legend.VisibilityÂ =Â Visibility.Visible
Me.olapChart.Legend.VisibilityÂ =Â Visibility.Collapsed
Me.olapChart.Legend.CheckBoxVisibilityÂ =Â Visibility.Visible
Me.olapChart.Legend.CheckBoxVisibilityÂ =Â Visibility.Collapsed
'Â SetÂ theÂ ChartÂ LegendÂ Position.
ChartDockPanel.SetDock(Me.olapChart.Legend,Â ChartDock.Right)
ChartDockPanel.SetDock(Me.olapChart.Legend,Â ChartDock.Left)
ChartDockPanel.SetDock(Me.olapChart.Legend,Â ChartDock.Top)
ChartDockPanel.SetDock(Me.olapChart.Legend,Â ChartDock.Bottom)
ChartDockPanel.SetDock(Me.olapChart.Legend,Â ChartDock.Floating)

{% endhighlight %}

{% endtabs %}

![Appearance_img1](Appearance_images/Appearance_img1.png)

## Chart border and background style

The WPF OLAP Chart provides options to set the chart border and background style:

* **BorderThickness**: Sets the border thickness for the OLAP chart control.
* **BorderBrush**: Specifies the border color for the OLAP chart control.
* **Background**: Specifies the background color for the OLAP chart control.
* **GridBackground**: Specifies the interior background color for the OLAP chart control.

The following code sample illustrates how to customize the chart border and the background style.

{% tabs %}

{% highlight c# %}

// Set the Chart Border Style.
this.olapChart.BorderThickness = new Thickness(2);
this.olapChart.BorderBrush = Brushes.Blue;
// Set the Chart Background Style.
this.olapChart.Background = Brushes.LightBlue;
this.olapChart.GridBackground = Brushes.LightGray;

{% endhighlight %}

{% highlight vbnet %}
  
'Â SetÂ theÂ ChartÂ BorderÂ Style.
Me.olapChart.BorderThicknessÂ =Â NewÂ Thickness(2)
Me.olapChart.BorderBrushÂ =Â Brushes.Blue
'Â SetÂ theÂ ChartÂ BackgroundÂ Style.
Me.olapChart.BackgroundÂ =Â Brushes.LightBlue
Me.olapChart.GridBackgroundÂ =Â Brushes.LightGray

{% endhighlight %}

{% endtabs %}
 
![Appearance_img2](Appearance_images/Appearance_img2.png)

## Chart points labels

The WPF OLAP Chart supports customizing the labels and symbols of chart points. This is illustrated in the following code sample.

{% tabs %}

{% highlight c# %}
 
foreachÂ (ChartSeriesÂ seriesÂ inÂ this.Series)
{
Â Â Â Â series.AdornmentsInfo.VisibleÂ =Â true;
Â Â Â Â ChartAdornmentInfoÂ caiÂ =Â series.AdornmentsInfo;
Â Â Â Â //Â ToÂ displayÂ theÂ x-axisÂ labelÂ value.
Â Â Â Â series.AdornmentsInfo.LabelContentPathÂ =Â "DataPoint.X";
Â Â Â Â //Â ToÂ displayÂ theÂ y-axisÂ labelÂ value.
Â Â Â Â series.AdornmentsInfo.LabelContentPathÂ =Â "DataPoint.Y";
Â Â Â Â //Â ToÂ displayÂ theÂ SeriesÂ labelÂ value.
Â Â Â Â series.AdornmentsInfo.LabelContentPathÂ =Â "Series.Label";
}

{% endhighlight %}

{% highlight vbnet %}
  
ForÂ EachÂ seriesÂ AsÂ ChartSeriesÂ InÂ Me.Series
Â Â Â Â series.AdornmentsInfo.VisibleÂ =Â True
Â Â Â Â DimÂ caiÂ AsÂ ChartAdornmentInfoÂ =Â series.AdornmentsInfo
Â Â Â Â 'Â ToÂ displayÂ theÂ x-axisÂ labelÂ value.
Â Â Â Â series.AdornmentsInfo.LabelContentPathÂ =Â "DataPoint.X"
Â Â Â Â 'Â ToÂ displayÂ theÂ y-axisÂ labelÂ value.
Â Â Â Â series.AdornmentsInfo.LabelContentPathÂ =Â "DataPoint.Y"
Â Â Â Â 'Â ToÂ displayÂ theÂ SeriesÂ labelÂ value.
Â Â Â Â series.AdornmentsInfo.LabelContentPathÂ =Â "Series.Label"
NextÂ series

{% endhighlight %}

{% endtabs %}

![Appearance_img3](Appearance_images/Appearance_img3.png)

## Chart axis labels

The WPF OLAP Chart supports customizing the labels of primary and secondary axes.

### Customizing the font style of the primary axis

Dynamically change the font family, font color, and font weight for labels of the primary axis:

* **PrimaryAxis.LabelFontFamily**: Specifies the font family for the label of the primary axis.
* **PrimaryAxis.LabelForeground**: Specifies the font color for the label of the primary axis.
* **PrimaryAxis.LabelFontWeight**: Specifies the font weight for the label of the primary axis.

The following code sample illustrates how to customize the font style of the primary axis.

{% tabs %}

{% highlight c# %}
 
//Â SetÂ theÂ FontÂ Family.
this.olapChart.PrimaryAxis.LabelFontFamilyÂ =Â newÂ FontFamily("Arial");
//Â SetÂ theÂ FontÂ Color.
this.olapChart.PrimaryAxis.LabelForegroundÂ =Â Brushes.LightBlue;
//Â SetÂ theÂ FontÂ Weight.
this.olapChart.PrimaryAxis.LabelFontWeightÂ =Â FontWeights.Bold;

{% endhighlight %}

{% highlight vbnet %}
  
'Â SetÂ theÂ FontÂ Family.
Me.olapChart.PrimaryAxis.LabelFontFamilyÂ =Â NewÂ FontFamily("Arial")
'Â SetÂ theÂ FontÂ Color.
Me.olapChart.PrimaryAxis.LabelForegroundÂ =Â Brushes.LightBlue
'Â SetÂ theÂ FontÂ Weight.
Me.olapChart.PrimaryAxis.LabelFontWeightÂ =Â FontWeights.Bold

{% endhighlight %}

{% endtabs %}
 
### Customizing the font style of the secondary axis

Dynamically change the font family, font color, and font weight for labels of the secondary axis.

* **SecondaryAxis.LabelFontFamily**: Specifies the font family for the label of the secondary axis.
* **SecondaryAxis.LabelForeground**: Specifies the font color for the label of the secondary axis.
* **SecondaryAxis.LabelFontWeight**: Specifies the font weight for the label of the secondary axis.

The following code sample illustrates how to customize the font style of the secondary axis.

{% tabs %}

{% highlight c# %}
 
//Â SetÂ theÂ FontÂ Family.
this.olapChart.SecondaryAxis.LabelFontFamilyÂ =Â newÂ FontFamily("Arial");
//Â SetÂ theÂ ForegroundÂ Color.
this.olapChart.SecondaryAxis.LabelForegroundÂ =Â Brushes.LightBlue;
//Â SetÂ theÂ FontÂ Weight.
this.olapChart.SecondaryAxis.LabelFontWeightÂ =Â FontWeights.Bold;

{% endhighlight %}

{% highlight vbnet %}
  
'Â SetÂ theÂ FontÂ Family.
Me.olapChart.SecondaryAxis.LabelFontFamilyÂ =Â NewÂ FontFamily("Arial")
'Â SetÂ theÂ ForegroundÂ Color.
Me.olapChart.SecondaryAxis.LabelForegroundÂ =Â Brushes.LightBlue
'Â SetÂ theÂ FontÂ Weight.
Me.olapChart.SecondaryAxis.LabelFontWeightÂ =Â FontWeights.Bold

{% endhighlight %}

{% endtabs %}

![Appearance_img4](Appearance_images/Appearance_img4.png)

A sample demo is available at the following location.

{system drive}:\Users\&lt;User Name&gt;\AppData\Local\Syncfusion\EssentialStudio\&lt;Version Number&gt;\WPF\OlapChart.WPF\Samples\Chart Appearance\Appearance
