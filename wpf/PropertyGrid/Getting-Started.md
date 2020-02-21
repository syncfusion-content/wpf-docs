---
layout: post
title: Getting started with WPF PropertyGrid control | Syncfusion
description: Learn here about getting started with Syncfusion WPF PropertyGrid control and more details about the control features.
platform: WPF
control: PropertyGrid
documentation: ug
---

# Getting started with WPF PropertyGrid

This section explains how to create a WPF [PropertyGrid](https://www.syncfusion.com/wpf-ui-controls/propertygrid) control and its features.

## Assembly deployment

Refer to the [control dependencies](https://help.syncfusion.com/wpf/control-dependencies#propertygrid) section to get the list of assemblies or NuGet package that needs to be added as a reference to use the control in any application.

You can find more details about installing the NuGet package in a WPF application in the following link: 

[How to install nuget packages](https://help.syncfusion.com/wpf/nuget-packages)

## Adding WPF PropertyGrid via designer

You can add the [PropertyGrid](https://www.syncfusion.com/wpf-ui-controls/propertygrid) control to an application by dragging it from the toolbox to a view of the designer. The following dependent assembly will be added automatically:

* Syncfusion.PropertyGrid.Wpf
* Syncfusion.Shared.WPF
* Syncfusion.Tools.Wpf

![PropertyGrid Control added by designer](Getting-Started_images/Getting-Started_img2.png)

## Adding WPF PropertyGrid via XAML

To add the `PropertyGrid` control manually in XAML, follow these steps:
1. Create a new WPF project in Visual Studio.

2. Add the  following assembly references to the project,
   * Syncfusion.PropertyGrid.Wpf
   * Syncfusion.Shared.WPF
   * Syncfusion.Tools.Wpf

 
3. Import Syncfusion WPF schema **http://schemas.syncfusion.com/wpf** and declare the `PropertyGrid` control in XAML page.

{% tabs %}
{% highlight xaml %}

<Window x:Class="PropertyGridSample.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:syncfusion="http://schemas.syncfusion.com/wpf"
        mc:Ignorable="d" 
        Title="MainWindow" Height="600" Width="500">
    <Grid>
        <syncfusion:PropertyGrid  Name="propertyGrid1" Height="400" Width="300" >
        </syncfusion:PropertyGrid>
    </Grid>
</Window>

{% endhighlight %}
{% endtabs %}

## Adding WPF PropertyGrid via C\#

To add the `PropertyGrid` control manually in C#, follow these steps:

1. Create a new WPF application via Visual Studio.

2. Add the  following assembly references to the project,
    * Syncfusion.PropertyGrid.Wpf
    * Syncfusion.Shared.WPF
    *  Syncfusion.Tools.Wpf

3. Include the required namespace.

{% tabs %}
{% highlight C# %}

using Syncfusion.Windows.PropertyGrid;

{% endhighlight %}
{% endtabs %}

4. Create an instance of PropertyGrid and add it to the window.

{% tabs %}
{% highlight C# %}

public partial class MainWindow : Window
{
    public MainWindow()
    {
        InitializeComponent();

        // Creating an instance of PropertyGrid control

        PropertyGrid propertyGrid1 = new PropertyGrid();

        // Setting height and width to PropertyGrid

        propertyGrid1.Height = 300;
        propertyGrid1.Width = 200;

        //Adding PropertyGrid as window content

        this.Content = propertyGrid1;
    }
}

{% endhighlight %}
{% endtabs %}

![PropertyGrid control added to Window by code](Getting-Started_images/Getting-Started_img15.png)

## Populating the properties

We can display the properties of any DotNet object using the [SelectedObject](https://help.syncfusion.com/cr/wpf/Syncfusion.PropertyGrid.Wpf~Syncfusion.Windows.PropertyGrid.Property~SelectedObject.html) property. When the `SelectedObject` property is bound with an object, the properties of that object are parsed and displayed in the PropertyGrid.

{% tabs %}
{% highlight C# %}

// Employee class to be explored in property grid.
public class Employee {
    public string EmployeeName { get; set; }
    public string ID { get; set; }
    public int Age { get; set; }
    public int Experiance { get; set; }
}

//Create ViewModel class with a property to be bounded with PropertyGrid.SelectedObject 
public class ViewModel {
    public object SelectedEmployee { get; set; }
    public ViewModel() {
        SelectedEmployee = new Employee() 
        {
            EmployeeName = "Johnson",
            Age = 25,
            ID = "1234",
            Experiance =3
        };
    }
}

{% endhighlight %}
{% endtabs %}

The properties of the SelectedEmployee object can be populated in the following ways,

### Populating the properties using XAML

We can populate the properties of the Object using XAML

{% tabs %}
{% highlight xaml %}

<syncfusion:PropertyGrid SelectedObject="{Binding SelectedEmployee}"
                         Name="propertyGrid1" >
    <syncfusion:PropertyGrid.DataContext>
        <local:ViewModel></local:ViewModel>
    </syncfusion:PropertyGrid.DataContext>
</syncfusion:PropertyGrid>

{% endhighlight %}
{% endtabs %}

In the above code snippet, the `SelectedEmployee` object is set as `SelectedObject` for the `PropertyGrid`. Thus, the `PropertyGrid` shows all the properties available in the `SelectedEmployee` object. 

### Populating the properties using C#

We can sets the object to the `SelectedObject` property using C# to populate the properties in the `PropertyGrid`.

{% tabs %}
{% highlight c# %}

PropertyGrid propertyGrid1 = new PropertyGrid();
propertyGrid1.DataContext = new ViewModel();
propertyGrid1.SelectedObject = (propertyGrid1.DataContext as ViewModel).SelectedEmployee;

{% endhighlight %}
{% endtabs %}

![ Populating the SelectedEmployee object properties into the PropertyGrid control](Getting-Started_images/Binding-with-any-object_img1.png)

## Custom Editor for value editors

The [PropertyGrid](https://www.syncfusion.com/wpf-ui-controls/propertygrid) control supports several built-in editors, to give a good look and feel for the application, use `CustomEditors`. We can make own customized value editor for the properties instead of default value editors by using the [Editor](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.editorattribute?view=netframework-4.8) attribute or [CustomEditorCollection](https://help.syncfusion.com/cr/wpf/Syncfusion.PropertyGrid.Wpf~Syncfusion.Windows.PropertyGrid.PropertyGrid~CustomEditorCollection.html).

### Creating the Custom Editor 

To create `CustomEditor`, we need to implement `ITypeEditor` interface. Here, `SfMaskedEdit` is created with `EmailId` mask as `EmailEditor`.

{% tabs %}
{% highlight C# %}

//Custom Editor for the EmailId properties.
public class EmailEditor : ITypeEditor {
    SfMaskedEdit maskededit;
    public void Attach(PropertyViewItem property, PropertyItem info) {
        if (info.CanWrite) {
            var binding = new Binding("Value")
            {
                Mode = BindingMode.TwoWay,
                Source = info,
                ValidatesOnExceptions = true,
                ValidatesOnDataErrors = true
            };
            BindingOperations.SetBinding(maskededit, SfMaskedEdit.ValueProperty, binding);
        }
        else {
            maskededit.IsEnabled = false;
            var binding = new Binding("Value")
            {
                Source = info,
                ValidatesOnExceptions = true,
                ValidatesOnDataErrors = true
            };
            BindingOperations.SetBinding(maskededit, SfMaskedEdit.ValueProperty, binding);
        }
    }
    public object Create(PropertyInfo propertyInfo) {
        maskededit = new SfMaskedEdit();
        maskededit.MaskType = MaskType.RegEx;
        maskededit.Mask = "[A-Za-z0-9._%-]+@[A-Za-z0-9]+.[A-Za-z]{2,3}";
        return maskededit;
    }
    public void Detach(PropertyViewItem property) {

    }
}

{% endhighlight %}
{% endtabs %}

### Assigning a Custom Editor using Editor Attribute

We can assign the `CustomEditor` to any individual property by name of the property and to multiple properties based on the property type by using the `Editor` attribute.

{% tabs %}
{% highlight C# %}

//CustomEditor for the specific (EmailID) property
[Editor("EmailID", typeof(EmailEditor))]
//Custom Editor for the multiple(Integer type) properties
[Editor(typeof(int), typeof(IntegerEditor))]
public class Employee : NotificationObject {
    public string EmailID { get; set; }
    public string Name { get; set; }
    public int Age { get; set; }
    public int Experience { get; set; }
}

class ViewModel {
    public object SelectedEmployee { get; set; }
    public ViewModel() {
        SelectedEmployee = new Employee()
        {
            Age = 25,
            Name = "mark",
            Experience = 5,
            EmailID = "mark@gt"
        };
    }
}

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight xaml %}

<syncfusion:PropertyGrid SelectedObject="{Binding SelectedEmployee}"
                         x:Name="propertyGrid1" >
    <syncfusion:PropertyGrid.DataContext>
        <local:ViewModel></local:ViewModel>
   </syncfusion:PropertyGrid.DataContext>
</syncfusion:PropertyGrid>

{% endhighlight %}
{% highlight C# %}

PropertyGrid propertyGrid1 = new PropertyGrid();
ViewModel viewModel = new ViewModel();
propertyGrid1.SelectedObject = viewModel.SelectedEmployee;

{% endhighlight %}
{% endtabs %}


Here, The `EmailID` is a string property, the `TextBox` is assigned as a default editor. We changed it as `SfMaskedEdit` textbox that accepts only inputs which are in the email-id format. Also, we assigned the `IntegerEditor` for the integer type properties, so it applied to the `Experience` and `Age` properties. Then, the value editors for the `Experience` and `Age` property is changed from `NumericTextBox` to `Updown` control.

![Property grid with specified custom value editor for EmailID property](CustomEditor-support_images/CustomEditor-Attribute.png)



Click [here](https://github.com/SyncfusionExamples/wpf-property-grid-examples/tree/master/Samples/PropertyGrid-CustomEditor) to download the sample that showcases the `CustomEditor` support.



Click [here](https://github.com/SyncfusionExamples/wpf-property-grid-examples/tree/master/Samples/PropertyGrid-Common) to download the sample that showcases the `PropertyGrid` overall features.

