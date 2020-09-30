---
layout: post
title: Description settings in WPF PropertyGrid control | Syncfusion
description: This section explains how a description of the property item has been added through attributes in the WPF PropertyGrid control.
platform: wpf
control: PropertyGrid 
documentation: ug
---

# Describe the Properties

You can display the description about the property using the  description panel which is placed on the bottom of the [PropertyGrid](https://www.syncfusion.com/wpf-ui-controls/propertygrid) control. Description panel visibility can be managed by [DescriptionPanelVisibility](https://help.syncfusion.com/cr/wpf/Syncfusion.PropertyGrid.Wpf~Syncfusion.Windows.PropertyGrid.PropertyGrid~DescriptionPanelVisibility.html) property . The default value of the `DescriptionPanelVisibility` is `Collapsed`. To display the description panel, you should set `DescriptionPanelVisibility`  property value as `Visible`.

## Property Description using attributes

We can give a meaningful description about the properties by using the [Description](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.descriptionattribute?view=netframework-4.8) attribute and [Display](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.dataannotations.displayattribute?view=netframework-4.8) attribute's [Description](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.dataannotations.displayattribute.description?view=netframework-4.8) field. This description will be displayed in `PropertyGrid` Description panel while focusing the property or its value editor.


{% tabs %}
{% highlight C# %}

using System;
using System.ComponentModel;
using System.ComponentModel.DataAnnotations;

public class Employee {
    [Display(Description = "Name of the employee")]
    public string Name { get; set; }
    public string ID { get; set; }
    [Description("Birth date of the employee")]
    public DateTime DOB { get; set; }
}

public class ViewModel {
    public Object SelectedEmployee { get; set; }
    public ViewModel() {
        SelectedEmployee = new Employee()
        {
            Name = "John",
            ID = "381",
            DOB = new DateTime(1995, 12, 24)
        };
    }
}
      
{% endhighlight %}
{% endtabs %} 

{% tabs %}
{% highlight xaml %}

<syncfusion:PropertyGrid DescriptionPanelVisibility="Visible" 
                         DescriptionPanelHeight="50"
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
propertyGrid1.DescriptionPanelVisibility = Visibility.Visible;
propertyGrid1.DescriptionPanelHeight = new GridLength(50);

{% endhighlight %} 
{% endtabs %} 

![Value specified in the Description field of the Display attribute is displayed in the Description Panel](Attribute-Images\Display-Description-Attribute.png)

Here, the description about the `Name` property  is displayed by using the `Display` attribute's `Description` field.

![Value specified in the Description attribute is displayed in the Description Panel](Attribute-Images\Description-Attribute.png)

Here, the description about the `DOB` property  is displayed by using the `Description` attribute.

N> If you use both the `Description` attribute and `Description` field of the `Display` attribute, the `Description` attribute will have higher priority.

N> The Display attribute is contained in the [System.ComponentModel.Annotations.dll](https://www.nuget.org/packages/System.ComponentModel.Annotations/) assembly.

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/wpf-property-grid-examples/tree/master/Samples/Name-Description)

## Change Property Description at runtime

We can set the property description without using the attributes and can change the property description at runtime by handling the [AutoGeneratingPropertyGridItem](https://help.syncfusion.com/cr/wpf/Syncfusion.PropertyGrid.Wpf~Syncfusion.Windows.PropertyGrid.PropertyGrid~AutoGeneratingPropertyGridItem_EV.html)  event with [AutoGeneratingPropertyGridItemEventArgs.Description](https://help.syncfusion.com/cr/wpf/Syncfusion.PropertyGrid.Wpf~Syncfusion.Windows.PropertyGrid.AutoGeneratingPropertyGridItemEventArgs~Description.html) property.

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
                         DescriptionPanelVisibility="Visible" 
                         DescriptionPanelHeight="50"
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
propertyGrid1.DescriptionPanelVisibility = Visibility.Visible;
propertyGrid1.DescriptionPanelHeight = new GridLength(50);

{% endhighlight %} 
{% endtabs %} 

{% tabs %}
{% highlight C# %}

private void PropertyGrid1_AutoGeneratingPropertyGridItem(object sender, AutoGeneratingPropertyGridItemEventArgs e) {
    //Description about the DOB properties is added.
    if (e.DisplayName == "DOB") {
        e.Description = "Birth date of the Employee";
    }
}

{% endhighlight %} 
{% endtabs %} 

![Description of the Properties added by the Description property of the AutoGeneratingPropertyGridItem event](Attribute-Images\Description-AutoGeneratingPropertyGridItem.png)

Here, the `DOB` property description is added by the `AutoGeneratingPropertyGridItemEventArgs.Description` property of the `AutoGeneratingPropertyGridItem` event, not by any attributes.

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/wpf-property-grid-examples/tree/master/Samples/AutoGeneratingPropertyGridItem%20event)

## Setting description panel height

By default, the height of the description panel is automatically adjusted, based on the description text length of the property items. If you want to set description panel height manually, use the [DescriptionPanelHeight](https://help.syncfusion.com/cr/wpf/Syncfusion.PropertyGrid.Wpf~Syncfusion.Windows.PropertyGrid.PropertyGrid~DescriptionPanelHeight.html) property. The default value of `DescriptionPanelHeight` property is `Auto`.

N> If length of the description text exceeds the `DescriptionPanelHeight` when manually setting the value to `DescriptionPanelHeight`, particular text is trimmed. you can see the full description text using the tooltip.

{% tabs %}
{% highlight C# %}

using System;
using System.ComponentModel;
using System.ComponentModel.DataAnnotations;

public class Employee {
    [Display(Description = "Name of the employee")]
    public string Name { get; set; }
    [Description("An employee ID is a code used by an employer to uniquely identify the people working at an organization")]
    public string ID { get; set; }
    public DateTime DOB { get; set; }
}

public class ViewModel {
    public Object SelectedEmployee { get; set; }
    public ViewModel() {
        SelectedEmployee = new Employee()
        {
            Name = "John",
            ID = "381",
            DOB = new DateTime(1995, 12, 24)
        };
    }
}
      
{% endhighlight %}
{% endtabs %} 

{% tabs %}
{% highlight xaml %}

<syncfusion:PropertyGrid DescriptionPanelVisibility="Visible" 
                         DescriptionPanelHeight="60"
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
propertyGrid1.DescriptionPanelVisibility = Visibility.Visible;
propertyGrid1.DescriptionPanelHeight = new GridLength(60);

{% endhighlight %} 
{% endtabs %}

![Description panel height is manually changed](Attribute-Images\DescriptionPanelHeight.png)
