---
layout: post
title: DisplayName of the Properties in WPF PropertyGrid control | Syncfusion
description: This section explains how the display name of the property item has been customized through attributes.
platform: wpf
control: PropertyGrid 
documentation: ug
---

# Display name of the Properties in WPF PropertyGrid

By default, the property name is displayed in the [PropertyGrid](https://www.syncfusion.com/wpf-ui-controls/propertygrid) . We can change the display name of the properties instead of the property name by using the attributes and event.

## Change property display name using attributes

We can give a meaningful name to the properties that are displayed in the [PropertyGrid](https://www.syncfusion.com/wpf-ui-controls/propertygrid) instead of the property name by using the [Name](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.dataannotations.displayattribute.name?view=netframework-4.8#System_ComponentModel_DataAnnotations_DisplayAttribute_Name) field of the [Display](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.dataannotations.displayattribute?view=netframework-4.8) attribute and [DisplayName](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.displaynameattribute?view=netframework-4.8) attribute.

{% tabs %}
{% highlight C# %}

using System;
using System.ComponentModel;
using System.ComponentModel.DataAnnotations;

public class Employee {
    [Display(Name = "Employee Name")] 
    public string Name { get; set; }
    [DisplayName("Employee ID")]
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

<syncfusion:PropertyGrid SelectedObject="{Binding SelectedEmployee}"
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

{% endhighlight %} 
{% endtabs %}

![Value specified in the Name field of the Display attribute and DisplayName attributes is displayed as Name of the property in PropertyGrid](Attribute-Images\Display-Name-Attribute.png)

Here, the `Name` and `ID` properties is displayed as `Employee Name` and  `Employee ID` respectively. 

N> If you use both the `DisplayName` attribute and `Name` field of the `Display` attribute, the `Name` field of the `Display` attribute will have higher priority.

 Click [here](https://github.com/SyncfusionExamples/wpf-property-grid-examples/tree/master/Samples/Name-Description) to download the sample that showcases the property `Display Name` support using attributes.

## Change property display name at runtime

We can set and change the property display name instead of the property name at runtime without using attributes by handling the [AutoGeneratingPropertyGridItem](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PropertyGrid.PropertyGrid.html)  event with [AutoGeneratingPropertyGridItemEventArgs.DisplayName](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PropertyGrid.AutoGeneratingPropertyGridItemEventArgs.html#Syncfusion_Windows_PropertyGrid_AutoGeneratingPropertyGridItemEventArgs_DisplayName) property.
   
{% tabs %}
{% highlight C# %}

using System;
using System.ComponentModel;
using System.ComponentModel.DataAnnotations;

public class Employee {
    public string Name { get; set; }
    public string ID { get; set; }
    public DateTime DOB { get; set; }
}

public class ViewModel {
    public object SelectedEmployee { get; set; }

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
    //Name and DOB property names changed as 'Employee Name' and 'Date of Birth'.
    if (e.DisplayName == "Name") {
        e.DisplayName = "Employee Name";
    }
    else if (e.DisplayName == "DOB") {
        e.DisplayName = "Date of Birth";
    }
}

{% endhighlight %} 
{% endtabs %} 

![Display name of the ID property changed to Employee ID by the DisplayName property of the AutoGeneratingPropertyGridItemEventArgs](Attribute-Images\DisplayName-AutoGeneratingPropertyGridItem.png)

Here, the `Name` and `DOB`property display name is changed as `Employee Name` and `Date of Birth` by the `AutoGeneratingPropertyGridItemEventArgs.Name` property of the `AutoGeneratingPropertyGridItem` event, not by any attributes.

Click [here](https://github.com/SyncfusionExamples/wpf-property-grid-examples/tree/master/Samples/AutoGeneratingPropertyGridItem%20event) to download the sample that showcases the property `Display Name` support using `AutoGeneratingPropertyGridItem` event.