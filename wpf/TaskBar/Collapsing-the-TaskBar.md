---
layout: post
title: Collapsing the TaskBar in WPF TaskBar control | Syncfusion
description: Learn about Collapsing the TaskBar support in Syncfusion Essential Studio WPF TaskBar control, its elements and more.
platform: wpf
control: TaskBar
documentation: ug
---

# Collapsing the TaskBar in WPF TaskBar

You can expand or collapse the TaskBar control similar to the Windows Taskbar. This is done by using the [IsOpened](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.TaskBar.html#Syncfusion_Windows_Tools_Controls_TaskBar_IsOpenedProperty) property. This is an attached property, which is used to expand or collapse the TaskBarItems by using the [SetIsOpened](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.TaskBar.html#Syncfusion_Windows_Tools_Controls_TaskBar_SetIsOpened_System_Windows_DependencyObject_System_Boolean_) method.

This property is used in both TaskBar and TaskBarItems.

Use the following code snippet to expand or collapse the TaskBar.

{%tabs%}
{% highlight xaml %}



<!-- Adding TaskBar that have collapsed TaskBarItem -->

<syncfusion:TaskBar Name="taskBar" GroupMargin="5" syncfusion:TaskBar.IsOpened="False">



    <!-- Adding TaskBarItem -->

    <syncfusion:TaskBarItem Name="taskBarItem1" Header="TaskBarItem1">



        <!-- Adding content to TaskBarItem -->

        <StackPanel Margin="10" HorizontalAlignment="Center" 											VerticalAlignment="Stretch">

            <TextBlock TextWrapping="Wrap">This taskbar provides an UI similar to that of Windows XP.</TextBlock>

        </StackPanel>

    </syncfusion:TaskBarItem>



    <!-- Adding TaskBarItem -->

    <syncfusion:TaskBarItem Name="taskBarItem2" Header="TaskBarItem2">



        <!-- Adding content to TaskBarItem -->

        <StackPanel Margin="10" HorizontalAlignment="Center" 											VerticalAlignment="Stretch">

            <TextBlock TextWrapping="Wrap">Specify and customize the group margin.</TextBlock>

        </StackPanel>

    </syncfusion:TaskBarItem>

</syncfusion:TaskBar>
{% endhighlight %}

{% highlight c# %}



// To Collapse the TaskBarItem in TaskBar.

TaskBar.SetIsOpened(taskBar, false);
{% endhighlight %}

{%endtabs%}


![Collapsing the TaskBar](Collapsing-the-TaskBar_images/Collapsing-the-TaskBar_img1.jpeg)





{%seealso%}

Expander Button Size
{%endseealso%}
