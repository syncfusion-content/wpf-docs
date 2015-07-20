---
layout: post
title: ColorMapping
description: colormapping
platform: wpf
control: TreeMap
documentation: ug
---

# ColorMapping

ColorMapping is categorized into four different types such as,

* UniColorMapping
* RangeBrushColorMapping
* DesaturationColorMapping
* PaletteColorMapping
* GroupColorMapping



TreeMap ColorMapping:

The leaf nodes of TreeMap can be colored by setting LeafColorMapping of TreeMap.



[XAML]

 <syncfusion:SfTreeMap ItemsSource="{Binding PopulationDetails}" 

                       WeightValuePath="Population"                              

                       ColorValuePath="Growth">

    &lt;syncfusion:SfTreeMap.LeafColorMapping&gt;

        &lt;syncfusion:UniColorMapping Color="Crimson"/&gt;

    &lt;/syncfusion:SfTreeMap.LeafColorMapping&gt;

    &lt;syncfusion:SfTreeMap.Levels&gt;

        &lt;syncfusion:TreeMapFlatLevel GroupPath="Continent" GroupGap="10"/&gt;

    &lt;/syncfusion:SfTreeMap.Levels&gt;

 &lt;/syncfusion:SfTreeMap&gt;







TreeMapLevel ColorMapping:

The headers of TreeMap level can also be colored using ColorMapping property of TreeMapLevel. 



[XAML]



<syncfusion:SfTreeMap ItemsSource="{Binding PopulationDetails}" 

                       WeightValuePath="Population"                              

                       ColorValuePath="Growth">

    &lt;syncfusion:SfTreeMap.LeafColorMapping&gt;

        &lt;syncfusion:UniColorMapping Color="Orange"/&gt;

    &lt;/syncfusion:SfTreeMap.LeafColorMapping&gt;

    &lt;syncfusion:SfTreeMap.Levels&gt;

        &lt;syncfusion:TreeMapFlatLevel GroupPath="Continent" GroupGap="10" HeaderHeight="20"&gt;

            &lt;syncfusion:TreeMapFlatLevel.ColorMapping&gt;

                &lt;syncfusion:UniColorMapping Color="YellowGreen"/&gt;

            &lt;/syncfusion:TreeMapFlatLevel.ColorMapping&gt;

        &lt;/syncfusion:TreeMapFlatLevel&gt;

        &lt;syncfusion:TreeMapFlatLevel GroupPath="Country" GroupGap="5" HeaderHeight="15"&gt;

            &lt;syncfusion:TreeMapFlatLevel.ColorMapping&gt;

                &lt;syncfusion:UniColorMapping Color="Crimson"/&gt;

            &lt;/syncfusion:TreeMapFlatLevel.ColorMapping&gt;

        &lt;/syncfusion:TreeMapFlatLevel&gt;

    &lt;/syncfusion:SfTreeMap.Levels&gt;

 &lt;/syncfusion:SfTreeMap&gt;  



## UniColorMapping

TreeMap leaf nodes can be colored with the help of Color property specified using UniColorMapping.



[XAML]



    &lt;Grid Background="Black"&gt;

        &lt;Grid.DataContext&gt;

            &lt;local:PopulationViewModel/&gt;

        &lt;/Grid.DataContext&gt;

        <syncfusion:SfTreeMap ItemsSource="{Binding PopulationDetails}"                              

                              WeightValuePath="Population"                              

                              ColorValuePath="Growth">

            &lt;syncfusion:SfTreeMap.LeafColorMapping&gt;

                &lt;syncfusion:UniColorMapping Color="Crimson"/&gt;

            &lt;/syncfusion:SfTreeMap.LeafColorMapping&gt;

            &lt;syncfusion:SfTreeMap.Levels&gt;

                <syncfusion:TreeMapFlatLevel GroupPath="Continent" 

                                             GroupGap="10"/>

                <syncfusion:TreeMapFlatLevel GroupPath="Country" 

                                             GroupGap="5"

                                             ShowLabels="True"/>

            &lt;/syncfusion:SfTreeMap.Levels&gt;

        &lt;/syncfusion:SfTreeMap&gt;

    &lt;/Grid&gt;







{ ![](ColorMapping_images/ColorMapping_img1.png) | markdownify }
{:.image }


## RangeBrushColorMapping

