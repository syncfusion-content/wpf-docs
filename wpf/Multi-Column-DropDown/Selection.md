---
layout: post
title: Selection in WPF Multi Column DropDown | Syncfusion.
description: Learn about single and multiple row selection support in Syncfusion WPF Multi Column DropDown and more details.
platform: wpf
control: SfMultiColumnDropDownControl
documentation: ug
---

# Selection

[SfMultiColumnDropDownControl](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.SfMultiColumnDropDownControl.html) allows you to select one or more rows based on the SelectionMode. You can get the selected item in the SfDataGrid by using [SelectedItem](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.SfMultiColumnDropDownControl~SelectedItem.html) property and the selected index by using [SelectedIndex](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.SfMultiColumnDropDownControl~SelectedIndex.html) property. 

By using [SelectedValue](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.SfMultiColumnDropDownControl~SelectedValue.html) property, you can get the selected value from the selected item based on the `ValueMember` property.

Its recommend to use the `SelectedItem` and `SelectedValue` instead of using `SelectedIndex` to get the selected value. 

By default, you can select only one item at a time from the dropdown, as the default value of SelectionMode is Single.

{% tabs %}
{% highlight xml %}
<syncfusion:SfMultiColumnDropDownControl x:Name="MultiColumnDropDown"
                         ItemsSource="{Binding Orders}"
						 ValueMember="CustomerID"
                         DisplayMember="CustomerName"
                         SelectionMode="Single">
