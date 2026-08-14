---
layout: post
title: Changing Flow Direction in WPF TaskBar | Syncfusion®
description: Changing Flow Direction in WPF TaskBar enables content arrangement for left-to-right (LTR) and right-to-left (RTL) user interface layouts.
platform: wpf
control: TaskBar
documentation: ug
---

# Changing Flow Direction in WPF TaskBar

The flow direction for the TaskBar is set through the [FlowDirection](https://learn.microsoft.com/en-us/dotnet/api/system.windows.frameworkelement.flowdirection?redirectedfrom=MSDN&view=netframework-4.7.2#System_Windows_FrameworkElement_FlowDirection) property.

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


![Flow directions](Changing-the-flow-directions_images/Changing-the-flow-directions_img1.jpeg)


FlowDirection = "RightToLeft"



