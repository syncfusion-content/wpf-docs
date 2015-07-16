---
layout: post
title: TreeMap-Legend
description: treemap legend
platform: wpf
control: TreeMap
documentation: ug
---

# TreeMap Legend

TreeMap legend is used to easily demonstrate about the color value of leaf nodes. But this legend could be appropriate only for the treemap having leaf nodes colored by using RangeBrushColorMapping. The labels of the legend item can be customized by specifying LegendLabel of RangeBrush mentioned in the Brushes of RangeBrushColorMapping.

The icon of legend item can be set by LegendIconStyle of TreeMapLegend. Custom legend icon can be set by assigning DataTemplate to LegendIconTemplate with LegendIconStyle as “Custom”. The width and height of the legend icon can be modified by setting LegendIconWidth and LegendIconHeight of TreeMapLegend.

The legend can be positioned to Left, Right, Top or Bottom of TreeMap with the help of LegendPosition property.



[XAML]



<syncfusion:SfTreeMap ItemsSource="{Binding PopulationDetails}" 

                      WeightValuePath="Population" ColorValuePath="Growth"

                      Margin="10" Name="TreeMap">

    &lt;syncfusion:SfTreeMap.Legend&gt;

        &lt;syncfusion:TreeMapLegend Margin="0 5" LegendItemMargin="0 0 20 10" LegendItemElementMargin="0 0 10 0" BorderThickness="0,0,0,2" BorderBrush="#CCCCCC" HorizontalAlignment="Left" LegendIconStyle="Rectangle" LegendIconHeight="18" LegendIconWidth="18" FontSize="25" Width="{Binding ActualWidth, ElementName=TreeMap}"&gt;

            &lt;syncfusion:TreeMapLegend.Header&gt;

               &lt;TextBlock Text="Population Growth FY2012" FontSize="35"                                   Margin="0,0,0,10”/&gt;

            &lt;/syncfusion:TreeMapLegend.Header&gt;

        &lt;/syncfusion:TreeMapLegend&gt;

    &lt;/syncfusion:SfTreeMap.Legend&gt;



    &lt;syncfusion:SfTreeMap.LeafColorMapping&gt;

        &lt;syncfusion:RangeBrushColorMapping&gt;

            &lt;syncfusion:RangeBrushColorMapping.Brushes&gt;

                &lt;syncfusion:RangeBrush Color="#77D8D8" From="0" To="1" LegendLabel="1 % Growth"/&gt;

                &lt;syncfusion:RangeBrush Color="#AED960" From="1" To="2" LegendLabel="2 % Growth"/&gt;

                &lt;syncfusion:RangeBrush Color="#FFAF51" From="2" To="3" LegendLabel="3 % Growth"/&gt;

                &lt;syncfusion:RangeBrush Color="#F3D240" From="3" To="4" LegendLabel="4 % Growth"/&gt;

            &lt;/syncfusion:RangeBrushColorMapping.Brushes&gt;

        &lt;/syncfusion:RangeBrushColorMapping&gt;

    &lt;/syncfusion:SfTreeMap.LeafColorMapping&gt;

    &lt;syncfusion:SfTreeMap.Levels&gt;

        &lt;syncfusion:TreeMapFlatLevel GroupPath="Continent" GroupGap="10"/&gt;

        <syncfusion:TreeMapFlatLevel GroupPath="Country" GroupGap="5"

                                     ShowLabels="True"/>

    &lt;/syncfusion:SfTreeMap.Levels&gt;

&lt;/syncfusion:SfTreeMap&gt;



{ ![](TreeMap-Legend_images/TreeMap-Legend_img1.png) | markdownify }
{:.image }


