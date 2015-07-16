---
layout: post
title: Changing-the-flow-directions
description: changing the flow directions
platform: wpf
control: TaskBar
documentation: ug
---

# Changing the flow directions

The flow direction for the TaskBar is set through the FlowDirection property.

_FlowDirection property table_

<table>
<tr>
<td>
Property</td><td>
Description</td></tr>
<tr>
<td>
FlowDirection</td><td>
Sets the flow direction for the TaskBar. The options provided are as follows.LeftToRightRightToLeft</td></tr>
</table>


Here is the code for setting this property.



[XAML]



&lt;!-- Adding TaskBar  --&gt;

&lt;syncfusion:TaskBar Name="taskBar" FlowDirection="RightToLeft"&gt;



    &lt;!-- Adding TaskBarItem --&gt;

    &lt;syncfusion:TaskBarItem Name="taskBarItem1" Header="TaskBarItem1"&gt;



        &lt;!-- Adding content to TaskBarItem --&gt;

        &lt;StackPanel Margin="10" HorizontalAlignment="Center" 											VerticalAlignment="Stretch"&gt;

            &lt;TextBlock TextWrapping="Wrap"&gt;

This is TaskBar that have a TaskBarItem</TextBlock>

        &lt;/StackPanel&gt;

    &lt;/syncfusion:TaskBarItem&gt;

&lt;/syncfusion:TaskBar&gt;





[C#]



// Setting flow direction as right to left

taskBar.FlowDirection = FlowDirection.RightToLeft;





{ ![](Changing-the-flow-directions_images/Changing-the-flow-directions_img1.jpeg) | markdownify }
{:.image }


_FlowDirection = "RightToLeft"_



