---
layout: post
title: ToolTip-Support
description: tooltip support
platform: wpf
control: TreeMap
documentation: ug
---

# ToolTip Support

You can enable ToolTip for TreeMap by setting ShowToolTip to “True”. For modifying default appearance of ToolTip, ToolTipTemplate can be specified.



[XAML]



<syncfusion:SfTreeMap ItemsSource="{Binding PopulationDetails}" 

                      WeightValuePath="Population" ColorValuePath="Growth"

                      ShowToolTip="True">

    &lt;syncfusion:SfTreeMap.ToolTipTemplate&gt;

        &lt;DataTemplate&gt;

            &lt;Grid Height="200" Width="420" Margin="0,-420,0,0"&gt;

                &lt;Path Data="M0,0 L360,0 L360,200 L20,200 L-20,220 L0,160 L0,0 z" Fill="#666666" Stroke="Wheat" Opacity="0.9" Stretch="Fill"/&gt;

                &lt;StackPanel&gt;

                  &lt;Grid Background="{Binding MappedColor}" Margin="40 10 20 0" Height="40"&gt;

                  &lt;TextBlock Text="{Binding Data.Continent}" Foreground= "White" FontWeight="SemiBold" FontSize="30" TextAlignment="Center"/&gt;

                  &lt;/Grid&gt;

                  &lt;StackPanel Margin="40 20"&gt;

                  &lt;StackPanel Orientation="Horizontal"&gt;

                  &lt;TextBlock Text="Country" Width="140" FontSize="25"/&gt;

                  &lt;TextBlock Text="-" Width="20" FontSize="25"/&gt;

                  &lt;TextBlock Text="{Binding Data.Country}" FontSize="25"/&gt;

                  &lt;/StackPanel&gt;

                  &lt;StackPanel Orientation="Horizontal"&gt;

                  &lt;TextBlock Text="Population" Width="140" FontSize="25"/&gt;

                  &lt;TextBlock Text="-" Width="20" FontSize="25"/&gt;

                  &lt;TextBlock Text="{Binding Data.Population}" FontSize="25"/&gt;

                  &lt;/StackPanel&gt;

                  &lt;/StackPanel&gt;

                &lt;/StackPanel&gt;

            &lt;/Grid&gt;

        &lt;/DataTemplate&gt;

    &lt;/syncfusion:SfTreeMap.ToolTipTemplate&gt;

    &lt;syncfusion:SfTreeMap.LeafColorMapping&gt;

        &lt;syncfusion:RangeBrushColorMapping&gt;

            &lt;syncfusion:RangeBrushColorMapping.Brushes&gt;

                &lt;syncfusion:RangeBrush From="0" To="1" Color="#1BA1E2"/&gt;

                &lt;syncfusion:RangeBrush From="1" To="2" Color="#F09609"/&gt;

                &lt;syncfusion:RangeBrush From="2" To="3" Color="#E671B8"/&gt;

                &lt;syncfusion:RangeBrush From="3" To="4" Color="#339933"/&gt;

            &lt;/syncfusion:RangeBrushColorMapping.Brushes&gt;

        &lt;/syncfusion:RangeBrushColorMapping&gt;

    &lt;/syncfusion:SfTreeMap.LeafColorMapping&gt;

    &lt;syncfusion:SfTreeMap.Levels&gt;

        &lt;syncfusion:TreeMapFlatLevel GroupPath="Continent" GroupGap="10"/&gt;

        &lt;syncfusion:TreeMapFlatLevel GroupPath="Country" GroupGap="5" ShowLabels="True"/&gt;

    &lt;/syncfusion:SfTreeMap.Levels&gt;

&lt;/syncfusion:SfTreeMap&gt;





The following screenshot shows a tree map with a tool tip.



{ ![](ToolTip-Support_images/ToolTip-Support_img1.png) | markdownify }
{:.image }


