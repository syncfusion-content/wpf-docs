---
layout: post
title: Setting-Group-Padding
description: setting group padding
platform: wpf
control: TaskBar
documentation: ug
---

# Setting Group Padding

You can set the padding for the TaskBar Items by using the GroupPadding property. This is an attached property, which sets the padding for adjusting the TaskBarItems by using the SetGroupPadding method. You can enhance the appearance of the content in the taskbar items by using this property.

You can also set the value for Left, Right, Bottom and Top group padding.

To set the group padding, use the below code



[XAML]



&lt;!-- Adding TaskBar that have group padding as 20 --&gt;

&lt;syncfusion:TaskBar Name="taskBar" GroupMargin="5" 												syncfusion:TaskBar.GroupPadding="20"&gt;



    &lt;!-- Adding TaskBarItem --&gt;

    &lt;syncfusion:TaskBarItem Name="taskBarItem1" Header="TaskBarItem1"&gt;



        &lt;!-- Adding content to taskbaritem --&gt;

        &lt;StackPanel Margin="10" HorizontalAlignment="Center" VerticalAlignment="Stretch"&gt;

            <TextBlock TextWrapping="Wrap">This taskbar provides an UI similar to that of Windows XP.&lt;/TextBlock&gt;

        &lt;/StackPanel&gt;

    &lt;/syncfusion:TaskBarItem&gt;



    &lt;!-- Adding TaskBarItem --&gt;

    &lt;syncfusion:TaskBarItem Name="taskBarItem2" Header="TaskBarItem2"&gt;



        &lt;!-- Adding content to TaskBarItem --&gt;

        &lt;StackPanel Margin="10" HorizontalAlignment="Center" 											VerticalAlignment="Stretch"&gt;

            <TextBlock TextWrapping="Wrap">Specify and customize the group 	margin.&lt;/TextBlock&gt;

        &lt;/StackPanel&gt;

    &lt;/syncfusion:TaskBarItem&gt;

&lt;/syncfusion:TaskBar&gt;





[C#]



//Setting group padding for TaskBar

TaskBar.SetGroupPadding(taskBar, new Thickness(20));





{ ![](Setting-Group-Padding_images/Setting-Group-Padding_img1.jpeg) | markdownify }
{:.image }




See Also

TaskBar Item Header Image

