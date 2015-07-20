---
layout: post
title: CustomToolTip
description: customtooltip
platform: wpf
control: Gantt
documentation: ug
---

# CustomToolTip

Essential Gantt provides tooltip support for the TaskBar. Tooltip is a small pop-up box, which is usually displayed on mouse hover. This is used to display additional information about the elements without increasing the window size. Essential Gantt provides support to add customizable tooltip. You can add text or image to your tooltip as needed. 

Properties

_Property_

<table>
<tr>
<td>
Property </td><td>
Description </td><td>
Type </td><td>
Data Type </td></tr>
<tr>
<td>
ToolTipTemplate</td><td>
Gets or set the TaskBarCollection Property of GanttControl</td><td>
Dependency Property</td><td>
DataTemplate</td></tr>
</table>


Adding CustomToolTip to Gantt 

The following code illustrates how to add a custom tooltip to the Gantt control.



[XAML]

 &lt;DataTemplate x:Key="ToolTipTemp"&gt;
            &lt;Grid&gt;
                &lt;Grid.ColumnDefinitions&gt;
                    &lt;ColumnDefinition /&gt;
                    &lt;ColumnDefinition /&gt;
                &lt;/Grid.ColumnDefinitions&gt;
                &lt;Grid.RowDefinitions&gt;
                    &lt;RowDefinition Height="40" /&gt;
                    &lt;RowDefinition Height="40" /&gt;
                    &lt;RowDefinition Height="40" /&gt;
                    &lt;RowDefinition Height="40" /&gt;
                    &lt;RowDefinition Height="40" /&gt;
                &lt;/Grid.RowDefinitions&gt;
                &lt;Border Grid.Column="0" Grid.Row="0" Margin="-2"                        CornerRadius="5" Grid.ColumnSpan="2" Background="#FF1F4877"                        BorderThickness="2"&gt;
                    &lt;TextBlock  Margin="5,0,0,0" Text="{Binding TaskName}"                                HorizontalAlignment="Center"                                VerticalAlignment="Center" FontWeight="Bold"                                FontFamily="Verdana" Foreground="WhiteSmoke" /&gt;

                &lt;/Border&gt;
                &lt;TextBlock Margin="1" Text="TaskID:" Grid.Column="0"                           Grid.Row="1" VerticalAlignment="Center"                           FontFamily="Verdana" /&gt;
                &lt;TextBlock Margin="1" Text="{Binding TaskId}" Grid.Column="1"                           VerticalAlignment="Center" Grid.Row="1"                           FontFamily="Verdana" /&gt;

                &lt;TextBlock Margin="1" Text="Start Date:" Grid.Column="0"                           Grid.Row="2" VerticalAlignment="Center"                           FontFamily="Verdana" /&gt;
                <TextBlock Margin="1" Text="{Binding StartDate}" Grid.Row="2"

                           Grid.Column="1" VerticalAlignment="Center"
                           FontFamily="Verdana" />
                &lt;TextBlock Margin="1" Text="Finish Date:"  Grid.Column="0"                           Grid.Row="3" VerticalAlignment="Center"                           FontFamily="Verdana" /&gt;
                &lt;TextBlock Margin="1" Text="{Binding FinishDate}" Grid.Column="1"                           Grid.Row="3" VerticalAlignment="Center"                           FontFamily="Verdana" /&gt;
                &lt;TextBlock Margin="1" Text="Progress:" Grid.Column="0"                           Grid.Row="4" VerticalAlignment="Center"                           FontFamily="Verdana" /&gt;
                &lt;ProgressBar Margin="1" Height="25" Value="{Binding Progress}"                             Grid.Column="1" VerticalAlignment="Center"                             Grid.Row="4" /&gt;
            &lt;/Grid&gt; 
        &lt;/DataTemplate&gt;

&lt;Sync:GanttControl x:Name="Gantt" ToolTipTemplate="{StaticResource ToolTipTemp}"/&gt;





The following image shows Custom ToolTip:



{ ![](CustomToolTip_images/CustomToolTip_img1.png) | markdownify }
{:.image }


_Custom ToolTip Demo_

Samples Link

To view samples: 

1. Select Start -> Programs -> Syncfusion -> Essential Studio x.x.xx -> Dashboard.
1. Click Run Samples for WPF under User Interface Edition panel .
2. Select Gantt.
3. Expand the Interactive Features item in the Sample Browser.
4. Choose the CustomToolTip samples to launch.



