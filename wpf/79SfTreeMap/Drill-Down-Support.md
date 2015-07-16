---
layout: post
title: Drill-Down-Support
description: drill down support
platform: wpf
control: TreeMap
documentation: ug
---

# Drill Down Support

TreeMap enables drill down to expose the hierarchy by clicking on a treemap node and allows drill up by clicking on drill down header. At a time, only one level of the hierarchy can be seen in the treemap.

Enabling Drill Down

Treemap items can be drilled down by enabling the property EnableDrillDown to ‘_true’_. The hierarchy of treemap levels can be shown by clicking on treemap items. The previous level can be drilled up by clicking on drill down header. DrilldDown header can be customized with the help of DrillDownHeaderTemplate property.

_Drill D__own Properties_

<table>
<tr>
<td>
Property </td><td>
Type </td><td>
Description</td></tr>
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




[XAML]



<syncfusion:SfTreeMap x:Name="TreeMap" ItemsSource="{Binding}" 

                      EnableDrillDown="True"     

                      DrillDownSelectionStroke="#1A9DAF"

                      WeightValuePath="Population" ColorValuePath="Area"

                      LeafLabelPath="Name" BorderThickness="1">

    &lt;syncfusion:SfTreeMap.DrillDownHeaderTemplate&gt;

        &lt;DataTemplate&gt;

            &lt;Border Background="#1A9DAF"&gt;

                &lt;StackPanel Orientation="Horizontal" VerticalAlignment="Center" Margin="10 0"&gt;

                    &lt;Path x:Name="path" Data="M197,153.5 L197,138 186.75,145.5 z" Height="16" Width="8" Fill="White" Stretch="Fill" /&gt;

                    <TextBlock Text="{Binding}" Margin="10 0" FontSize="15" 

                               FontWeight="Normal" FontFamily="Segoe UI" Foreground="White"/>

                &lt;/StackPanel&gt;

            &lt;/Border&gt;

        &lt;/DataTemplate&gt;

    &lt;/syncfusion:SfTreeMap.DrillDownHeaderTemplate&gt;

    &lt;syncfusion:SfTreeMap.LeafColorMapping&gt;

        &lt;syncfusion:UniColorMapping Color="#CCDFE3"/&gt;

    &lt;/syncfusion:SfTreeMap.LeafColorMapping&gt;

    &lt;syncfusion:SfTreeMap.Levels&gt;

        &lt;syncfusion:TreeMapFlatLevel GroupPath="Continent" ShowLabels="True"/&gt;

        &lt;syncfusion:TreeMapFlatLevel GroupPath="Country" ShowLabels="True"/&gt;

    &lt;/syncfusion:SfTreeMap.Levels&gt;

&lt;/syncfusion:SfTreeMap&gt;





The following screenshot illustrates a TreeMap with drill down support.



{ ![](Drill-Down-Support_images/Drill-Down-Support_img1.png) | markdownify }
{:.image }


_TreeMap with drill down support_





