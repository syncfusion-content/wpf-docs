---
layout: post
title: Changing-the-size-of-Expander-Button
description: changing the size of expander button
platform: wpf
control: TaskBar
documentation: ug
---

# Changing the size of Expander Button

You can change the size of the Expander button in the TaskBar control. This is achieved by using the ButtonSize attached property, which sets the height of the Expander button in the TaskBar by handling the SetButtonSize method.

To set the size of the Expander button, use the below code



[XAML]



&lt;!-- Adding TaskBar that have button size is 20 --&gt;

&lt;syncfusion:TaskBar Name="taskBar" GroupMargin="5" syncfusion:TaskBar.ButtonSize="20"&gt;

    &lt;!-- Adding TaskBarItem --&gt;

    &lt;syncfusion:TaskBarItem Name="taskBarItem1" Header="TaskBarItem1"&gt;

        &lt;!-- Adding content to taskbaritem --&gt;

        &lt;StackPanel Margin="10" HorizontalAlignment="Center" 											VerticalAlignment="Stretch"&gt;

            <TextBlock TextWrapping="Wrap">This taskbar provides an UI similar to that of Windows XP.&lt;/TextBlock&gt;

        &lt;/StackPanel&gt;

    &lt;/syncfusion:TaskBarItem&gt;

    &lt;!-- Adding TaskBarItem --&gt;

    &lt;syncfusion:TaskBarItem Name="taskBarItem2" Header="TaskBarItem2"&gt;

        &lt;!-- Adding content to taskbaritem --&gt;

        &lt;StackPanel Margin="10" HorizontalAlignment="Center" 											VerticalAlignment="Stretch"&gt;

            <TextBlock TextWrapping="Wrap">Specify and customize the group margin.&lt;/TextBlock&gt;

        &lt;/StackPanel&gt;

    &lt;/syncfusion:TaskBarItem&gt;

&lt;/syncfusion:TaskBar&gt;





[C#]



// Setting button size

TaskBar.SetButtonSize(taskBar, 20);





{ ![](Changing-the-size-of-Expander-Button_images/Changing-the-size-of-Expander-Button_img1.jpeg) | markdownify }
{:.image }




See Also

Collapsing the TaskBar

