---
layout: post
title: Setting Group Padding | TaskBar | wpf | Syncfusion
description: setting group padding
platform: wpf
control: TaskBar
 documentation: ug
---

# Setting Group Padding

You can set the padding for the TaskBar Items by using the GroupPadding property. This is an attached property, which sets the padding for adjusting the TaskBarItems by using the SetGroupPadding method. You can enhance the appearance of the content in the taskbar items by using this property.

You can also set the value for Left, Right, Bottom and Top group padding.

To set the group padding, use the below code

{%tabs%}
{% highlight xaml %}



<!-- Adding TaskBar that have group padding as 20 -->

<syncfusion:TaskBar Name="taskBar" GroupMargin="5" 												syncfusion:TaskBar.GroupPadding="20">



    <!-- Adding TaskBarItem -->

    <syncfusion:TaskBarItem Name="taskBarItem1" Header="TaskBarItem1">



        <!-- Adding content to taskbaritem -->

        <StackPanel Margin="10" HorizontalAlignment="Center" VerticalAlignment="Stretch">

            <TextBlock TextWrapping="Wrap">This taskbar provides an UI similar to that of Windows XP.</TextBlock>

        </StackPanel>

    </syncfusion:TaskBarItem>



    <!-- Adding TaskBarItem -->

    <syncfusion:TaskBarItem Name="taskBarItem2" Header="TaskBarItem2">



        <!-- Adding content to TaskBarItem -->

        <StackPanel Margin="10" HorizontalAlignment="Center" 											VerticalAlignment="Stretch">

            <TextBlock TextWrapping="Wrap">Specify and customize the group 	margin.</TextBlock>

        </StackPanel>

    </syncfusion:TaskBarItem>

</syncfusion:TaskBar>

{% endhighlight %}


{% highlight c# %}



//Setting group padding for TaskBar

TaskBar.SetGroupPadding(taskBar, new Thickness(20));

{% endhighlight %}
{%endtabs%}


![](Setting-Group-Padding_images/Setting-Group-Padding_img1.jpeg)




{%seealso%}

TaskBar Item Header Image
{%endseealso%}