The leaf nodes of TreeMap can be colored based upon the range, such as From and To, and Brush specified using RangeBrush collection of RangeBrushColorMapping.



[XAML]



<syncfusion:SfTreeMap ItemsSource="{Binding PopulationDetails}" 

                      WeightValuePath="Population" ColorValuePath="Growth">

    &lt;syncfusion:SfTreeMap.LeafColorMapping&gt;

        &lt;syncfusion:RangeBrushColorMapping&gt;

            &lt;syncfusion:RangeBrushColorMapping.Brushes&gt;

                &lt;syncfusion:RangeBrush From="0" To="1" Color="#A4C400"/&gt;

                &lt;syncfusion:RangeBrush From="1" To="2" Color="#AA00FF"/&gt;

                &lt;syncfusion:RangeBrush From="2" To="3" Color="#F0A30A"/&gt;

                &lt;syncfusion:RangeBrush From="3" To="4" Color="#1BA1E2"/&gt;

            &lt;/syncfusion:RangeBrushColorMapping.Brushes&gt;

        &lt;/syncfusion:RangeBrushColorMapping&gt;

    &lt;/syncfusion:SfTreeMap.LeafColorMapping&gt;

    &lt;syncfusion:SfTreeMap.Levels&gt;

        &lt;syncfusion:TreeMapFlatLevel GroupPath="Continent" GroupGap="10"/&gt;

        <syncfusion:TreeMapFlatLevel GroupPath="Country" GroupGap="5"

                                     ShowLabels="True"/>

    &lt;/syncfusion:SfTreeMap.Levels&gt;

&lt;/syncfusion:SfTreeMap&gt;





{ ![](ColorMapping_images/ColorMapping_img2.png) | markdownify }
{:.image }


## DesaturationColorMapping

The leaf nodes of TreeMap can be colored based upon the Color specified using DesaturationColorMapping. The RangeMinimum and RangeMaximum must be specified to determine the opacity for each leaf node. The opacity of leaf nodes are in the range of From and To mentioned in DesaturationColorMapping.



[XAML]



<syncfusion:SfTreeMap ItemsSource="{Binding PopulationDetails}"   

                      WeightValuePath="Population" ColorValuePath="Growth">

    &lt;syncfusion:SfTreeMap.LeafColorMapping&gt;

        <syncfusion:DesaturationColorMapping From="1" To="0.5" 

                                             RangeMinimum="0" RangeMaximum="4" Color="DeepSkyBlue">

        &lt;/syncfusion:DesaturationColorMapping&gt;

    &lt;/syncfusion:SfTreeMap.LeafColorMapping&gt;

    &lt;syncfusion:SfTreeMap.Levels&gt;

        &lt;syncfusion:TreeMapFlatLevel GroupPath="Continent" GroupGap="10"/&gt;

        <syncfusion:TreeMapFlatLevel GroupPath="Country" GroupGap="5"

                                     ShowLabels="True"/>

    &lt;/syncfusion:SfTreeMap.Levels&gt;

&lt;/syncfusion:SfTreeMap&gt;





{ ![](ColorMapping_images/ColorMapping_img3.png) | markdownify }
{:.image }


## PaletteColorMapping

The leaf nodes are colored by using the brushes mentioned in Colors collection of PaletteColorMapping.



[XAML]



<syncfusion:SfTreeMap ItemsSource="{Binding PopulationDetails}"                              

                      WeightValuePath="Population" ColorValuePath="Growth">

    &lt;syncfusion:SfTreeMap.LeafColorMapping&gt;

        &lt;syncfusion:PaletteColorMapping&gt;

            &lt;syncfusion:PaletteColorMapping.Colors&gt;

                &lt;SolidColorBrush Color="Red"/&gt;&lt;SolidColorBrush Color="Blue"/&gt;

                &lt;SolidColorBrush Color="Green"/&gt;&lt;SolidColorBrush Color="Yellow"/&gt;&lt;SolidColorBrush Color="Orange"/&gt;&lt;SolidColorBrush Color="Orchid"/&gt;&lt;SolidColorBrush Color="Brown"/&gt;&lt;SolidColorBrush Color="BlueViolet"/&gt;&lt;SolidColorBrush Color="OrangeRed"/&gt;

                &lt;SolidColorBrush Color="Magenta"/&gt;

                &lt;SolidColorBrush Color="Olive"/&gt;

                &lt;SolidColorBrush Color="Crimson"/&gt;

                &lt;SolidColorBrush Color="DeepSkyBlue"/&gt;

            &lt;/syncfusion:PaletteColorMapping.Colors&gt;

        &lt;/syncfusion:PaletteColorMapping&gt;

    &lt;/syncfusion:SfTreeMap.LeafColorMapping&gt;

    &lt;syncfusion:SfTreeMap.Levels&gt;

        &lt;syncfusion:TreeMapFlatLevel GroupPath="Continent" GroupGap="10"/&gt;

        <syncfusion:TreeMapFlatLevel GroupPath="Country" GroupGap="5"

                                     ShowLabels="True"/>

    &lt;/syncfusion:SfTreeMap.Levels&gt;

