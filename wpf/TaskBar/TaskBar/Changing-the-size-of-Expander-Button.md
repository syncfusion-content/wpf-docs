---
layout: post
title: Changing the size of Expander Button | TaskBar | wpf | Syncfusion
description: changing the size of expander button
platform: wpf
control: TaskBar
 documentation: ug
---

# Changing the size of Expander Button

You can change the size of the Expander button in the TaskBar control. This is achieved by using the ButtonSize attached property, which sets the height of the Expander button in the TaskBar by handling the SetButtonSize method.

To set the size of the Expander button, use the below code

{%tabs%}
{% highlight xaml %}



<!-- Adding TaskBar that have button size is 20 -->

<syncfusion:TaskBar Name="taskBar" GroupMargin="5" syncfusion:TaskBar.ButtonSize="20">

    <!-- Adding TaskBarItem -->

    <syncfusion:TaskBarItem Name="taskBarItem1" Header="TaskBarItem1">

        <!-- Adding content to taskbaritem -->

        <StackPanel Margin="10" HorizontalAlignment="Center" 											VerticalAlignment="Stretch">

            <TextBlock TextWrapping="Wrap">This taskbar provides an UI similar to that of Windows XP.</TextBlock>

        </StackPanel>

    </syncfusion:TaskBarItem>

    <!-- Adding TaskBarItem -->

    <syncfusion:TaskBarItem Name="taskBarItem2" Header="TaskBarItem2">

        <!-- Adding content to taskbaritem -->

        <StackPanel Margin="10" HorizontalAlignment="Center" 											VerticalAlignment="Stretch">

            <TextBlock TextWrapping="Wrap">Specify and customize the group margin.</TextBlock>

        </StackPanel>

    </syncfusion:TaskBarItem>

</syncfusion:TaskBar>
{% endhighlight %}



{% highlight c# %}



// Setting button size

TaskBar.SetButtonSize(taskBar, 20);

{% endhighlight %}

{%endtabs%}

![](Changing-the-size-of-Expander-Button_images/Changing-the-size-of-Expander-Button_img1.jpeg)





{%seealso%}

Collapsing the TaskBar

{%endseealso%}

