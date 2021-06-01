---
layout: post
title: ReadOnly Properties in WPF PropertyGrid control | Syncfusion
description: Learn about ReadOnly Properties support in Syncfusion Essential Studio WPF PropertyGrid control, its elements and more.
platform: wpf
control: PropertyGrid 
documentation: ug
---

# ReadOnly Properties in WPF PropertyGrid

We can display the readonly properties with its value editor in the non editable state by default. If we want to change any property as readonly, it can be achieved by attributes and event in the [PropertyGrid](https://www.syncfusion.com/wpf-ui-controls/propertygrid).

## ReadOnly properties using attributes

We can change the properties as read only by using the [ReadOnly](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.readonlyattribute?view=netframework-4.8) or [Editable](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.dataannotations.editableattribute?view=netframework-4.8) attributes. When the property is marked `ReadOnly` as `true` or `Editable` as `false`, the [PropertyGrid](https://www.syncfusion.com/wpf-ui-controls/propertygrid) will not allow the user to edit the property values.

{% tabs %}
{% highlight C# %}

public class Employee {
    public string Name { get; set; }
    public string ID { get; set; }
    [ReadOnly(true)]
    public DateTime DOB { get; set; }
    [Editable(false)]
    public int Experience { get; set; }
}

public class ViewModel {
    public object SelectedEmployee { get; set; }    
    public ViewModel() {
        SelectedEmployee = new Employee()
        {
            Name = "John",
            ID = "381",
            DOB = new DateTime(1995, 12, 24),
            Experience = 5;
        };
    }
}

{% endhighlight %} 
{% endtabs %}

{% tabs %}
{% highlight xaml %}

<syncfusion:PropertyGrid SelectedObject="{Binding SelectedEmployee}" SortDirection="{x:Null}"    
                         x:Name="propertyGrid1">
    <syncfusion:PropertyGrid.DataContext>
        <local:ViewModel></local:ViewModel>
    </syncfusion:PropertyGrid.DataContext>
</syncfusion:PropertyGrid>

{% endhighlight %} 
{% highlight C# %}

PropertyGrid propertyGrid1 = new PropertyGrid();
propertyGrid1.DataContext = new ViewModel();
propertyGrid1.SetBinding(PropertyGrid.SelectedObjectProperty, new Binding("SelectedEmployee")); 
propertyGrid1.SortDirection = null;

{% endhighlight %} 
{% endtabs %} 


Here, the `DOB` and `Experience` are readonly properties by the attributes.

![DOB and Experience is not editable in PropertyGrid](Attribute-Images\ReadOnly-Editable-Attribute.png)

N> If you use both the `ReadOnly` attribute and `Editable` attribute, the `ReadOnly` attribute will have higher priority.

Click [here](https://github.com/SyncfusionExamples/wpf-property-grid-examples/tree/master/Samples/ReadOnlyProperty) to download the sample that showcases the `ReadOnly` support using attribute.

## Change properties as readonly at runtime

We can change the properties as read only without using the attributes at runtime by handling the [AutoGeneratingPropertyGridItem](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PropertyGrid.PropertyGrid.html)  event with [AutoGeneratingPropertyGridItemEventArgs.ReadOnly](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PropertyGrid.AutoGeneratingPropertyGridItemEventArgs.html#Syncfusion_Windows_PropertyGrid_AutoGeneratingPropertyGridItemEventArgs_ReadOnly) property.

When `AutoGeneratingPropertyGridItemEventArgs.ReadOnly` property value sets as `true`, the property will be classified as read only, then the `PropertyGrid` will not allow the user to edit the property values. The Default value of `AutoGeneratingPropertyGridItemEventArgs.ReadOnly` property is `false`.

{% tabs %}
{% highlight C# %}

using System;
using System.ComponentModel;
using System.ComponentModel.DataAnnotations;

public class Employee {
    public string Name { get; set; }
    public string ID { get; set; }
    public DateTime DOB { get; set; }
    public int Experience { get; set; }
}

public class ViewModel {
    public object SelectedEmployee { get; set; }

    public ViewModel() {
        SelectedEmployee = new Employee()
        {
            Name = "John",
            ID = "381",
            DOB = new DateTime(1995, 12, 24),
            Experience = 5;
        };
    }
}

{% endhighlight %} 
{% endtabs %} 

{% tabs %}
{% highlight xaml %}

<syncfusion:PropertyGrid AutoGeneratingPropertyGridItem="PropertyGrid1_AutoGeneratingPropertyGridItem"
                         SelectedObject="{Binding SelectedEmployee}"
                         x:Name="propertyGrid1">
    <syncfusion:PropertyGrid.DataContext>
        <local:ViewModel></local:ViewModel>
    </syncfusion:PropertyGrid.DataContext>
</syncfusion:PropertyGrid>

{% endhighlight %} 
{% highlight C# %}

PropertyGrid propertyGrid1 = new PropertyGrid();
propertyGrid1.DataContext = new ViewModel();
propertyGrid1.SetBinding(PropertyGrid.SelectedObjectProperty, new Binding("SelectedEmployee"));
propertyGrid1.AutoGeneratingPropertyGridItem += PropertyGrid1_AutoGeneratingPropertyGridItem;

{% endhighlight %} 
{% endtabs %} 

{% tabs %}
{% highlight C# %}

private void PropertyGrid1_AutoGeneratingPropertyGridItem(object sender, AutoGeneratingPropertyGridItemEventArgs e) {
    // Change 'DOB' property as readonly
    if (e.DisplayName == "DOB") {
        e.ReadOnly = true;
    }
}

{% endhighlight %} 
{% endtabs %}

![DOB is not editable in PropertyGrid](Attribute-Images\ReadOnly-Editable-Attribute.png)

Here, the `DOB` property non-editable.

Click [here](https://github.com/SyncfusionExamples/wpf-property-grid-examples/tree/master/Samples/AutoGeneratingPropertyGridItem%20event) to download the sample that showcases the `ReadOnly` support using `AutoGeneratingPropertyGridItem` event.