&lt;/syncfusion:SfTreeMap&gt;





{ ![](ColorMapping_images/ColorMapping_img4.png) | markdownify }
{:.image }


## GroupColorMapping

The leaf nodes are colored by using different ColorMappings available in the TreeMap control. Each group can also be colored with different ColorMappings of TreeMapGroupColorMapping. GroupColorMapping is done based on the GroupID property.



[XAML]



<syncfusion:SfTreeMap Name="TreeMap" ItemsSource="{Binding PopulationDetails}" WeightValuePath="Growth" ColorValuePath="Growth"

                              ItemsLayoutMode="Squarified" Margin="10">



            &lt;syncfusion:SfTreeMap.GroupColorMappings&gt;

                &lt;syncfusion:GroupColorMapping GroupID="North America"&gt;

                    &lt;syncfusion:GroupColorMapping.TreeMapColorMapping&gt;

                        &lt;syncfusion:DesaturationColorMapping From="1" To="0.1" Color="#F3D240" RangeMinimum="0" RangeMaximum="6"/&gt;

                    &lt;/syncfusion:GroupColorMapping.TreeMapColorMapping&gt;

                &lt;/syncfusion:GroupColorMapping&gt;

                &lt;syncfusion:GroupColorMapping GroupID="Asia"&gt;

                    &lt;syncfusion:GroupColorMapping.TreeMapColorMapping&gt;

                        &lt;syncfusion:DesaturationColorMapping From="1" To="0.1" Color="#77D8D8" RangeMinimum="0" RangeMaximum="7"/&gt;

                    &lt;/syncfusion:GroupColorMapping.TreeMapColorMapping&gt;

                &lt;/syncfusion:GroupColorMapping&gt;

                &lt;syncfusion:GroupColorMapping GroupID="Africa"&gt;

                    &lt;syncfusion:GroupColorMapping.TreeMapColorMapping&gt;

                        &lt;syncfusion:DesaturationColorMapping From="1" To="0.1" Color="#faafbe" RangeMinimum="0" RangeMaximum="6"/&gt;

                    &lt;/syncfusion:GroupColorMapping.TreeMapColorMapping&gt;

                &lt;/syncfusion:GroupColorMapping&gt;

                &lt;syncfusion:GroupColorMapping GroupID="Europe"&gt;

                    &lt;syncfusion:GroupColorMapping.TreeMapColorMapping&gt;

                        &lt;syncfusion:DesaturationColorMapping From="1" To="0.1" Color="#AED960" RangeMinimum="0" RangeMaximum="6"/&gt;

                    &lt;/syncfusion:GroupColorMapping.TreeMapColorMapping&gt;

                &lt;/syncfusion:GroupColorMapping&gt;

                &lt;syncfusion:GroupColorMapping GroupID="South America"&gt;

                    &lt;syncfusion:GroupColorMapping.TreeMapColorMapping&gt;

                        &lt;syncfusion:DesaturationColorMapping From="1" To="0" Color="#FFAF51" RangeMinimum="0" RangeMaximum="6"/&gt;

                    &lt;/syncfusion:GroupColorMapping.TreeMapColorMapping&gt;

                &lt;/syncfusion:GroupColorMapping&gt;

            &lt;/syncfusion:SfTreeMap.GroupColorMappings&gt;



&lt;/syncfusion:SfTreeMap&gt;



{ ![](ColorMapping_images/ColorMapping_img5.png) | markdownify }
{:.image }


