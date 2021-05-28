---
layout: post
title: Sorting Mode in WPF Card View control | Syncfusion
description: Learn about Sorting Mode support in Syncfusion Essential Studio WPF Card View control, its elements and more details.
platform: wpf
control: CardView
 documentation: ug
---

# Sorting Mode in WPF Card View

This section describes how to enable or disable the sorting mode and perform sort operations in [CardView](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.CardView.html) control.

## Enable/disable the sorting mode

You can enable or disable the sorting mode of card items by setting the [CanSort](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.CardView.html#Syncfusion_Windows_Tools_Controls_CardView_CanSort) property value as `true` or `false`. The default value of `CanSort` property is `true`.

{% tabs %}
{% highlight xaml %}

<syncfusion:CardView CanSort="True" 
					 Name="cardView"/>

{% endhighlight %}
{% highlight c# %}

cardView.CanSort = true;

{% endhighlight %}
{% endtabs %}

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-card-view-examples/blob/master/Samples/Editing)

## Sort the CardViewItems

You can sort the cards inside the `CardView` control either default order, ascending or descending order by clicking the field name listed in the header. If you want to disable the sorting, use the [CanSort](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.CardView.html#Syncfusion_Windows_Tools_Controls_CardView_CanSort) property value as `false`.

{% tabs %}
{% highlight c# %}

//Model.cs
public class CardViewModel
{
    public string FirstName { get; set; }
    public string LastName { get; set; }
    public int Age { get; set; }
}

//ViewModel.cs
public class ViewModel : NotificationObject
{
    private ObservableCollection<CardViewModel> cardViewItems;
    public ObservableCollection<CardViewModel> CardViewItems
    {
        get { return cardViewItems; }
        set { cardViewItems = value;
            this.RaisePropertyChanged(nameof(CardViewItems)); }
    }
    public ViewModel()
    {
        CardViewItems = new ObservableCollection<CardViewModel>();
        populateItems();
    }
    private void populateItems()
    {
        CardViewItems.Add(new CardViewModel() { FirstName = "John", LastName= "Paulin", Age = 23});
        CardViewItems.Add(new CardViewModel() { FirstName = "Mark", LastName = "Paulin",Age = 26 });
        CardViewItems.Add(new CardViewModel() { FirstName = "Steven", LastName = "John", Age = 25 });
        CardViewItems.Add(new CardViewModel() { FirstName = "John", LastName = "Steven", Age = 23 });
        CardViewItems.Add(new CardViewModel() { FirstName = "Steven", LastName = "Smith", Age = 25 });
    }
}

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight XAML %}

<syncfusion:CardView CanSort="True" 
                     ItemsSource="{Binding CardViewItems}"
					 Name="cardView">
    <syncfusion:CardView.HeaderTemplate>
        <DataTemplate>
            <TextBlock Text="{Binding FirstName}"/>
        </DataTemplate>
    </syncfusion:CardView.HeaderTemplate>
    <syncfusion:CardView.ItemTemplate>
        <DataTemplate >
            <ListBox ScrollViewer.HorizontalScrollBarVisibility="Disabled">
                <ListBoxItem Padding="1">
                    <Grid>
                        <Grid.ColumnDefinitions>
                            <ColumnDefinition Width="75" />
                            <ColumnDefinition />
                        </Grid.ColumnDefinitions>
                        <TextBlock Text="First Name:" />
                        <TextBlock Grid.Column="1"
                                   Text="{Binding FirstName,
                                          UpdateSourceTrigger=PropertyChanged}" />
                    </Grid>
                </ListBoxItem>
                <ListBoxItem Padding="1">
                    <Grid>
                        <Grid.ColumnDefinitions>
                            <ColumnDefinition Width="75" />
                            <ColumnDefinition Width="*" />
                        </Grid.ColumnDefinitions>
                        <TextBlock Text="Last Name:" />
                        <TextBlock Grid.Column="1" 
                                   Text="{Binding LastName, 
                                          UpdateSourceTrigger=PropertyChanged}" />
                    </Grid>
                </ListBoxItem>
                <ListBoxItem Padding="1">
                    <Grid>
                        <Grid.ColumnDefinitions>
                            <ColumnDefinition Width="75" />
                            <ColumnDefinition Width="*" />
                        </Grid.ColumnDefinitions>
                        <TextBlock Text="Age:" />
                        <TextBlock Grid.Column="1"
                                   Text="{Binding Age,
                                          UpdateSourceTrigger=PropertyChanged}" />
                    </Grid>
                </ListBoxItem>
            </ListBox>
        </DataTemplate>
    </syncfusion:CardView.ItemTemplate>        
</syncfusion:CardView>

{% endhighlight %}
{% highlight c# %}

cardView.CanSort = true;

{% endhighlight %}
{% endtabs %}

![wpf card view items sorted in ascending and descending order](Grouping-Sorting-Filtering_images/sorting.gif)

Here, `CardViewItems` sorted based on `FirstName` field.

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-card-view-examples/blob/master/Samples/Editing)

## Sort the grouped CardViewItems

You can sort the grouped items either default order, ascending or descending order by directly clicking the grouped fields that is available in the dropping region of the `CardView` header.

{% tabs %}
{% highlight XAML %}

<syncfusion:CardView CanSort="True"
                     CanGroup="True"
                     ItemsSource="{Binding CardViewItems}"
					 Name="cardView"/>

{% endhighlight %}
{% highlight c# %}

cardView.CanGroup = true;
cardView.CanSort = true;

{% endhighlight %}
{% endtabs %}

![wpf card view control sort the grouped items](Grouping-Sorting-Filtering_images/Sorting_groupedheader.gif)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-card-view-examples/blob/master/Samples/Editing)

## Hide the sorting header

You can hide the sorting header by using the [ShowHeader](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.CardView.html#Syncfusion_Windows_Tools_Controls_CardView_ShowHeader) property value as `false`. The default value of `ShowHeader` property is `true`.

{% tabs %}
{% highlight XAML %}

<syncfusion:CardView ShowHeader="False" 
                     ItemsSource="{Binding CardViewItems}"
					 Name="cardView"/>
{% endhighlight %}
{% highlight c# %}

cardView.ShowHeader = false;

{% endhighlight %}
{% endtabs %}

![wpf card view control hides the sort header](Grouping-Sorting-Filtering_images/hidegroupheader.png)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-card-view-examples/blob/master/Samples/Editing)
