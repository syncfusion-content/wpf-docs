---
layout: post
title: Changing the flow directions in WPF TaskBar Control | Syncfusion
description: Changing the flow directions in Syncfusion Essential Studio WPF TaskBar control, its elements and more.
platform: wpf
control: TaskBar
documentation: ug
---

# Changing the flow directions

The flow direction for the TaskBar is set through the FlowDirection property.

FlowDirection property table
<table>
<tr>
<th>
Property <th><th>
Description</th></tr>
<tr>
<td>
FlowDirection</td><td>
Sets the flow direction for the TaskBar. The options provided are as follows.LeftToRightRightToLeft</td></tr>
</table>


Here is the code for setting this property.

{%tabs%}
{% highlight xaml %}



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
{% endhighlight %}



{% highlight c# %}



// Setting flow direction as right to left

taskBar.FlowDirection = FlowDirection.RightToLeft;
{% endhighlight %}

{%endtabs%}


![Changing-the-flow-directions_images1](Changing-the-flow-directions_images/Changing-the-flow-directions_img1.jpeg)


FlowDirection = "RightToLeft"



