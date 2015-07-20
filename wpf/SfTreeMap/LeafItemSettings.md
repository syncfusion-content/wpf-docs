---
layout: post
title: LeafItemSettings
description: leafitemsettings
platform: wpf
control: TreeMap
documentation: ug
---

# LeafItemSettings

LeafItemSettings of SfTreeMap is a setting by which we can settings the template for the leafNode.



[XAML]



    &lt;Grid Background="Black"&gt;

        &lt;Grid.DataContext&gt;

            &lt;local:PopulationViewModel/&gt;

        &lt;/Grid.DataContext&gt;

        <syncfusion:SfTreeMap Name="TreeMap" ItemsSource="{Binding PopulationDetails}" WeightValuePath="Population" ColorValuePath="Growth"

                              ItemsLayoutMode="Squarified" Margin="10">

            &lt;syncfusion:SfTreeMap.LeafItemSettings&gt;

                &lt;syncfusion:LeafItemSettings/&gt;

            &lt;/syncfusion:SfTreeMap.LeafItemSettings&gt;

       &lt;/syncfusion:SfTreeMap&gt;

    &lt;/Grid&gt; 





> _Note: The specified field must be available in each and every sub class (object) defined in hierarchical (nested) data collection._



## LabelPath

LabelPath of the leaves is WeightValuePath by default and you can change the LabelPath as desired based on the data provided.



[XAML]



    &lt;Grid Background="Black"&gt;

        &lt;Grid.DataContext&gt;

            &lt;local:PopulationViewModel/&gt;

        &lt;/Grid.DataContext&gt;

        <syncfusion:SfTreeMap Name="TreeMap" ItemsSource="{Binding PopulationDetails}" WeightValuePath="Population" ColorValuePath="Growth"

                              ItemsLayoutMode="Squarified" Margin="10">

            &lt;syncfusion:SfTreeMap.LeafItemSettings&gt;

                &lt;syncfusion:LeafItemSettings LabelPath="Country"/&gt;                                                                                      &lt;/syncfusion:SfTreeMap.LeafItemSettings&gt;

       &lt;/syncfusion:SfTreeMap&gt;

    &lt;/Grid&gt; 



## LabelTemplate

LabelTemplate of LeafitemSettings class provides the template for the labels of the leafNodes.



[XAML]



    &lt;Grid Background="Black"&gt;

        &lt;Grid.DataContext&gt;

            &lt;local:PopulationViewModel/&gt;

        &lt;/Grid.DataContext&gt;

        <syncfusion:SfTreeMap Name="TreeMap" ItemsSource="{Binding PopulationDetails}" WeightValuePath="Population" ColorValuePath="Growth"

                              ItemsLayoutMode="Squarified" Margin="10">

            &lt;syncfusion:SfTreeMap.LeafItemSettings&gt;

                &lt;syncfusion:LeafItemSettings&gt;

                    &lt;syncfusion:LeafItemSettings.LabelTemplate&gt;

                            &lt;DataTemplate&gt;

                                &lt;TextBlock Text="{Binding Data.Country}" Foreground="White" FontSize="16" FontWeight="Normal" HorizontalAlignment="Left" VerticalAlignment="Top" Margin="5,5,0,0"/&gt;

                            &lt;/DataTemplate&gt;



                    &lt;/syncfusion:LeafItemSettings.LabelTemplate&gt;

                &lt;/syncfusion:LeafItemSettings&gt;

            &lt;/syncfusion:SfTreeMap.LeafItemSettings&gt;

       &lt;/syncfusion:SfTreeMap&gt;

    &lt;/Grid&gt; 



## Gap

Gap provides the gap between the leaves at Leaf Level.



[XAML]



    &lt;Grid Background="Black"&gt;

        &lt;Grid.DataContext&gt;

            &lt;local:PopulationViewModel/&gt;

        &lt;/Grid.DataContext&gt;

        <syncfusion:SfTreeMap Name="TreeMap" ItemsSource="{Binding PopulationDetails}" WeightValuePath="Population" ColorValuePath="Growth"

                              ItemsLayoutMode="Squarified" Margin="10">

            &lt;syncfusion:SfTreeMap.LeafItemSettings&gt;

                &lt;syncfusion:LeafItemSettings Gap="5"&gt;

                &lt;/syncfusion:LeafItemSettings&gt;

            &lt;/syncfusion:SfTreeMap.LeafItemSettings&gt;

       &lt;/syncfusion:SfTreeMap&gt;

    &lt;/Grid&gt; 



## BorderBrush

BorderBrush provides the border color for the leafNodes and BorderThickness provides the thickness of the BorderBrush.



[XAML]



    &lt;Grid Background="Black"&gt;

        &lt;Grid.DataContext&gt;

            &lt;local:PopulationViewModel/&gt;

        &lt;/Grid.DataContext&gt;

        <syncfusion:SfTreeMap Name="TreeMap" ItemsSource="{Binding PopulationDetails}" WeightValuePath="Population" ColorValuePath="Growth"

                              ItemsLayoutMode="Squarified" Margin="10">

            &lt;syncfusion:SfTreeMap.LeafItemSettings&gt;

                &lt;syncfusion:LeafItemSettings BorderBrush="Red" BorderThickness="3"/&gt;  

            &lt;/syncfusion:SfTreeMap.LeafItemSettings&gt;

       &lt;/syncfusion:SfTreeMap&gt;

    &lt;/Grid&gt; 





{ ![](LeafItemSettings_images/LeafItemSettings_img1.png) | markdownify }
{:.image }


