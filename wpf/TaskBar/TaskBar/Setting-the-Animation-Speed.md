---
layout: post
title: Setting the Animation Speed | TaskBar | wpf | Syncfusion
description: setting the animation speed
platform: wpf
control: TaskBar
 documentation: ug
---

# Setting the Animation Speed

You can set the animation speed, which controls the time taken to expand or collapse the taskbar items in the TaskBar, using the Speed property. This is an attached property, which controls the time taken to expand or collapse the TaskBarItems in the TaskBar by using the SetSpeed method.

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

This method is used to get the animation speed, which controls the time taken to expand or collapse the TaskBarItems in the TaskBar. It has one argument, which returns the speed value of type, double.


{% highlight c# %}



double speed;

//Getting speed

speed = TaskBar.GetSpeed(taskBar);

{% endhighlight %}



### SetSpeed

This method is used to set the animation speed, which controls the time taken to expand or collapse the TaskBarItems in the TaskBar. It has two arguments. The first argument specifies the object, while the second argument specifies the value of speed of type double.


{% highlight c# %}



//Setting the speed

TaskBar.SetSpeed(taskBar, 10);

{% endhighlight %}

