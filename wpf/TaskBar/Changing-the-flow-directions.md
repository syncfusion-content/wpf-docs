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



<!-- Adding TaskBar  -->

<syncfusion:TaskBar Name="taskBar" FlowDirection="RightToLeft">



    <!-- Adding TaskBarItem -->

    <syncfusion:TaskBarItem Name="taskBarItem1" Header="TaskBarItem1">



        <!-- Adding content to TaskBarItem -->

        <StackPanel Margin="10" HorizontalAlignment="Center" 											VerticalAlignment="Stretch">

            <TextBlock TextWrapping="Wrap">

This is TaskBar that have a TaskBarItem</TextBlock>

        </StackPanel>

    </syncfusion:TaskBarItem>

</syncfusion:TaskBar>





[C#]



// Setting flow direction as right to left

taskBar.FlowDirection = FlowDirection.RightToLeft;





{{ '![](Changing-the-flow-directions_images/Changing-the-flow-directions_img1.jpeg)' | markdownify }}
{:.image }


_FlowDirection = "RightToLeft"_



