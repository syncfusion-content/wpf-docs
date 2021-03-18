layout: post
title: Create a preview of the entire content of the Diagram | syncfusion.
description: How to see the preview of the large Diagrams and to ease navigations within that Diagram and how to custimize the appearance and its behaviour?
platform: wpf
control: SfDiagram
documentation: ug
---

# Overview Control in WPF Diagram (SfDiagram)

Overview control is used to display a preview (overall view) of the entire content of a Diagram. This helps you to look overall picture of large diagram and easy to navigate (pan or zoom) to a particular position of the page.

## Usage scenario

When you work on a huge and complex diagram, you may not know the part where you are actually working, and navigating from one part to another might be difficult. To navigation, zoom out entire diagram and find where you are. This solution is not suitable when you need some frequent navigation.

Overview control solved this problem by displaying a preview (overall view) of the entire diagram with option to pan and zoom.

## Define overview

Overview control can be added to the application by dragging it from the toolbox and dropping it in Designer view. The required assembly references will be added automatically.

Steps to add Overview control manually in XAML:

1. Add the following required assembly reference to the project, `Syncfusion.SfDiagram.WPF`

2. Import Syncfusion WPF schema `http://schemas.syncfusion.com/wpf` or SfDiagram control namespace `Syncfusion.UI.Xaml.Diagram.Controls` in XAML page.

3. Declare Overview control in XAML page.

{% tabs %}
{% highlight xaml %}

<Window x:Class="UserInteraction_Overview.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:syncfusion="http://schemas.syncfusion.com/wpf"
        WindowStartupLocation="CenterScreen"
        Title="Overview" Height="720" Width="1200">
    
    <!--Initialize the overview control and bind the diagram control elements to overview-->
    <syncfusion:Overview Source="{Binding ElementName=diagram}" Height="300" Margin="0,25,0,0"/>

    <!--Initialize the SfDiagram-->
    <syncfusion:SfDiagram x:Name="diagram"/>
</Window>
	
{% endhighlight %}	
{% endtabs %}

![Overview](Overview-Control_images/Overview-Control_img1.png)

[View Sample in GitHub](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/Overview).

## ZoomSlider

The [ShowZoomSlider](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Controls.Overview.html#Syncfusion_UI_Xaml_Diagram_Controls_Overview_ShowZoomSliderProperty) property is used to show or hide the zoom slider in the overview control. By default, the ShowZoomSlider is true.

You can zoom in or zoom out the overview as well as the diagram by changing the slider or click on the zoom in or zoom out button.

 The following code example explains how to hide the zoom slider.

{% tabs %}
{% highlight xaml %}

<Window x:Class="UserInteraction_Overview.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:syncfusion="http://schemas.syncfusion.com/wpf"
        WindowStartupLocation="CenterScreen"
        Title="Overview" Height="720" Width="1200">
    
    <!--Initialize the overview control and bind the diagram control elements to overview-->
    <syncfusion:Overview Source="{Binding ElementName=diagram}" Height="300" Margin="0,25,0,0" ShowZoomSlider="False"/>

    <!--Initialize the SfDiagram-->
    <syncfusion:SfDiagram x:Name="diagram"/>
</Window>
	
{% endhighlight %}	
{% endtabs %}

![Overview](Overview-Control_images/Overview-Control_img.png)


## Interaction

Overview control allows Zoom and Pan interactions. The red rectangle indicates the area currently displayed on the diagram page. The red box can be moved within the panel to pan around the diagram. You can click and drag the corner of the rectangle to change the level of zooming on the diagram page or you can draw a new rectangle by clicking and dragging anywhere within the panel to zoom an area.

{% tabs %}
{% highlight xaml %}

<!--Initialize the overview control with its constraint-->
<syncfusion:Overview Source="{Binding ElementName=diagram}" 
                     Constraint="Default" 
                     Height="300" Margin="0,25,0,0"/>

<!--Initialize the SfDiagram-->
<syncfusion:SfDiagram x:Name="diagram"/>

{% endhighlight %}	
{% endtabs %}

The [Constraint](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Controls.Overview.html#Syncfusion_UI_Xaml_Diagram_Controls_Overview_ConstraintProperty) property of the Overview class allows you to control the Pan and Zoom interactions based the value assigned to that property. The following table explains the various values and their behaviors:

| OverviewConstraints | Description | Output |
|---|---|---|
| Pan | Allows users to pan the diagram page by dragging the focused rectangle. |![Overview pan](Overview-Control_images/OverViewPan.gif) |
| Zoom | Allows users to perform zoom by resizing the corners of the focused rectangle. |![Overview Resize](Overview-Control_images/OverViewResize.gif) |
| DrawFocus | Allows users to draw new focused rectangle anywhere within the overview panel, that is corresponding region in the diagram will be brought into the view.|![Overview Draw](Overview-Control_images/OverViewDrawFocus.gif) |
| TapFocus | Allows users move the focused rectangle to any area within the panel by just tapping it.| |
| Default | Allows users to perform drag, resize, draw, and tap the overview control.| |
| None |No interaction can be performed on the focused rectangle.||

## Deferred scrolling

Diagram supports the deferred scrolling behaviour to improve the zoom and pan performances.

To learn more about deferred scrolling, refer to [Deferred Scrolling](/wpf/diagram/virtualization#deferred-scrolling "DeferredScrolling").

## Event

The `OverviewChangedEvent` will notify the interactions in Overview control with [OverviewChangedEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Controls.OverviewChangedEventArgs.html) as argument. This argument will provide the dragging and interaction state value of the overview.

{% seealso %}

[How to virtualize the diagram control](/wpf/sfdiagram/virtualization)

[How to serialize the diagram control](/wpf/sfdiagram/serialization)

[How to localize the diagram control](/wpf/sfdiagram/localization)

{% endseealso %}