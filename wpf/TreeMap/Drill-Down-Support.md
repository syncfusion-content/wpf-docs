---
layout: post
title: Drill Down Support in WPF TreeMap control | Syncfusion
description: Learn here all about Drill Down Support support in Syncfusion WPF TreeMap (SfTreeMap) control and more.
platform: wpf
control: TreeMap
documentation: ug
---

# Drill Down Support in WPF TreeMap (SfTreeMap)

TreeMap enables drill down to expose the hierarchy by clicking on a treemap node and allows drill up by clicking on drill down header. At a time, only one level of the hierarchy can be seen in the treemap.

## Enabling Drill Down

Treemap items can be drilled down by enabling the property EnableDrillDown to ‘_true’_. The hierarchy of treemap levels can be shown by clicking on treemap items. The previous level can be drilled up by clicking on drill down header. DrillDown header can be customized with the help of DrillDownHeaderTemplate property.

Drill Down Properties

<table>
<tr>
<th>
Property</th><th>
Type </th><th>
Description</th></tr>
<tr>
<td>
EnableDrillDown</td><td>
Bool</td><td>
Gets or sets a value to indicate whether the drill down support should be enabled.</td></tr>
<tr>
<td>
DrillDownHeaderHeight</td><td>
Double</td><td>
Gets or sets a value for specifying the height for drill down header.</td></tr>
<tr>
<td>
DrillDownHeaderTemplate</td><td>
DataTemplate</td><td>
Gets or sets a template to customize drill down header.</td></tr>
<tr>
<td>
DrillDownSelectionStroke</td><td>
Brush</td><td>
Gets or sets a color for highlighting tree map item while drill down.</td></tr>
</table>



{% highlight xaml %}



<syncfusion:SfTreeMap x:Name="TreeMap" ItemsSource="{Binding}" 

                      EnableDrillDown="True"     

                      DrillDownSelectionStroke="#1A9DAF"

                      WeightValuePath="Population" ColorValuePath="Area"

                      LeafLabelPath="Name" BorderThickness="1">

    <syncfusion:SfTreeMap.DrillDownHeaderTemplate>

        <DataTemplate>

            <Border Background="#1A9DAF">

                <StackPanel Orientation="Horizontal" VerticalAlignment="Center" Margin="10 0">

                    <Path x:Name="path" Data="M197,153.5 L197,138 186.75,145.5 z" Height="16" Width="8" Fill="White" Stretch="Fill" />

                    <TextBlock Text="{Binding}" Margin="10 0" FontSize="15" 

                               FontWeight="Normal" FontFamily="Segoe UI" Foreground="White"/>

                </StackPanel>

            </Border>

        </DataTemplate>

    </syncfusion:SfTreeMap.DrillDownHeaderTemplate>

    <syncfusion:SfTreeMap.LeafColorMapping>

        <syncfusion:UniColorMapping Color="#CCDFE3"/>

    </syncfusion:SfTreeMap.LeafColorMapping>

    <syncfusion:SfTreeMap.Levels>

        <syncfusion:TreeMapFlatLevel GroupPath="Continent" ShowLabels="True"/>

        <syncfusion:TreeMapFlatLevel GroupPath="Country" ShowLabels="True"/>

    </syncfusion:SfTreeMap.Levels>

</syncfusion:SfTreeMap>

{% endhighlight %}



The following screenshot illustrates a TreeMap with drill down support.



![Drilldown support image](Drill-Down-Support_images/Drill-Down-Support_img1.png)



TreeMap with drill down support
{:.caption}


## see also

[How to customize leaf level SfTreeMap](https://www.syncfusion.com/kb/7649/how-to-customize-leaf-level-treemap) 

[How to apply colors based on the ColorValuePath to a leaf template in SfTreeMap](https://www.syncfusion.com/kb/4099/how-to-apply-colors-based-on-the-colorvaluepath-to-a-leaftemplate-in-sftreemap) 
