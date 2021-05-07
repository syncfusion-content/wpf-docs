---
layout: post
title: Setting the Animation Speed in WPF TaskBar control | Syncfusion
description: Learn about Setting the Animation Speed support in Syncfusion WPF TaskBar control and more.
platform: wpf
control: TaskBar
documentation: ug
---

# Setting the Animation Speed in WPF TaskBar

You can set the animation speed, which controls the time taken to expand or collapse the taskbar items in the TaskBar, using the [Speed](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.TaskBar.html#Syncfusion_Windows_Tools_Controls_TaskBar_SpeedProperty) property. This is an attached property, which controls the time taken to expand or collapse the TaskBarItems in the TaskBar by using the SetSpeed method.

Use the following code snippet to set this property.

{%tabs%}
{% highlight xaml %}



<!-- Adding TaskBar that have animation speed as 10 -->

<syncfusion:TaskBar Name="taskBar" GroupMargin="5" syncfusion:TaskBar.Speed="10">



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



// Setting the speed

TaskBar.SetSpeed(taskBar, 10);
{% endhighlight %}


{%endtabs%}

## Methods handled with Speed Property

### GetSpeed

This [GetSpeed](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.TaskBar.html#Syncfusion_Windows_Tools_Controls_TaskBar_GetSpeed_System_Windows_DependencyObject_) method is used to get the animation speed, which controls the time taken to expand or collapse the TaskBarItems in the TaskBar. It has one argument, which returns the speed value of type, double.


{% highlight c# %}



double speed;

//Getting speed

speed = TaskBar.GetSpeed(taskBar);

{% endhighlight %}



### SetSpeed

This [SetSpeed](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.TaskBar.html#Syncfusion_Windows_Tools_Controls_TaskBar_SetSpeed_System_Windows_DependencyObject_System_Double_) method is used to set the animation speed, which controls the time taken to expand or collapse the TaskBarItems in the TaskBar. It has two arguments. The first argument specifies the object, while the second argument specifies the value of speed of type double.


{% highlight c# %}



//Setting the speed

TaskBar.SetSpeed(taskBar, 10);

{% endhighlight %}

