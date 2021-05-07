---
layout: post
title: ToolBarManager in WPF ToolBar control | Syncfusion
description: Learn here all about ToolBarManager support in Syncfusion WPF ToolBar (ToolBarAdv) control and more.
platform: wpf
control: ToolBarAdv
documentation: ug
---

# ToolBarManager in WPF ToolBar (ToolBarAdv)

ToolBarManager is a container in which the ToolBarTrayAdv can place in top, bottom, left or right provided with the following properties.

* TopToolBarTray
* BottomToolBarTray
* LeftToolBarTray
* RightToolBarTray

And the content of the ToolBarManager will be displayed in the remaining space.

The following code illustrates how to place the ToolBarAdv at the top:

{% tabs %}

{% highlight XAML %}
<syncfusion:ToolBarManager x:Name="toolBarManager" >

<syncfusion:ToolBarManager.Resources>

<Style TargetType="Button">

<Setter Property="Height" Value="20" />

<Setter Property="Width" Value="20"/>

</Style>

<Style TargetType="ToggleButton">

<Setter Property="Height" Value="20"/>

<Setter Property="Width" Value="20"/>

</Style>

</syncfusion:ToolBarManager.Resources>

<syncfusion:ToolBarManager.TopToolBarTray>

<syncfusion:ToolBarTrayAdv >

<syncfusion:ToolBarAdv ToolBarName="Standard">

<Button>

<Image Source="Images/NewDocumentHS.png" Width="16" Height="16"/>

</Button>

<Button >

<Image Source="Images/openHS.png" Width="16" Height="16"/>

</Button>

</syncfusion:ToolBarAdv>

</syncfusion:ToolBarTrayAdv>

</syncfusion:ToolBarManager.TopToolBarTray>

</syncfusion:ToolBarManager>     



{% endhighlight %}

{% highlight C# %}

ToolBarAdv toolBar = new ToolBarAdv();

Button button = new Button();

button.Content = new Image() { Source = new BitmapImage() { UriSource = new Uri("Images/NewDocumentHS.png", UriKind.RelativeOrAbsolute) } };

toolBar.Items.Add(button);

button = new Button();

button.Content = new Image() { Source = new BitmapImage() { UriSource = new Uri("Images/openHS.png", UriKind.RelativeOrAbsolute) } };

toolBar.Items.Add(button);

ToolBarTrayAdv tray = new ToolBarTrayAdv();

tray.ToolBars.Add(toolBar);

ToolBarManager manager = new ToolBarManager();

manager.TopToolBarTray = tray;

Grid1.Children.Add(manager);





{% endhighlight %}

{% endtabs %}