</syncfusion:SfMultiColumnDropDownControl>
{% endhighlight %}
{% highlight c# %}
using Syncfusion.UI.Xaml.Grid;

this.MultiColumnDropDown.SelectionMode = DropDownSelectionMode.Single;
{% endhighlight %}
{% endtabs %}

![Single item selected in WPF SfMultiColumnDropDownControl](Selection_images/Selection_img1.png)

## Multiple Selection

You can select multiple rows at same time by setting SelectionMode as Multiple. Further, you can select multiple rows in the following ways

1. By clicking on the respective rows.
2. By dragging mouse on the dropdown grid.
3. By using `Space` key.
4. By interacting with the checkbox in the `Selector column`.

{% tabs %}
{% highlight xml %}
<syncfusion:SfMultiColumnDropDownControl x:Name="MultiColumnDropDown"
                         ItemsSource="{Binding Orders}"
						 ValueMember="CustomerID"
                         DisplayMember="CustomerName"
                         SelectionMode="Multiple">
</syncfusion:SfMultiColumnDropDownControl>
{% endhighlight %}
{% highlight c# %}
using Syncfusion.UI.Xaml.Grid;

this.MultiColumnDropDown.SelectionMode = DropDownSelectionMode.Multiple;
{% endhighlight %}
{% endtabs %}

![Multiple items selected in WPF SfMultiColumnDropDownControl](Selection_images/Selection_img2.png)

N> SelectedItem will be added, only after clicking on `Ok` button in the dropdown or by pressing `Enter` key. `SelectedItem`, `SelectedIndex` and `SelectedValue` denotes the first selected row.

### Separator string customization

By default, selected values in the editor are separated by `;`. You can change this string by setting SeparatorString property.

{% tabs %}
{% highlight xml %}
<syncfusion:SfMultiColumnDropDownControl x:Name="MultiColumnDropDown"
                         ItemsSource="{Binding Orders}"
                         SelectionMode="Multiple"
						 ValueMember="CustomerID"
                         DisplayMember="CustomerName"
                         SeparatorString="-">            
</syncfusion:SfMultiColumnDropDownControl>
{% endhighlight %}
{% highlight c# %}
using Syncfusion.UI.Xaml.Grid;

this.MultiColumnDropDown.SeparatorString = "-";
{% endhighlight %}
{% endtabs %}

![Customization of SeparatorString in WPF SfMultiColumnDropDownControl](Selection_images/Selection_img1.png)

### Adding custom header to the dropdown

You can add custom header to the dropdown by setting HeaderTemplate property. For example, you can add textbox at the header of dropdown to search and filter items.

{% tabs %}
{% highlight xml %}
xmlns:interactivity="http://schemas.microsoft.com/expression/2010/interactivity"

<Window.Resources>
    <local:MultiConverter x:Key="multiConverter"/>
    <DataTemplate x:Key="headerTemplate">
        <Border BorderThickness="0,0,0,1" BorderBrush="Gray">
            <TextBox x:Name="searchTextBox" Margin="3" >
                <interactivity:Interaction.Triggers>
                    <interactivity:EventTrigger EventName="TextChanged">
                        <interactivity:InvokeCommandAction Command="{Binding Path=DataContext.TextChanged, Source={x:Reference Name=MultiColumnDropDown}}" >
                            <interactivity:InvokeCommandAction.CommandParameter>
                                <MultiBinding Converter="{StaticResource multiConverter}">
                                    <Binding Source="{x:Reference Name=MultiColumnDropDown}"/>
                                    <Binding RelativeSource="{RelativeSource Mode=FindAncestor, AncestorType=TextBox}"/>
                                </MultiBinding>
                            </interactivity:InvokeCommandAction.CommandParameter>
                        </interactivity:InvokeCommandAction>
                    </interactivity:EventTrigger>
                </interactivity:Interaction.Triggers>
            </TextBox>
        </Border>
    </DataTemplate>
</Window.Resources>
	
<syncfusion:SfMultiColumnDropDownControl x:Name="MultiColumnDropDown"                                        
                                         DisplayMember="Title"
                                         HeaderTemplate="{StaticResource headerTemplate}"
                                         ItemsSource="{Binding MoviesLists}" 
                                         ValueMember="Cast" 
                                         SelectionMode="Multiple">
    <interactivity:Interaction.Triggers>
        <interactivity:EventTrigger EventName="PopupOpening">
            <interactivity:InvokeCommandAction 
			        Command="{Binding Path=DataContext.PopupOpening, ElementName=MultiColumnDropDown}"
                    CommandParameter="{Binding ElementName=MultiColumnDropDown}" />
        </interactivity:EventTrigger>
    </interactivity:Interaction.Triggers>
</syncfusion:SfMultiColumnDropDownControl>
{% endhighlight %}
{% highlight c# %}
using Syncfusion.UI.Xaml.Grid;
using Syncfusion.UI.Xaml.Utility;

public BaseCommand TextChanged
{
    get
    {
        if (textChanged == null)
            textChanged = new BaseCommand(OnTextChangedExecuted);
        return textChanged;
    }
}

public BaseCommand PopupOpening
{
    get
    {
        if (popupOpeningCommand == null)
            popupOpeningCommand = new BaseCommand(OnPopupOpening);
        return popupOpeningCommand;
    }
}

private void OnTextChangedExecuted(object obj)
{
    var param = (object[])obj;
    var multiColumnDropDown = param[0] as SfMultiColumnDropDownControl;
    searchTextBox = param[1] as TextBox;
    var grid = multiColumnDropDown.GetDropDownGrid();
    if (grid != null && grid.View != null && grid.View.Filter != null)
        grid.View.RefreshFilter();
}

private void OnPopupOpening(object obj)
{
    var multiColumnDropDown = obj as SfMultiColumnDropDownControl;
    var grid = multiColumnDropDown.GetDropDownGrid();
    if (grid != null)
        grid.View.Filter = CustomerFilter;
}

private bool CustomerFilter(object item)
{
    var movie = item as GrossingMoviesList;
    return movie.Title.ToLower().Contains(searchTextBox.Text.ToLower());
}

internal class MultiConverter : IMultiValueConverter
{
    public object Convert(object[] values, Type targetType, object parameter, CultureInfo culture)
    {
        return values.ToArray();
    }

    public object[] ConvertBack(object value, Type[] targetTypes, object parameter, CultureInfo culture)
    {
        throw new NotImplementedException();
    }
}
	
{% endhighlight %}
{% endtabs %}

You can refer `Search with TextBox in DropDown` section in this [sample](https://github.com/syncfusion/wpf-demos/tree/master/MultiColumn%20Dropdown/MultiColumnDropDownDemo/CS).

## Events

You can handle the selection operations in SfMultiColumnDropDownControl by using [SelectionChanged](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.SfMultiColumnDropDownControl~SelectionChanged_EV.html) event.

### SelectionChanged

`SelectionChanged` event is fired when select the item in SfDataGrid. You can use this event to get the SelectedItem, SelectedValue. [SelectionChangedEventArgs](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.SelectionChangedEventArgs.html) provides data for `SelectionChanged` event.

{% tabs %}
{% highlight c# %}
MultiColumnDropDown.SelectionChanged += MultiColumnDropDown_SelectionChanged;

void MultiColumnDropDown_SelectionChanged(object sender, Syncfusion.UI.Xaml.Grid.SelectionChangedEventArgs args)
{
     var selectedValue = (sender as SfMultiColumnDropDownControl).SelectedValue;
}
{% endhighlight %}
{% endtabs %}

N> SelectionChanged event will not be triggered when SelectionMode is Multiple.