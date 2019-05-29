---
layout: post
title: CategoryEditor support | PropertyGrid  | wpf | Syncfusion
description: The PropertyGrid control supports several built-in editors, to give a good look and feel for the application using CustomEditors or CategoryEditors.
platform: wpf
control: PropertyGrid 
documentation: ug
---

# CategoryEditor Support

The PropertyGrid control supports several built-in editors, to give a good look and feel for the application (like in Expression Blend) using CustomEditors or CategoryEditors. CategoryEditor support enables you to set related properties (one or more properties) on a custom control. CategoryEditor can be applied for Grouping. While sorting, default editors will be displayed.

## Adding CategoryEditor support to an application 

Using CategoryEditor, you can set the related properties on a custom control. 

In the below example, Text related properties are grouped under one category using CategoryEditor support. You can add any number of CategoryEditors. You must add property names in the Properties collection CategoryEditor. The properties can also be shown in a  separate tab using the Category property of CategoryEditor. You have to set the Template to group the related properties, using the EditorTemplate property of CategoryEditor.

In the below example, FontWeightButton and FontListBox are the custom controls.

{% tabs %}
{% highlight xaml %}

<syncfusion:PropertyGrid x:Name="propertyGrid" SelectedObject="{Binding ElementName=Btn}" Margin="50"                            Width="350" BorderBrush="Gray" BorderThickness="3" HorizontalAlignment="Center" VerticalAlignment="Center">
<syncfusion:PropertyGrid.CategoryEditors>
<syncfusion:CategoryEditor Category="MyFonts">
<syncfusion:CategoryEditor.Properties>
<syncfusion:CategoryEditorProperty Name="FontSize"/>
<syncfusion:CategoryEditorProperty Name="FontFamily"/>
<syncfusion:CategoryEditorProperty Name="FontStyle"/>
<syncfusion:CategoryEditorProperty Name="FontWeight"/>
</syncfusion:CategoryEditor.Properties>
<syncfusion:CategoryEditor.EditorTemplate>
<DataTemplate>
<Border HorizontalAlignment="Stretch" VerticalAlignment="Stretch" BorderBrush="Gray" BorderThickness="1" Margin="10" Background="LightGray" CornerRadius="5">
<Grid>
<Grid.ColumnDefinitions>
<ColumnDefinition Width="5*"/>
<ColumnDefinition Width="5*"/>
</Grid.ColumnDefinitions>
<Grid.RowDefinitions>
<RowDefinition Height="Auto"/>
<RowDefinition Height="Auto"/>
</Grid.RowDefinitions>
<local:FontListBox SelectedValue="{Binding Path=CategoryValueProperties[FontFamily].Value,Mode=TwoWay}" Grid.Row="0" Grid.Column="0" Margin="5"/>
<shared:IntegerTextBox Value="{Binding Path=CategoryValueProperties[FontSize].Value,Mode=TwoWay}" Grid.Row="0" Grid.Column="1" Margin="5"/>
<local:FontWeightButton SelectedValue="{Binding Path=CategoryValueProperties[FontWeight].Value,Mode=TwoWay}" Grid.Row="1" Grid.Column="0" Margin="5" PropType="FontWeight"/>
<local:FontWeightButton SelectedValue="{Binding Path=CategoryValueProperties[FontStyle].Value,Mode=TwoWay}" Grid.Row="1" Grid.Column="1" Margin="5" PropType="FontStyle"/>
</Grid>
</Border>
</DataTemplate>
</syncfusion:CategoryEditor.EditorTemplate>
</syncfusion:CategoryEditor>
</syncfusion:PropertyGrid.CategoryEditors>
</syncfusion:PropertyGrid>

{% endhighlight %}
{% endtabs %}

![PropertyGrid with CategoryEditor](CategoryEditor-support_images/CategoryEditor-support_img1.png)


### Properties

CategoryEditor Table

<table>
<tr>
<th>
Property </th><th>
Description </th><th>
Type </th><th>
Data Type </th><th>
Reference links </th></tr>
<tr>
<td>
CategoryEditors</td><td>
CategoryEditor support enables you to set the related properties (one or more properties) on a custom control.</td><td>
DependencyProperty</td><td>
CategoryEditorCollection</td><td>
</td></tr>
</table>


#### Sample link

1. Select Start -> Programs -> Syncfusion -> Essential Studio xx.x.x.xx -> Dashboard.
2. Select   Run Locally Installed Samples in WPF Button.
3. Now expand the PropertyGrid treeview item in the Sample Browser.
4. Choose any one of the samples listed under it to launch. 