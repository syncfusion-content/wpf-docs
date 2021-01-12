---
layout: post
title: Grouping Mode in WPF Card View control | Syncfusion
description: This section describes how to enable or disable the group mode and perform group operations in WPF CardView control.
platform: wpf
control: CardView
documentation: ug
---

# Grouping Mode in WPF CardView

This section describes how to enable or disable the grouping mode and perform group operations in [CardView](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.CardView.html) control.

## Enable/disable the grouping mode

You can enable or disable the grouping mode of card items by setting the [CanGroup](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.CardView.html#Syncfusion_Windows_Tools_Controls_CardView_CanGroup) property value as `true` or `false`. The default value of `CanGroup` property is `true`.

{% tabs %}
{% highlight xaml %}

<syncfusion:CardView CanGroup="True" 
					 Name="cardView"/>

{% endhighlight %}
{% highlight c# %}

cardView.CanGroup = true;

{% endhighlight %}
{% endtabs %}

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-card-view-examples/blob/master/Samples/Editing)

## Group the CardViewItems

You can group the cards inside the `CardView` control by dragging the available field from the list and drop it into the dropping region of the `CardView` control header. Based on the dropped field, the cards are grouped.

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

<syncfusion:CardView CanGroup="True" 
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

cardView.CanGroup = true;

{% endhighlight %}
{% endtabs %}

![wpf card view items grouped based on age field](Grouping-Sorting-Filtering_images/grouping.gif)

Here, `CardViewItems` grouped based on `Age` field.

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-card-view-examples/blob/master/Samples/Editing)

## Group the cards programmatically

You can group the cards programmatically by passing the specific field name into the [GroupCards(String)](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.CardView.html#Syncfusion_Windows_Tools_Controls_CardView_GroupCards_System_String_) method. Based on the field name, cards are grouped programmatically.

{% tabs %}
{% highlight c# %}

cardView.CanGroup = true;
cardView.GroupCards("Age");

{% endhighlight %}
{% endtabs %}

Here, the cards are grouped programmatically based on the `Age` field.

![wpf card view items grouped programmatically](Grouping-Sorting-Filtering_images/porgrammaticgrouping.png)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-card-view-examples/blob/master/Samples/CardView-EditMode)

## Nested grouping of CardViewItems

You can group the card items in multiple nested level by dragging the required fields from the list and drop it into the dropping region of the `CardView` control header. Based on the fields add into the dropping region, the card items will be  grouped in nested level.

{% tabs %}
{% highlight XAML %}

<syncfusion:CardView CanGroup="True" 
                     ItemsSource="{Binding CardViewItems}"
					 Name="cardView"/>

{% endhighlight %}
{% highlight c# %}

cardView.CanGroup = true;

{% endhighlight %}
{% endtabs %}

![wpf card view items grouped with nested level](Grouping-Sorting-Filtering_images/nestedgrouping.gif)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-card-view-examples/blob/master/Samples/Editing)

## Hide the grouping header

You can hide the grouping header by using the [ShowHeader](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.CardView.html#Syncfusion_Windows_Tools_Controls_CardView_ShowHeader) property value as `false`. The default value of `ShowHeader` property is `true`.

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

![wpf card view control hides the group header](Grouping-Sorting-Filtering_images/hidegroupheader.png)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-card-view-examples/blob/master/Samples/Editing)