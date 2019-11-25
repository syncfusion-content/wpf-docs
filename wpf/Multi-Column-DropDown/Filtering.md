---
layout: post
title: Filtering in SfMultiColumnDropDownControl.
description: How to handle the filtering in SfMultiColumnDropDownControl.
platform: wpf
control: SfMultiColumnDropDownControl
documentation: ug
---

# Filtering

SfMultiColumnDropDownControl provides support to filter the drop down display list based on typed text by setting [AllowIncrementalFiltering](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.SfMultiColumnDropDownControl~AllowIncrementalFiltering.html) as `true`. The records are filter based on `DisplayMember`. 

By default, drop down list is filtered based on `SearchCondition.StartsWith` condition. You can change the filtering search condition by setting [SearchCondition](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.SfMultiColumnDropDownControl~SearchCondition.html) (StartsWith, Contains, Equals options).

{% tabs %}
{% highlight xml %}
<syncfusion:SfMultiColumnDropDownControl x:Name="sfMultiColumn "
                                         Width="175"
                                         Height="30"
                                         AutoGenerateColumns="False"
                                         DisplayMember="CustomerName"
                                         ItemsSource="{Binding Orders}"
                                         SelectedIndex="4"
                                         ValueMember="CustomerName">
    <syncfusion:SfMultiColumnDropDownControl.Columns>
        <syncfusion:GridTextColumn MappingName="CustomerName" />
        <syncfusion:GridTextColumn MappingName="OrderID" />
        <syncfusion:GridTextColumn MappingName="CustomerID" />
        <syncfusion:GridTextColumn MappingName="Country" />
    </syncfusion:SfMultiColumnDropDownControl.Columns>
</syncfusion:SfMultiColumnDropDownControl>
{% endhighlight %}
{% endtabs %}

![](Filtering_images/Filtering_img1.png)

## Case-Sensitive Filtering

You can decides whether the automatic completion of text and the filtering are case-sensitive or not by setting [AllowCaseSensitiveFiltering](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.SfMultiColumnDropDownControl~AllowCaseSensitiveFiltering.html) as true.

## How to filter SfMultiColumnDropDownControl based on various column values

By default, SfMultiColumnDropDownControl filter the text based on `DisplayMember` (considers single column text only). You can also filter the text based on multiple columns by overriding the [FilterRecord](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.SfMultiColumnDropDownControl~FilterRecord.html) method in `SfMultiColumnDropDownControl` and use the [SearchText](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.SfMultiColumnDropDownControl~SearchText.html) property to get the entered text in editor.
 
{% tabs %}
{% highlight c# %}
public class CustomMultiColumnControl : SfMultiColumnDropDownControl
{
    /// <summary>
    /// Returns true if the item is displayed in the Filtered List, otherwise returns false.
    /// </summary>
    /// <param name="item"></param>
    /// <returns></returns>
    
    protected override bool FilterRecord(object item)
    {
        var _item = item as GrossingMoviesList;
        var result = (_item.Title.Contains(this.SearchText)) || (_item.Cast.Contains(this.SearchText));
        return result;
        }
      }
{% endhighlight %}
{% highlight xml %}
<local:CustomMultiColumnControl x:Name="sfMultiColumn"
                                Width="175"
                                Height="25"
                                AutoGenerateColumns="False"
                                DisplayMember="Title"
                                ItemsSource="{Binding MoviesLists}"
                                SelectedIndex="2"
                                ValueMember="Title">
            <local:CustomMultiColumnControl.Columns>
                <syncfusion:GridTextColumn MappingName="Title" />
                <syncfusion:GridTextColumn MappingName="Cast" />
                <syncfusion:GridTextColumn MappingName="Director" />
                <syncfusion:GridTextColumn MappingName="Rating" />
            </local:CustomMultiColumnControl.Columns>
        </local:CustomMultiColumnControl>
{% endhighlight %}
{% endtabs %}

Here, `Title` is defined as a `DisplayMember`. But it also searches the match case from the `Cast` column also while filtering.

![](Filtering_images/Filtering_img2.png)


N> Excel-like filtering is not supported in SfMultiColumnDropDownControl. You can customize the SfMultiColumnDropDownControl ControlTemplate to enable the Excel-like filtering by setting `AllowFiltering` as true in SfDataGrid.

## Filtering Delay
The SfMultiColumnDropDown provides support to set the delay in milliseconds when filtering the records in DropDown by using the FilterDelay property. The default FilterDelay is 500. 

{% tabs %}
{% highlight c# %}
this.sfmulticolumn.FilterDelay = 2000;
{% endhighlight %}
{% highlight xml %}
<syncfusion:SfMultiColumnDropDownControl x:Name="sfmulticolumn"
                                                 Width="175"
                                                 Height="30"
                                                 ItemsSource="{Binding Orders}"
                                                 DisplayMember="OrderID" 
                                                 AutoGenerateColumns="False"
                                                 FilterDelay="2000"
                                                 SelectedIndex="2">
            <syncfusion:SfMultiColumnDropDownControl.Columns>
                <syncfusion:GridTextColumn MappingName="OrderID" />
                <syncfusion:GridTextColumn MappingName="CustomerID" />
                <syncfusion:GridTextColumn MappingName="Country" />
            </syncfusion:SfMultiColumnDropDownControl.Columns>
        </syncfusion:SfMultiColumnDropDownControl>
{% endhighlight %}
{% endtabs %}

## Limitations
When setting DataTable as `ItemsSource`, `AllowIncrementalFiltering` is not supported.
