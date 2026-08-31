---
layout: post
title: ToolBarManager in WPF ToolBarAdv  | Syncfusion®
description: ToolBarManager in WPF ToolBarAdv  enables placing ToolBarTrayAdv containers on different sides of a layout and managing toolbar content efficiently.
platform: wpf
control: ToolBarAdv 
documentation: ug
---

# ToolBarManager in WPF ToolBar

ToolBarManager is a container in which a ToolBarTrayAdv can be placed at the top, bottom, left, or right using the following properties.

* `TopToolBarTray`
* `BottomToolBarTray`
* `LeftToolBarTray`
* `RightToolBarTray`

The `Content` of the ToolBarManager is displayed in the remaining space between the trays.

The following code illustrates how to place a ToolBar at the top of a ToolBarManager.

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
