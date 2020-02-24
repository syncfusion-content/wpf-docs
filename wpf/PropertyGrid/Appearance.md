---
layout: post
title: Appearance in WPF PropertyGrid control | Syncfusion
description: Learn about Appearance support in Syncfusion WPF PropertyGrid control and more details about the control features.
platform: wpf
control: PropertyGrid 
documentation: ug
---

# Appearance in WPF PropertyGrid

This section explains different UI customization, styling, theming options available in [PropertyGrid](https://www.syncfusion.com/wpf-ui-controls/propertygrid) control.

## Setting the Foreground

We can change the foreground color for properties of [SelectedObject](https://help.syncfusion.com/cr/wpf/Syncfusion.PropertyGrid.Wpf~Syncfusion.Windows.PropertyGrid.PropertyGrid~SelectedObject.html) by setting the `Foreground` property. The default color value of `Foreground` property is `Blue`.

{% tabs %}
{% highlight xaml %}

<syncfusion:PropertyGrid Foreground="Red" x:Name="propertyGrid">
    <syncfusion:PropertyGrid.SelectedObject>
         <Button></Button>
    </syncfusion:PropertyGrid.SelectedObject>
</syncfusion:PropertyGrid>

{% endhighlight %}
{% highlight C# %}

PropertyGrid propertyGrid = new PropertyGrid();
propertyGrid.SelectedObject = new Button();
propertyGrid.Foreground = Brushes.Red;

{% endhighlight %}
{% endtabs %}

![PropertyGrid with Red foreground](Appearance_images/Appearance_Foreground.png)

## Setting the Background and FontWeight

We can change the background and font weight for all the properties by using the [ViewBackgroundColor](https://help.syncfusion.com/cr/wpf/Syncfusion.PropertyGrid.Wpf~Syncfusion.Windows.PropertyGrid.PropertyGrid~ViewBackgroundColor.html) and `FontWeight` properties.

{% tabs %}
{% highlight xaml %}

<syncfusion:PropertyGrid ViewBackgroundColor="Cyan" FontWeight="Bold" 
                         x:Name="propertyGrid">
    <syncfusion:PropertyGrid.SelectedObject>
        <Button></Button>
    </syncfusion:PropertyGrid.SelectedObject>
</syncfusion:PropertyGrid>

{% endhighlight %}
{% highlight C# %}

PropertyGrid propertyGrid = new PropertyGrid();
propertyGrid.SelectedObject = new Button();
propertyGrid.ViewBackgroundColor = Brushes.Cyan;
propertyGrid.FontWeight = FontWeights.Bold;
{% endhighlight %}
{% endtabs %}

![PropertyGrid with Cyan background and bold font](Appearance_images/Appearance_Background-Font.png)

### Background and FontWeight for the Editable and Readonly Properties

If we want to differentiate between editable and readonly properties, we can do this by using [EditableBackground](https://help.syncfusion.com/cr/wpf/Syncfusion.PropertyGrid.Wpf~Syncfusion.Windows.PropertyGrid.PropertyGrid~EditableBackground.html) and [EditableFontWeight](https://help.syncfusion.com/cr/wpf/Syncfusion.PropertyGrid.Wpf~Syncfusion.Windows.PropertyGrid.PropertyGrid~EditableFontWeight.html) properties to highlights the editable properties and use the [ReadOnlyBackground](https://help.syncfusion.com/cr/wpf/Syncfusion.PropertyGrid.Wpf~Syncfusion.Windows.PropertyGrid.PropertyGrid~ReadOnlyBackground.html) and [ReadOnlyFontWeight](https://help.syncfusion.com/cr/wpf/Syncfusion.PropertyGrid.Wpf~Syncfusion.Windows.PropertyGrid.PropertyGrid~ReadOnlyFontWeight.html) properties to highlights the readonly properties.

{% tabs %}
{% highlight C# %}

class Employee {
    public string EmployeeName { get; set; }
    [Editable(false)]
    public int EmployeeID { get; set; }     
    public int Age { get; set; }
    [ReadOnly(true)]
    public DateTime DOB { get; set; }
}

public class ViewModel {
    public Object SelectedEmployee { get; set; }
    public ViewModel() {
        SelectedEmployee = new Employee() 
        { 
            EmployeeName = "John", 
            DOB = new DateTime(1995, 01, 08), 
            Age=25, 
            EmployeeID = 036 
        };
    }
}

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight xaml %}

<syncfusion:PropertyGrid EditableBackground="LightGreen" EditableFontWeight="Bold"
                         ReadOnlyBackground="LightPink"  ReadOnlyFontWeight="UltraLight"
                         SelectedObject="{Binding SelectedEmployee}" x:Name="propertyGrid" >
    <syncfusion:PropertyGrid.DataContext>
        <local:ViewModel></local:ViewModel>
    </syncfusion:PropertyGrid.DataContext>
</syncfusion:PropertyGrid>

{% endhighlight %}
{% highlight C# %}

PropertyGrid propertyGrid = new PropertyGrid();
propertyGrid.DataContext = new ViewModel();
propertyGrid.SetBinding(PropertyGrid.SelectedObjectProperty, new Binding("SelectedEmployee"));
propertyGrid.EditableBackground = Brushes.LightGreen;
propertyGrid.EditableFontWeight = FontWeights.Bold;
propertyGrid.ReadOnlyBackground = Brushes.LightPink;
propertyGrid.ReadOnlyFontWeight = FontWeights.UltraLight;

{% endhighlight %}
{% endtabs %}

![Different Background and FontWeight applyed to the Editable and Readonly Properties](Appearance_images/Appearance_CustomBackground.png)

N> If you use `EditableBackground` or `ReadOnlyBackground` properties with `ViewBackgroundColor` property, `EditableBackground` and `ReadOnlyBackground` properties have higher priority.

N> If you use `EditableFontWeight` or `ReadOnlyFontWeight` properties with `FontWeight` property, `EditableFontWeight` and `ReadOnlyFontWeight` properties have higher priority.

## Category Header's foreground and background

We can change the background and foreground of the category header by setting the [LineColor](https://help.syncfusion.com/cr/wpf/Syncfusion.PropertyGrid.Wpf~Syncfusion.Windows.PropertyGrid.PropertyGrid~LineColor.html) property and [CategoryForeground](https://help.syncfusion.com/cr/wpf/Syncfusion.PropertyGrid.Wpf~Syncfusion.Windows.PropertyGrid.PropertyGrid~CategoryForeground.html) property. The `LineColor` property value applied to the background and `CategoryForeground` property value applied to the foreground of the category header only on category view. To enable category view, use the [EnableGrouping](https://help.syncfusion.com/cr/wpf/Syncfusion.PropertyGrid.Wpf~Syncfusion.Windows.PropertyGrid.PropertyGrid~EnableGrouping.html) property as `true`.


{% tabs %}
{% highlight xaml %}

<syncfusion:PropertyGrid LineColor="Cyan" CategoryForeground="Red"
                         x:Name="propertyGrid" >
    <syncfusion:PropertyGrid.SelectedObject>
        <Button></Button>
    </syncfusion:PropertyGrid.SelectedObject>
</syncfusion:PropertyGrid>

{% endhighlight %}
{% highlight C# %}

PropertyGrid propertyGrid = new PropertyGrid();
propertyGrid.SelectedObject = new Button();
propertyGrid.LineColor = Brushes.Cyan;
propertyGrid.CategoryForeground = Brushes.Red;

{% endhighlight %}
{% endtabs %}

![PropertyGrid with group header Red foreground and Cyan background](Appearance_images/Appearance_Groupheader.png)

## Setting ToolTip

ToolTip is used to show the information about the segment, when you mouse over on the segment. We can show information about the property name and type using tooltip when hovering the mouse on the properties and its value field. Tooltip is enabled by default, you can disable it by setting [EnableToolTip](https://help.syncfusion.com/cr/wpf/Syncfusion.PropertyGrid.Wpf~Syncfusion.Windows.PropertyGrid.PropertyGrid~EnableToolTip.html)  to `false`.

{% tabs %}
{% highlight XAML %}

<syncfusion:PropertyGrid EnableToolTip="False" x:Name="propertyGrid" >
    <syncfusion:PropertyGrid.SelectedObject>
        <Button></Button>
    </syncfusion:PropertyGrid.SelectedObject>
</syncfusion:PropertyGrid>

{% endhighlight %}
{% highlight C# %}

PropertyGrid propertyGrid = new PropertyGrid();
propertyGrid.SelectedObject = new Button();
propertyGrid.EnableToolTip = false;

{% endhighlight %}
{% endtabs %}

![PropertyGrid with tool tip and without tool tip](Appearance_images/Appearance_EnableToolTip.png)

Click [here](https://github.com/SyncfusionExamples/wpf-property-grid-examples/tree/master/Samples/PropertyGrid-Apperance) to download the sample that showcases the UI customization and styling support. 

## Theme

We can customize the appearance of the `PropertyGrid` control by using the [SfSkinManager.SetVisualStyle](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfSkinmanager.Wpf~Syncfusion.SfSkinmanager.SfSkinmanager~SetVisualStyle.html) method. The following are the various built-in visual styles for `PropertyGrid` control.

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

Here, the `Blend` style is applied to the `PropertyGrid`.

{% tabs %}
{% highlight xaml %}

<syncfusion:PropertyGrid syncfusionskin:SfSkinManager.VisualStyle="Blend" 
                         x:Name="propertyGrid" >
    <syncfusion:PropertyGrid.SelectedObject>
        <Button></Button>
    </syncfusion:PropertyGrid.SelectedObject>
</syncfusion:PropertyGrid>

{% endhighlight %}
{% highlight C# %}

// Namespace for the SfSkinManager.
using Syncfusion.SfSkinManager;
PropertyGrid propertyGrid = new PropertyGrid();
propertyGrid.SelectedObject = new Button();
SfSkinManager.SetVisualStyle(propertyGrid, VisualStyles.Blend);

{% endhighlight %}
{% endtabs %}

![PropertyGrid with Blend visual style](Appearance_images/Appearance_BlendTheme.png)

Click [here](https://github.com/SyncfusionExamples/wpf-property-grid-examples/tree/master/Samples/Themes) to download the sample that showcases the different theming support. 