---
layout: post
title: Update value on lost focus in WPF PropertyGrid | Syncfusion
description: Learn about the binding modes that determines when to update the values of property item in PropertyGrid control.
platform: wpf
control: PropertyGrid 
documentation: ug
---

# Update value on lost focus in PropertyGrid

We can update the value of property item either immediately when the editor property changes or during the editor's lost focus using [UpdateSourceMode](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PropertyGrid.PropertyGrid.html#Syncfusion_Windows_PropertyGrid_PropertyGrid_UpdateSourceMode) property of PropertyGrid. Values of `UpdateSourceMode` are `Immediately`, `ReturnOrLostFocus`. The default value is `Immediately`.

## Binding modes 

 If the property `UpdateSourceMode` is `Immediately`, value of property item will be updated immediately when the editor property changes. Also, if the property `UpdateSourceMode` is `ReturnOrLostFocus`, value of property item will be updated only when editor lost its focus or when enter key is pressed.

{% tabs %}

{% highlight xaml %}

<Grid>
    <Grid.ColumnDefinitions>
        <ColumnDefinition Width="0.6*"/>
        <ColumnDefinition Width="0.4*"/>
    </Grid.ColumnDefinitions>

    <syncfusion:PropertyGrid Margin="10" 
                             x:Name="propertyGrid"
                             UpdateSourceMode="ReturnOrLostFocus" 
                             SelectedObject="{Binding ElementName=button}" />
    
    <syncfusion:ButtonAdv  Name="button" 
                           Margin="10" 
                           Height="25" 
                           Width="200" 
                           Label="SelectedObject"
                           HorizontalAlignment="Center" 
                           VerticalAlignment="Center"
                           Grid.Column="1" 
                           syncfusion:SkinStorage.VisualStyle="Default" />
</Grid>

{% endhighlight %}

{% highlight C# %}

propertyGrid.UpdateSourceMode = UpdateSourceMode.ReturnOrLostFocus;

{% endhighlight %}

{% endtabs %}

The SelectedObject value changes immediately when the target element property changes, as shown below:

![Wpf PropertyGrid selected object value changes immediately](Binding-with-any-object_images/wpf-propertygrid-updatesourcemode-immediately.gif)

The SelectedObject value changes only when the target element lost its focus or when enter key is pressed, as shown below.

![Wpf PropertyGrid selected object value changes during editor lost focus](Binding-with-any-object_images/wpf-propertygrid-updatesourcemode-lost-focus.gif)