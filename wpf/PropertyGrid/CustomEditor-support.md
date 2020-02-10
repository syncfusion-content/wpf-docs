---
layout: post
title: CustomEditor for the Properties in WPF PropertyGrid control | Syncfusion
description: Learn about CustomEditor for the Properties of selected object in Syncfusion WPF PropertyGrid control and more details.
platform: wpf
control: PropertyGrid 
documentation: ug
---

# CustomEditor Support in WPF PropertyGrid

The [PropertyGrid](https://www.syncfusion.com/wpf-ui-controls/propertygrid) control supports several built-in editors, to give a good look and feel for the application, use `CustomEditors` or `CategoryEditors`. You can make own customized value editor for the properties instead of default value editors by using the [Editor](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.editorattribute?view=netframework-4.8) attribute or [CustomEditorCollection](https://help.syncfusion.com/cr/wpf/Syncfusion.PropertyGrid.Wpf~Syncfusion.Windows.PropertyGrid.PropertyGrid~CustomEditorCollection.html).

## Creating the Custom Editor 

To create `CustomEditor`, you need to implement `ITypeEditor` interface. Here, `SfMaskedEdit` is created with `EmailId` mask and `UpDown` control is created with min, max value as a Custom Editors.

{% tabs %}
{% highlight C# %}

//Custom Editor for the EmailId properties.
public class EmailEditor : ITypeEditor
{
    SfMaskedEdit maskededit;
    public void Attach(PropertyViewItem property, PropertyItem info)
    {
        if (info.CanWrite)
        {
            var binding = new Binding("Value") { Mode = BindingMode.TwoWay, Source = info, ValidatesOnExceptions = true, ValidatesOnDataErrors = true };
            BindingOperations.SetBinding(maskededit, SfMaskedEdit.ValueProperty, binding);
        }
        else
        {
            maskededit.IsEnabled = false;
            var binding = new Binding("Value") { Source = info, ValidatesOnExceptions = true, ValidatesOnDataErrors = true };
            BindingOperations.SetBinding(maskededit, SfMaskedEdit.ValueProperty, binding);
        }
    }
    public object Create(PropertyInfo propertyInfo)
    {
        maskededit = new SfMaskedEdit();
        maskededit.MaskType = MaskType.RegEx;
        maskededit.Mask = "[A-Za-z0-9._%-]+@[A-Za-z0-9]+.[A-Za-z]{2,3}";
        return maskededit;
    }
    public void Detach(PropertyViewItem property)
    {

    }
}

//Custom Editor for the integer type properties.
public class IntegerEditor : ITypeEditor
{
    UpDown upDown;
    public void Attach(PropertyViewItem property, PropertyItem info)
    {
        if (info.CanWrite)
        {
            var binding = new Binding("Value") { Mode = BindingMode.TwoWay, Source = info, ValidatesOnExceptions = true, ValidatesOnDataErrors = true };
            BindingOperations.SetBinding(upDown, UpDown.ValueProperty, binding);
        }
        else
        {
            upDown.IsEnabled = false;
            var binding = new Binding("Value") { Source = info, ValidatesOnExceptions = true, ValidatesOnDataErrors = true };
            BindingOperations.SetBinding(upDown, UpDown.ValueProperty, binding);
        }
    }
    public object Create(PropertyInfo propertyInfo)
    {
        upDown = new UpDown();  
        upDown.ApplyZeroColor = false;
        upDown.MinValue = 0;
        upDown.MaxValue = 100;
        upDown.NumberDecimalDigits = 0;
        return upDown;
    }
    public void Detach(PropertyViewItem property)
    {

    }
}

{% endhighlight  %}
{% endtabs %}

{% tabs %}
{% highlight C# %}

{% endhighlight  %}
{% endtabs %}

//Employee class containing the properties.
public class Employee : NotificationObject
{
    public string EmailID { get; set; }
    public string Name { get; set; }
    public int Age { get; set; }
    public int Experience { get; set; }
}

class ViewModel
{
    public object SelectedEmployee { get; set; }
    public ViewModel()
    {
        SelectedEmployee = new Employee() { Age = 25, Name = "mark", Experience = 5, EmailID = "mark@gt" };
    }
}

{% tabs %}
{% highlight xaml %}

<Window xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:syncfusion="http://schemas.syncfusion.com/wpf"
        mc:Ignorable="d"
        Title="MainWindow" Height="450" Width="800">
    <Window.DataContext>
        <local:ViewModel></local:ViewModel>
    </Window.DataContext>
    <Grid>
        <syncfusion:PropertyGrid x:Name="propertyGrid1" SelectedObject="{Binding SelectedEmployee}" Height="200" Width="400" ></syncfusion:PropertyGrid>
    </Grid>
</Window>

{% endhighlight  %}
{% endtabs %}

## Assigning a CustomEditor using Editor Attribute

The User can assign the `CustomEditor` to any individual property based on the `Name` of the property or to multiple properties containing the same `Type` by using the `Editor` attribute.

{% tabs %}
{% highlight C# %}

//Custom Editor for the EmailId property 
[Editor("EmailID", typeof(EmailEditor))]
//Custom Editor for integer type properties
[Editor(typeof(int), typeof(IntegerEditor))]

public class Employee : NotificationObject
{
    public string EmailID { get; set; }
    public string Name { get; set; }
    public int Age { get; set; }
    public int Experience { get; set; }
}

{% endhighlight  %}
{% endtabs %}

Here, The `EmailID` is a string property, the `TextBox` is assigned as a default editor. We changed it as `SfMaskedEdit` textbox that accepts only inputs which are in the Email id format by using the `EmailEditor`. Also, we assigned the `IntegerEditor` for the  the integer type properties, so it applied to the `ID` and `Age` properties. Then, the editors for the `Id` and `Age` property is changed from `NumericTextBox` to `Updown` control.

![Property grid with specified custom attribute](CustomEditor-support_images/CustomEditor-Attribute.png)

## Assigning a CustomEditor using CustomEditorCollection

The User can assign the `CustomEditor` to any particular property or to multiple properties which are in same type. 

If User want to apply custom editor for any particular property which are in same type, you need to create the `CustomEditor` instance, assign your own editor to the `CustomEditor.Editor` and add the property name to the `CustomEditor.Properties` collection. Then, add the `CustomEditor` instance to the `PropertyGrid.CustomEditorCollection`.

{% tabs %}
{% highlight C# %}

public partial class MainWindow : Window
{
    public MainWindow()
    {
        InitializeComponent();
        CustomEditor editor = new CustomEditor();
        editor.Editor = new EmailEditor();
        editor.Properties.Add("EmailID");
        this.propertyGrid1.CustomEditorCollection.Add(editor);
        this.DataContext = new ViewModel();
    }
}

![CustomEditor applied for EmailID property](CustomEditor-support_images/CustomEditor-Collection1.png)


{% endhighlight  %}
{% endtabs %}

If User want to apply custom editor for multiple properties, you need to create the `CustomEditor` instance, assign your own editor to the `CustomEditor.Editor` and sets the `CustomEditor.HasPropertyType`  property  to `true`. Then, mention the type of the properties to the `CustomEditor.PropertyType`.

{% tabs %}
{% highlight C# %}

public partial class MainWindow : Window
{
    public MainWindow()
    {
        InitializeComponent();
        CustomEditor editor1 = new CustomEditor();
        editor1.Editor = new IntegerEditor();
        editor1.HasPropertyType = true;
        editor1.PropertyType = typeof(int);
        this.propertyGrid1.CustomEditorCollection.Add(editor1);
        this.DataContext = new ViewModel();
    }
}

{% endhighlight  %}
{% endtabs %}

![CustomEditor applied for integer type properties](CustomEditor-support_images/CustomEditor-Collection2.png)

Refer to this [`sample`](https://github.com/SyncfusionExamples/How-to-set-custom-editor-for-properties-through-EditorAttribute-in-WPF-PropertyGrid) to know how the custom editor has been set to the class.
