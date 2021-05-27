---
layout: post
title: Setting Header Image in WPF TaskBar Control | Syncfusion
description: Learn here about Setting Header Image in Syncfusion Essential Studio WPF TaskBar Control, its elements and more.
platform: wpf
control: TaskBar
documentation: ug
---

# Setting Header Image in WPF TaskBar Control

You can set a custom header image for the TaskBarItem. Use the following code snippet to set an image for the header.

{% highlight xaml %}



<!-- Adding TaskBar that have group orientation as horizontal -->

<syncfusion:TaskBar Name="taskBar" GroupMargin="5">



    <!-- Adding TaskBarItem -->

    <syncfusion:TaskBarItem Name="taskBarItem1">



        <!-- Adding header with image -->

        <syncfusion:TaskBarItem.Header>

            <DockPanel Margin="0">

                <Image Height="16" Width="16" Source="App.ico"/>

                <TextBlock Foreground="White" Margin="5,0,0,0" 												Text="Header"/>				

</DockPanel>

        </syncfusion:TaskBarItem.Header>



        <!-- Adding content to taskbaritem -->

        <StackPanel Margin="10" HorizontalAlignment="Center" 											VerticalAlignment="Stretch">

            <TextBlock TextWrapping="Wrap">This taskbar provides an UI similar to that of Windows XP.</TextBlock>

        </StackPanel>

    </syncfusion:TaskBarItem>

</syncfusion:TaskBar>
{% endhighlight %}


![Setting-Header-Image_images1](Setting-Header-Image_images/Setting-Header-Image_img1.jpeg)




{%seealso%}

Group Padding for the TaskBar Item

{%endseealso%}

