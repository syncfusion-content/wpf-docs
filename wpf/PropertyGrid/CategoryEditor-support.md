---
layout: post
title: CategoryEditor for the Properties in WPF PropertyGrid control | Syncfusion
description: The PropertyGrid control supports several built-in editors, to give a good look and feel for the application using CustomEditors or CategoryEditors.
platform: wpf
control: PropertyGrid 
documentation: ug
---

# CategoryEditor Support in WPF PropertyGrid

The [PropertyGrid](https://www.syncfusion.com/wpf-ui-controls/propertygrid) control supports several built-in editors, to give a good look and feel for the application, use `CustomEditors` or `CategoryEditors`. `CategoryEditor` support enables you to set related properties (one or more properties) under single or multiple Category based on the need. `CategoryEditor` can be applied for `Grouping`. While sorting, default editors will be displayed.

## Adding CategoryEditor to PropertyGrid

If user want to display some related properties under the specific Category, you can do it by the `CategoryEditor`. You can add any number of `CategoryEditors`. You must add property names in the `CategoryEditor.Properties` collection which are need to be categorized in the same category. Using the `CategoryEditor.EditorTemplate`, you can create the own template for the Categorized properties. To display the `CategoryEditor`, you need the enable the [EnableGrouping](https://help.syncfusion.com/cr/wpf/Syncfusion.PropertyGrid.Wpf~Syncfusion.Windows.PropertyGrid.PropertyGrid~EnableGrouping.html) property as `true`.    

a) `ColorEdit` control visibility converter for the CategoryEditor template

{% tabs %}
{% highlight C# %}

using System;
using System.Windows;
using System.Windows.Data;

public class SelectedIndexToVisibility : IValueConverter
{
    public object Convert(object value, Type targetType, object parameter, System.Globalization.CultureInfo culture)
    {
        int index = (int)value;
        Visibility vis;
        if (index == 0 && parameter.ToString() == "Foreground")
        {
            vis = Visibility.Visible;
        }
        else if (index == 1 && parameter.ToString() == "Background")
        {
            vis = Visibility.Visible;
        }
        else if (index == 2 && parameter.ToString() == "BorderBrush")
        {
            vis = Visibility.Visible;
        }
        else
        {
            vis = Visibility.Collapsed;
        }

        return vis;
    }

    public object ConvertBack(object value, Type targetType, object parameter, System.Globalization.CultureInfo culture)
    {
        return null;
    }
}

{% endhighlight %}
{% endtabs %}
 
 b) Creating the CategoryEditor for the properties:

{% tabs %}
{% highlight xaml %}

<Window.Resources>
        <local:SelectedIndexToVisibility x:Key="VisConv"/>
    </Window.Resources>
    <Grid>
        <Grid.ColumnDefinitions>
            <ColumnDefinition></ColumnDefinition>
            <ColumnDefinition Width="300"></ColumnDefinition>
        </Grid.ColumnDefinitions>
        <syncfusion:PropertyGrid Margin="20" Grid.Column="0" Name="propertyGrid1" SelectedObject="{Binding ElementName=button}" EnableGrouping="True" >
            <syncfusion:PropertyGrid.CategoryEditors>
                <syncfusion:CategoryEditor Category="A-Brushes">
                    <syncfusion:CategoryEditor.Properties>
                        <syncfusion:CategoryEditorProperty Name="Background"/>
                        <syncfusion:CategoryEditorProperty Name="Foreground"/>
                        <syncfusion:CategoryEditorProperty Name="BorderBrush"/>
                    </syncfusion:CategoryEditor.Properties>
                    <syncfusion:CategoryEditor.EditorTemplate>
                        <DataTemplate>
                            <Grid>
                                <Grid.RowDefinitions>
                                    <RowDefinition />
                                    <RowDefinition />
                                </Grid.RowDefinitions>
                                <ListBox BorderBrush="Transparent" x:Name="list" SelectedIndex="0">
                                    <StackPanel HorizontalAlignment="Center" Orientation="Horizontal">
                                        <TextBlock Text="Foreground" Margin="5" Width="80"/>
                                        <Rectangle Stroke="Black" Fill="{Binding Path=CategoryValueProperties[Foreground].Value, Mode=TwoWay}" Height="15" Width="25" Margin="5"/>
                                    </StackPanel>
                                    <StackPanel HorizontalAlignment="Center" Orientation="Horizontal">
                                        <TextBlock Text="Background" Margin="5" Width="80"/>
                                        <Rectangle Stroke="Black" x:Name="background" Fill="{Binding Path=CategoryValueProperties[Background].Value, Mode=TwoWay}" Height="15" Width="25" Margin="5" />
                                    </StackPanel>
                                    <StackPanel HorizontalAlignment="Center" Orientation="Horizontal">
                                        <TextBlock Text="BorderBrush" Margin="5" Width="80"/>
                                        <Rectangle Stroke="Black" Fill="{Binding Path=CategoryValueProperties[BorderBrush].Value, Mode=TwoWay}" Height="15" Width="25" Margin="5"/>
                                    </StackPanel>
                                </ListBox>
                                
                                <syncfusion:ColorEdit Grid.Row="1" IsGradientPropertyEnabled="False" Visibility="{Binding ElementName=list, Path=SelectedIndex, Converter={StaticResource VisConv}, ConverterParameter=Foreground}"
                                                      Brush="{Binding Path=CategoryValueProperties[Foreground].Value, Mode=TwoWay}" EnableToolTip="False"/>
                                <syncfusion:ColorEdit Grid.Row="1" IsGradientPropertyEnabled="False" Visibility="{Binding ElementName=list, Path=SelectedIndex, Converter={StaticResource VisConv}, ConverterParameter=Background}"
                                                      Brush="{Binding Path=CategoryValueProperties[Background].Value, Mode=TwoWay}" EnableToolTip="False"/>
                                <syncfusion:ColorEdit Grid.Row="1" IsGradientPropertyEnabled="False" Visibility="{Binding ElementName=list, Path=SelectedIndex, Converter={StaticResource VisConv}, ConverterParameter=BorderBrush}"
                                                      Brush="{Binding Path=CategoryValueProperties[BorderBrush].Value, Mode=TwoWay}" EnableToolTip="False"/>
                            </Grid>
                        </DataTemplate>
                    </syncfusion:CategoryEditor.EditorTemplate>
                </syncfusion:CategoryEditor>
            </syncfusion:PropertyGrid.CategoryEditors>
        </syncfusion:PropertyGrid>
        <StackPanel Grid.Column="1" VerticalAlignment="Center" HorizontalAlignment="Center" >
            <TextBlock Grid.Column="1" Margin="10" HorizontalAlignment="Center"  TextWrapping="Wrap" VerticalAlignment="Center" Width="168"><Run Text="Selected Object: "/><Run FontWeight="Bold" Text="Button"/></TextBlock>
            <Button Name="button" Width="200" Height="50" VerticalAlignment="Center" HorizontalAlignment="Center" Content="Click me"/>
        </StackPanel>
    </Grid>

{% endhighlight %}
{% endtabs %}

Here, the `Background`, `Foreground` and `BorderBrush` properties are categorized under the `A-Brushes` category with `ColorEdit` as value editor by the `CategoryEditor`. Before using the `CategoryEditor`, `Background`, `Foreground` and `BorderBrush` properties are categorized under the `Appearance` category.

![PropertyGrid with CategoryEditor](CategoryEditor-support_images/CategoryEditor-support_img1.png)
