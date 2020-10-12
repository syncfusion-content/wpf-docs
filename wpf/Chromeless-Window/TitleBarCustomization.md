---
layout: post
title: Title bar Customization | ChromelessWindow | WPF | Syncfusion
description: This section briefly describes the various customizations such as background, height, font size and much more in Title bar in Syncfusion's Chromeless Window
platform: wpf
control: ChromelessWindow
documentation: ug
---
# Title bar Customization

## Customizing the background
 
 The [`TitleBarBackground`](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.ChromelessWindow.html#Syncfusion_Windows_Shared_ChromelessWindow_TitleBarBackground) property can be used to set the background for the Title bar.
 
 {% tabs %}
 
 {% highlight XAML %}
 
 <syncfusion:ChromelessWindow x:Class="Chromelesswindow.MainWindow"
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
  Title="MainWindow" Height="350" Width="525"  TitleBarBackground="Red"   x:Name="_chromelessWindow"  
  syncfusion:SkinStorage.VisualStyle="Metro"  
  xmlns:syncfusion="clr-namespace:Syncfusion.Windows.Shared;assembly=Syncfusion.Shared.WPF" >
  <Grid>
  </Grid>
 </syncfusion:ChromelessWindow>
 
 {% endhighlight %}
 
 {% highlight c# %}
 
 this.TitleBarBackground = new SolidColorBrush(Colors.Red);
 
 {% endhighlight %}
 
 {% highlight VB %}
 
 Me.TitleBarBackground = New SolidColorBrush(Colors.Red)
 
 {% endhighlight %}
 
 {% endtabs %}
 
 The following screen shots illustrate the title bar background changes.
 
 ![Setting title bar background](TitleBarBackground_images/TitleBarBackground_img1.jpeg)
 
## Customizing the height
 
 The [`TitleBarHeight`](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.ChromelessWindow.html#Syncfusion_Windows_Shared_ChromelessWindow_TitleBarHeight) property can be used to change the height of the Title bar. The default value is `30`. 
  
 {% tabs %}
 
 {% highlight XAML %}
 
 <syncfusion:ChromelessWindow x:Class="Chromelesswindow.MainWindow"
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
  Title="ChromelessWindow" Height="350" Width="525" TitleBarHeight="60" TitleBarBackground="Pink" 
  syncfusion:SkinStorage.VisualStyle="Metro"  x:Name="_chromelessWindow"  
  xmlns:syncfusion="clr-namespace:Syncfusion.Windows.Shared;assembly=Syncfusion.Shared.WPF" >
  <Grid>
  </Grid>
 </syncfusion:ChromelessWindow>
 
 {% endhighlight %}
 
 {% highlight c# %}
 
 this.TitleBarHeight = 60;
 
 {% endhighlight %}
 
 {% highlight VB %}
 
   Me.TitleBarHeight = 60
   
 {% endhighlight %}
 
 {% endtabs %}
 
 ![Setting title bar height](TitleBarHeight-Support_images/TitleBarHeight-Support_img1.jpeg)

## Customizing  the font size

 The font size of the ChromelessWindow title bar can be changed by using [`TitleFontSize`](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.ChromelessWindow.html#Syncfusion_Windows_Shared_ChromelessWindow_TitleFontSize) property. The default value is `12`.

 {% tabs %}

 {% highlight XAML %}

 <syncfusion:ChromelessWindow x:Class="Chromelesswindow.MainWindow"
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
  Title="ChromelessWindow" Height="350" Width="525" TitleFontSize="25" syncfusion:SkinStorage.VisualStyle="Metro"     
  x:Name="_chromelessWindow" xmlns:syncfusion="clr-namespace:Syncfusion.Windows.Shared;assembly=Syncfusion.Shared.WPF" >
  <Grid>
  </Grid>
 </syncfusion:ChromelessWindow>

 {% endhighlight %}
 
 {% highlight c# %}
 
 this.TitleFontSize = 25;
 
 {% endhighlight %}
 
 {% highlight VB %}
 
 Me.TitleFontSize = 25
 
 {% endhighlight %}
 
 {% endtabs %}
 
 ![Setting font size for the title bar text](ChromelessWindow-TitleFontSize-Support_images/ChromelessWindow-TitleFontSize-Support_img1.jpeg)

## Show or hide the title bar text

 The visibility of the title can be customized using the [`ShowTitle`](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.ChromelessWindow.html#Syncfusion_Windows_Shared_ChromelessWindow_ShowTitle) property. The default value of `ShowTitle` property is true.

 {% tabs %}
 {% highlight XAML %}
 <syncfusion:ChromelessWindow x:Class="Chromeless_Window_Sample.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:Chromeless_Window_Sample"
        mc:Ignorable="d" xmlns:syncfusion="http://schemas.syncfusion.com/wpf"
        xmlns:skin="clr-namespace:Syncfusion.SfSkinManager;assembly=Syncfusion.SfSkinManager.WPF"
        skin:SfSkinManager.VisualStyle="Office2019Colorful"
        TitleTextAlignment="Center"
        Icon="App.ico"
        ShowTitle="False" 
        Title="Getting Started"
        Height="350" Width="550">
    <Grid>
    </Grid>
 </syncfusion:ChromelessWindow>
 {% endhighlight %}
 {% endtabs %}

 ![Show or hide the title bar text](Getting-Started_images/ShowTitle.PNG)
 
## Show or hide the title bar icon

The visibility of the title bar icon can be customized using the [`ShowIcon`](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.ChromelessWindow.html#Syncfusion_Windows_Shared_ChromelessWindow_ShowIcon) property. The default value of `ShowIcon` property is true.

{% tabs %}
{% highlight XAML %}
<syncfusion:ChromelessWindow x:Class="Chromeless_Window_Sample.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:Chromeless_Window_Sample"
        mc:Ignorable="d" xmlns:syncfusion="http://schemas.syncfusion.com/wpf"
        xmlns:skin="clr-namespace:Syncfusion.SfSkinManager;assembly=Syncfusion.SfSkinManager.WPF"
        skin:SfSkinManager.VisualStyle="Office2019Colorful"
        TitleTextAlignment="Center"
        Icon="App.ico"
        ShowIcon="False" 
        Title="Getting Started"
        Height="350" Width="550">
    <Grid>
    </Grid>
</syncfusion:ChromelessWindow>
{% endhighlight %}
{% endtabs %}

![Show or hide the title bar icon](Getting-Started_images/ShowIcon.PNG)

## Show or hide the maximize and minimize buttons

 The visibility of maximize and minimize buttons can be customized using the [`ShowMaximizeButton`](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.ChromelessWindow.html#Syncfusion_Windows_Shared_ChromelessWindow_ShowMaximizeButton) and [`ShowMinimizeButton`](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.ChromelessWindow.html#Syncfusion_Windows_Shared_ChromelessWindow_ShowMinimizeButton) properties respectively. The default value of `ShowMaximizeButton` and `ShowMinimizeButton` properties are true. 

 N> By default, the maximize and minimize buttons will not be displayed in ResizeMode -`NoResize` even when the value of `ShowMaximizeButton` and `ShowMaximizeButton` set as `True`. The maximize and minimize buttons will be displayed only in the remaining resize modes such as `CanMinimize`, `CanResize`, `CanResizeWithGrip` based on the `ShowMaximizeButton` and `ShowMinimizeButton` properties.

 {% tabs %}
{% highlight XAML %}
<syncfusion:ChromelessWindow x:Class="Chromeless_Window_Sample.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:Chromeless_Window_Sample"
        mc:Ignorable="d" xmlns:syncfusion="http://schemas.syncfusion.com/wpf"
        xmlns:skin="clr-namespace:Syncfusion.SfSkinManager;assembly=Syncfusion.SfSkinManager.WPF"
        skin:SfSkinManager.VisualStyle="Office2019Colorful"
        TitleTextAlignment="Center"
        Icon="App.ico"
        ShowMinimizeButton="False"
        ShowMaximizeButton="False" 
        Title="Getting Started"
        Height="350" Width="550">
    <Grid>
    </Grid>
</syncfusion:ChromelessWindow>
{% endhighlight %}
{% endtabs %}

![Show or hide the maximize and minimize buttons](Getting-Started_images/MaximizeMinimizeButton.PNG)
