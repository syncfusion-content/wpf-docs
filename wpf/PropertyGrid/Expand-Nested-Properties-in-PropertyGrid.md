---
layout: post
title: Expand Nested Properties in WPF PropertyGrid control | Syncfusion
description: Learn about expanding the nested properties of selected object in Syncfusion WPF PropertyGrid control and more details.
platform: wpf
control: PropertyGrid 
documentation: ug
---

# Expand Nested Properties in PropertyGrid

The [PropertyGrid](https://www.syncfusion.com/wpf-ui-controls/propertygrid) control has support to expand instance properties of a class which has [ExpandableObjectConverter](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.expandableobjectconverter?view=netframework-4.8) as its [TypeConverter](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.typeconverter?view=netframework-4.8). 
User can show the direct property and user can create a sub properties with any number of levels.

###  Navigate to the sub-properties Properties

The Users can choose whether the sub-properties of the [SelectedObject](https://help.syncfusion.com/cr/wpf/Syncfusion.PropertyGrid.Wpf~Syncfusion.Windows.PropertyGrid.PropertyGrid~SelectedObject.html) can be expanded or not by using the [PropertyExpandMode](https://help.syncfusion.com/cr/wpf/Syncfusion.PropertyGrid.Wpf~Syncfusion.Windows.PropertyGrid.PropertyGrid~PropertyExpandMode.html) property. The Values of `PropertyExpandMode` is `NestedMode` and `FlatMode`. By default, the sub-properties are not shown.  If User want to display the sub-properties, you can set the `PropertyExpandMode`  property as `NestedMode`.

{% tabs %}
{% highlight C# %}

// A Class that represents the nested properties
public class Address {
    public string State { get; set; }        
    public string StreetName { get; set; }
    public string DoorNo { get; set; }
    public override string ToString() {
        return DoorNo + ", " + StreetName + ", " + State;
    }
}

public class Employee {
    public string Name { get; set; }
    public string ID { get; set; }
    public int Age { get; set; }
    // Property contains the sub properties
    public Address Address { get; set; }
}

public class ViewModel
{
    public object SelectedEmployee { get; set; }
    public PropertyExpandModes PropertyExpandMode { get; set; }
    public ViewModel(){
        SelectedEmployee = new Employee() { Address = new Address() { State = "New Yark", DoorNo = "10", StreetName = "Martin street" }, Age = 23, ID = "1207", Name = "Mark" };
        PropertyExpandMode = PropertyExpandModes.FlatMode;
    }
}

{% endhighlight  %}
{% endtabs %}

{% tabs %}
{% highlight xaml %}

<Window.DataContext>
    <local:ViewModel></local:ViewModel>
</Window.DataContext>

<Grid>
    <Grid.ColumnDefinitions>
        <ColumnDefinition></ColumnDefinition>
        <ColumnDefinition Width="200"></ColumnDefinition>
    </Grid.ColumnDefinitions>
    <syncfusion:PropertyGrid PropertyExpandMode="{Binding PropertyExpandMode, Mode=TwoWay}" SelectedObject="{Binding SelectedEmployee }" Grid.Column="0" Name="propertyGrid1" Height="300" Width="300" />
    <StackPanel HorizontalAlignment="Center" VerticalAlignment="Center" Grid.Column="1">
        <TextBlock FontWeight="Normal" FontFamily="Segoe UI" FontSize="13" Margin="3" Text ="Nested Property Mode" />
        <ComboBox FontWeight="Bold" FontFamily="Segoe UI" FontSize="13" SelectedValue="{Binding PropertyExpandMode, Mode=TwoWay}"  Margin="3" Name="nestedProperties"  >
            <syncfusion:PropertyExpandModes>NestedMode</syncfusion:PropertyExpandModes>
            <syncfusion:PropertyExpandModes>FlatMode</syncfusion:PropertyExpandModes>
        </ComboBox>
    </StackPanel>
</Grid>

{% endhighlight  %}
{% endtabs %}

Here, In the `Employee` class, `Address` is a direct property. It contains the `State`, `StreetName` and `DoorNo` properties as sub properties. All the sub properties are shown by `PropertyExpandMode` as `NestedMode`. 

![PropertyGrid show the sub properties](Expand-Nested-Properties_images/Expand-Nested-Properties.png)