---
layout: post
title: Appearance in WPF PropertyGrid control | Syncfusion
description: Learn about Appearance support in Syncfusion WPF PropertyGrid control and more details about the control features.
platform: wpf
control: PropertyGrid 
documentation: ug
---

# Appearance in WPF PropertyGrid

This section deals with the appearance of [PropertyGrid](https://www.syncfusion.com/wpf-ui-controls/propertygrid) control and contains the following topics.

## Setting the Foreground

The User can change the foreground color for properties of `PropertyGrid's` [SelectedObject](https://help.syncfusion.com/cr/wpf/Syncfusion.PropertyGrid.Wpf~Syncfusion.Windows.PropertyGrid.PropertyGrid~SelectedObject.html) by setting the `Foreground` property. The default color value of `Foreground` property is `Blue`.

{% tabs %}
{% highlight xaml %}

<syncfusion:PropertyGrid x:Name="propertyGrid" Width="350" Height="400"
                         Foreground="Red">
            <syncfusion:PropertyGrid.SelectedObject>
                <Button></Button>
            </syncfusion:PropertyGrid.SelectedObject>
</syncfusion:PropertyGrid>

{% endhighlight %}
{% highlight C# %}

PropertyGrid propertyGrid = new PropertyGrid();
propertyGrid.Width = 350;
propertyGrid.Height = 400;
propertyGrid.SelectedObject = new Button();
propertyGrid.Foreground = Brushes.Red;

{% endhighlight %}
{% endtabs %}

![PropertyGrid with Red foreground](Appearance_images/Appearance_Foreground.png)

## Setting the Background

The Users can change the background color for the properties of `PropertyGrid's` `SelectedObject` by setting the [ViewBackgroundColor](https://help.syncfusion.com/cr/wpf/Syncfusion.PropertyGrid.Wpf~Syncfusion.Windows.PropertyGrid.PropertyGrid~ViewBackgroundColor.html) property. The default color value of `ViewBackgroundColor` is `White`.

{% tabs %}
{% highlight xaml %}

<syncfusion:PropertyGrid x:Name="propertyGrid" Width="350" Height="400"
                         ViewBackgroundColor="Cyan">
            <syncfusion:PropertyGrid.SelectedObject>
                <Button></Button>
            </syncfusion:PropertyGrid.SelectedObject>
</syncfusion:PropertyGrid>

{% endhighlight %}
{% highlight C# %}

PropertyGrid propertyGrid = new PropertyGrid();
propertyGrid.Width = 350;
propertyGrid.Height = 400;
propertyGrid.SelectedObject = new Button();
propertyGrid.ViewBackgroundColor = Brushes.Cyan;

{% endhighlight %}
{% endtabs %}

![PropertyGrid with Cyan background](Appearance_images/Appearance_Background.png)

### Group Header's foreground and background

You can change the foreground and background of the Category Header by setting the [LineColor](https://help.syncfusion.com/cr/wpf/Syncfusion.PropertyGrid.Wpf~Syncfusion.Windows.PropertyGrid.PropertyGrid~LineColor.html) property and [CategoryForeground](https://help.syncfusion.com/cr/wpf/Syncfusion.PropertyGrid.Wpf~Syncfusion.Windows.PropertyGrid.PropertyGrid~CategoryForeground.html) property. The `LineColor` and `CategoryForeground` values applied to the foreground and background of the Category Header only on grouping state.


{% tabs %}
{% highlight xaml %}

<syncfusion:PropertyGrid x:Name="propertyGrid"  Width="350" 
                         LineColor="Cyan" CategoryForeground="Red">
    <syncfusion:PropertyGrid.SelectedObject>
        <Button></Button>
    </syncfusion:PropertyGrid.SelectedObject>
</syncfusion:PropertyGrid>

{% endhighlight %}
{% highlight C# %}

PropertyGrid propertyGrid = new PropertyGrid();
propertyGrid.Width = 350;
propertyGrid.Height = 400;
propertyGrid.SelectedObject = new Button();
propertyGrid.LineColor = Brushes.Cyan;
propertyGrid.CategoryForeground = Brushes.Red;

{% endhighlight %}
{% endtabs %}

![PropertyGrid with group header Red foreground and Cyan background](Appearance_images/Appearance_Groupheader.png)

## Setting ToolTip

ToolTips are used to show the information about the segment, when you mouse over on the segment. You can show or hide the tooltip for the properties in the `PropertyGrid` by handling [EnableToolTip](https://help.syncfusion.com/cr/wpf/Syncfusion.PropertyGrid.Wpf~Syncfusion.Windows.PropertyGrid.PropertyGrid~EnableToolTip.html) Property. The default value of `EnableToolTip` property is `true`.

{% tabs %}
{% highlight XAML %}

<syncfusion:PropertyGrid x:Name="propertyGrid"  Width="350"
                         EnableToolTip="False">
    <syncfusion:PropertyGrid.SelectedObject>
        <Button></Button>
    </syncfusion:PropertyGrid.SelectedObject>
</syncfusion:PropertyGrid>

{% endhighlight %}
{% highlight C# %}

PropertyGrid propertyGrid = new PropertyGrid();
propertyGrid.Width = 350;
propertyGrid.Height = 400;
propertyGrid.SelectedObject = new Button();
propertyGrid.EnableToolTip = false;

{% endhighlight %}
{% endtabs %}

![PropertyGrid with tool tip and without tool tip](Appearance_images/Appearance_EnableToolTip.png)

## Theme

The appearance of the `PropertyGrid` control can be customized by using the [SfSkinManager.SetVisualStyle](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfSkinmanager.Wpf~Syncfusion.SfSkinmanager.SfSkinmanager~SetVisualStyle.html) method. The following are the various built-in visual styles for `PropertyGrid` control.

* Blend
* Default
* Lime
* Metro
* Office2010Black
* Office2010Blue
* Office2010Silver
* Office2013DarkGray
* Office2013LightGray
* Office2013White
* Office2016Colorful
* Office2016DarkGray
* Office2016White
* Office365
* Saffron
* SystemTheme
* VisualStudio2013
* VisualStudio2015

For example, the `Blend` style applied to the `PropertyGrid` as shown in the following example code:

{% tabs %}
{% highlight C# %}

// Namespace for the SfSkinManager.

using Syncfusion.SfSkinManager;

{% endhighlight %}
{% endtabs %}


{% tabs %}
{% highlight C# %}

PropertyGrid propertyGrid = new PropertyGrid();
propertyGrid.Width = 350;
propertyGrid.Height = 400;
propertyGrid.SelectedObject = new Button();
SfSkinManager.SetVisualStyle(propertyGrid, VisualStyles.Blend);

{% endhighlight %}
{% endtabs %}

![PropertyGrid with Blend visual style](Appearance_images/Appearance_BlendTheme.png)

























