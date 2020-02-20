---
layout: post
title: CustomEditor support in WPF PropertyGrid control | Syncfusion
description: Learn about CustomEditor for the Properties of selected object in Syncfusion WPF PropertyGrid control and more details.
platform: wpf
control: PropertyGrid 
documentation: ug
---

# Custom Editor in WPF PropertyGrid

The [PropertyGrid](https://www.syncfusion.com/wpf-ui-controls/propertygrid) control supports several built-in editors. Based on the property type, the built-in editors automatically assigned as value editor to the properties.

<table>
<th> S.No </th>
<th> Property Type </th>
<th> Default Editor </th>
<tr>
<td>1</td>
<td>int</td>
<td>IntegerTextBox</td>
</tr>
<tr>
<td>2</td>
<td>double</td>
<td>DoubleTextBox</td>
</tr>
<tr>
<td>3</td>
<td>string</td>
<td>TextBox</td>
</tr>
<tr>
<td>4</td>
<td>enum</td>
<td>ComboBox</td>
</tr>
<tr>
<td>5</td>
<td>DateTime</td>
<td>DateTimeEdit</td>
</tr>
<tr>
<tr>
<td>6</td>
<td>bool</td>
<td>CheckBox</td>
</tr>
<tr>
<tr>
<td>7</td>
<td>Brush</td>
<td>ColorPicker</td>
</tr>
<tr>
</table>


To give a good look and feel for the application, use `CustomEditors`. We can make own customized value editor for the properties instead of default value editors by using the [Editor](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.editorattribute?view=netframework-4.8) attribute or [CustomEditorCollection](https://help.syncfusion.com/cr/wpf/Syncfusion.PropertyGrid.Wpf~Syncfusion.Windows.PropertyGrid.PropertyGrid~CustomEditorCollection.html).

## Creating the Custom Editor 

To create `CustomEditor`, we need to implement `ITypeEditor` interface. Here, `SfMaskedEdit` is created with `EmailId` mask as `EmailEditor` and `UpDown` control is created with min, max value as `IntegerEditor`. `EmailEditor` and `IntegerEditor` are the custom editors.

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

//Custom Editor for the integer type properties.
public class IntegerEditor : ITypeEditor {
    UpDown upDown;
    public void Attach(PropertyViewItem property, PropertyItem info) {
        if (info.CanWrite) {
            var binding = new Binding("Value")
            {
                Mode = BindingMode.TwoWay,
                Source = info,
                ValidatesOnExceptions = true,
                ValidatesOnDataErrors = true
            };
            BindingOperations.SetBinding(upDown, UpDown.ValueProperty, binding);
        }
        else {
            upDown.IsEnabled = false;
            var binding = new Binding("Value")
            {
                Source = info,
                ValidatesOnExceptions = true,
                ValidatesOnDataErrors = true
            };
            BindingOperations.SetBinding(upDown, UpDown.ValueProperty, binding);
        }
    }
    public object Create(PropertyInfo propertyInfo) {
        upDown = new UpDown();
        upDown.ApplyZeroColor = false;
        upDown.MinValue = 0;
        upDown.MaxValue = 100;
        upDown.NumberDecimalDigits = 0;
        return upDown;
    }
    public void Detach(PropertyViewItem property) {

    }
}

{% endhighlight  %}
{% endtabs %}

## Assigning a Custom Editor using Editor Attribute

We can assign the `CustomEditor` to any individual property by name of the property and to multiple properties based on the property type by using the `Editor` attribute.

{% tabs %}
{% highlight C# %}

//CustomEditor for the specfic(EmailID) property
[Editor("EmailID", typeof(EmailEditor))]
//Custom Editor for the multiple(Tnteger type) properties
[Editor(typeof(int), typeof(IntegerEditor))]
public class Employee {
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

{% endhighlight  %}
{% endtabs %}

{% tabs %}
{% highlight xaml %}

<syncfusion:PropertyGrid SelectedObject="{Binding SelectedEmployee}"
                         x:Name="propertyGrid1" >
    <syncfusion:PropertyGrid.DataContext>
        <local:ViewModel></local:ViewModel>
   </syncfusion:PropertyGrid.DataContext>
</syncfusion:PropertyGrid>

{% endhighlight  %}
{% highlight C# %}

PropertyGrid propertyGrid1 = new PropertyGrid();
ViewModel viewModel = new ViewModel();
propertyGrid1.SelectedObject = viewModel.SelectedEmployee;

{% endhighlight  %}
{% endtabs %}

Here, The `EmailID` is a string property, the `TextBox` is assigned as a default editor. We changed it as `SfMaskedEdit` textbox that accepts only inputs which are in the email-id format. Also, we assigned the `IntegerEditor` for the integer type properties, so it applied to the `Experience` and `Age` properties. Then, the value editors for the `Experience` and `Age` property is changed from `NumericTextBox` to `Updown` control.

![Property grid with specified custom attribute](CustomEditor-support_images/CustomEditor-Attribute.png)

## Assigning a Custom Editor using Collection

We can assign the `CustomEditor` to any particular property and to multiple properties using the `CustomEditorCollection`. 

### Assigning a Custom Editor to the specific property

If we want to apply custom editor for any particular property, we need to create the `CustomEditor` instance, assign our own editor to the `CustomEditor.Editor` and add the property name to the `CustomEditor.Properties` collection. Then, add the `CustomEditor` instance to the `PropertyGrid.CustomEditorCollection`.

{% tabs %}
{% highlight C# %}

public class Employee {
    public string EmailID { get; set; }
    public string Name { get; set; }
    public int Age { get; set; }
    public int Experience { get; set; }
}

class ViewModel {
    public object SelectedEmployee { get; set; }
    public CustomEditorCollection customEditorCollection = new CustomEditorCollection();
    public CustomEditorCollection CustomEditorCollection
    {
        get { return customEditorCollection; }
        set { customEditorCollection = value; }
    }
    public ViewModel() {
        SelectedEmployee = new Employee() { Age = 25, Name = "mark", Experience = 5, EmailID = "mark@gt" };

        // EmailEditor added to the collection and will applied to the "EmailID" property
        CustomEditor editor1 = new CustomEditor();
        editor1.Editor = new EmailEditor();
        editor1.Properties.Add("EmailID");
        CustomEditorCollection.Add(editor1);
    }
}

{% endhighlight  %}
{% endtabs %}

{% tabs %}
{% highlight xaml %}

<syncfusion:PropertyGrid CustomEditorCollection="{Binding CustomEditorCollection}" 
                         SelectedObject="{Binding SelectedEmployee}"
                         x:Name="propertyGrid1" >
    <syncfusion:PropertyGrid.DataContext>
        <local:ViewModel></local:ViewModel>
   </syncfusion:PropertyGrid.DataContext>
</syncfusion:PropertyGrid>

{% endhighlight  %}
{% highlight C# %}

PropertyGrid propertyGrid1 = new PropertyGrid();
ViewModel viewModel = new ViewModel();
propertyGrid1.SelectedObject = viewModel.SelectedEmployee;

{% endhighlight  %}
{% endtabs %}

Here, The `EmailID` is a string property, the `TextBox` is assigned as a default editor. We changed it as `SfMaskedEdit` textbox that accepts only inputs which are in the email-id format.

![CustomEditor applied for EmailID property](CustomEditor-support_images/CustomEditor-Collection1.png)

## Assigning a Custom Editor based on the property type

If we want to apply custom editor for multiple properties which contains same type, we need to create the `CustomEditor` instance, assign our own editor to the `CustomEditor.Editor` and sets the `CustomEditor.HasPropertyType`  property  to `true`. Then, mention the property type to the `CustomEditor.PropertyType`.

{% tabs %}
{% highlight C# %}

public class Employee {
    public string EmailID { get; set; }
    public string Name { get; set; }
    public int Age { get; set; }
    public int Experience { get; set; }
}

class ViewModel {
    public object SelectedEmployee { get; set; }
    public CustomEditorCollection customEditorCollection = new CustomEditorCollection();
    public CustomEditorCollection CustomEditorCollection
    {
        get { return customEditorCollection; }
        set { customEditorCollection = value; }
    }
    public ViewModel() {
        SelectedEmployee = new Employee() { Age = 25, Name = "mark", Experience = 5, EmailID = "mark@gt" };
        // IntegerEditor added to the collection and will applied to the "int" type properties
        CustomEditor editor = new CustomEditor();
        editor.Editor = new IntegerEditor();
        editor.HasPropertyType = true;
        editor.PropertyType = typeof(int);
        CustomEditorCollection.Add(editor);
    }
}

{% endhighlight  %}
{% endtabs %}

{% tabs %}
{% highlight xaml %}

<syncfusion:PropertyGrid CustomEditorCollection="{Binding CustomEditorCollection}" 
                         SelectedObject="{Binding SelectedEmployee}"
                         x:Name="propertyGrid1" >
    <syncfusion:PropertyGrid.DataContext>
        <local:ViewModel></local:ViewModel>
   </syncfusion:PropertyGrid.DataContext>
</syncfusion:PropertyGrid>

{% endhighlight  %}
{% highlight C# %}

PropertyGrid propertyGrid1 = new PropertyGrid();
ViewModel viewModel = new ViewModel();
propertyGrid1.SelectedObject = viewModel.SelectedEmployee;

{% endhighlight  %}
{% endtabs %}

![CustomEditor applied for integer type properties](CustomEditor-support_images/CustomEditor-Collection2.png)

Here, we assigned the `IntegerEditor` custom editor for the integer type properties, so it applied to the `Experience` and `Age` properties. Then, the value editors for the `Experience` and `Age` property is changed from `NumericTextBox` to `Updown` control.

Click [here](https://github.com/SyncfusionExamples/wpf-property-grid-examples/tree/master/Samples/PropertyGrid-CustomEditor) to download the sample that showcases the `CustomEditor` support.
