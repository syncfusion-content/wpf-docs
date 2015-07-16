---
layout: post
title: Collapsing-the-TaskBar
description: collapsing the taskbar
platform: wpf
control: TaskBar
documentation: ug
---

# Collapsing the TaskBar

You can expand or collapse the TaskBar control similar to the Windows Taskbar. This is done by using the IsOpened property. This is an attached property, which is used to expand or collapse the TaskBarItems by using the SetIsOpened method.

This property is used in both TaskBar and TaskBarItems.

Use the following code snippet to expand or collapse the TaskBar.



[XAML]



&lt;!-- Adding TaskBar that have collapsed TaskBarItem --&gt;

&lt;syncfusion:TaskBar Name="taskBar" GroupMargin="5" syncfusion:TaskBar.IsOpened="False"&gt;



    &lt;!-- Adding TaskBarItem --&gt;

    &lt;syncfusion:TaskBarItem Name="taskBarItem1" Header="TaskBarItem1"&gt;



        &lt;!-- Adding content to TaskBarItem --&gt;

        &lt;StackPanel Margin="10" HorizontalAlignment="Center" 											VerticalAlignment="Stretch"&gt;

            <TextBlock TextWrapping="Wrap">This taskbar provides an UI similar to that of Windows XP.&lt;/TextBlock&gt;

        &lt;/StackPanel&gt;

    &lt;/syncfusion:TaskBarItem&gt;



    &lt;!-- Adding TaskBarItem --&gt;

    &lt;syncfusion:TaskBarItem Name="taskBarItem2" Header="TaskBarItem2"&gt;



        &lt;!-- Adding content to TaskBarItem --&gt;

        &lt;StackPanel Margin="10" HorizontalAlignment="Center" 											VerticalAlignment="Stretch"&gt;

            <TextBlock TextWrapping="Wrap">Specify and customize the group margin.&lt;/TextBlock&gt;

        &lt;/StackPanel&gt;

    &lt;/syncfusion:TaskBarItem&gt;

&lt;/syncfusion:TaskBar&gt;



[C#]



// To Collapse the TaskBarItem in TaskBar.

TaskBar.SetIsOpened(taskBar, false);





{ ![](Collapsing-the-TaskBar_images/Collapsing-the-TaskBar_img1.jpeg) | markdownify }
{:.image }




See Also

Expander Button Size

