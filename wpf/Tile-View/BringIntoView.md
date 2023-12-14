---
layout: post
title: BringIntoView in WPF Tile View control | Syncfusion
description: Learn about BringIntoView support in Syncfusion Essential Studio WPF Tile View control, its elements and more.
platform: wpf
control: TileViewControl
documentation: ug
---

# BringIntoView in WPF Tile View

This section explains how to bring the `TileViewItem` which is out of view to view programmatically in TileView control. 

## BringIntoView

The TileViewControl allows programmatically to bring the `TileViewItem` to view using `BringIntoView` method.

### BringIntoView using TileViewItem

The below example shows how to bring the `TileViewItem` into view using the specified item.

{% tabs %}
{% highlight XAML %}

<Grid>
    <Grid.RowDefinitions>
        <RowDefinition Height="50"/>
        <RowDefinition Height="50"/>
        <RowDefinition Height="*"/>
    </Grid.RowDefinitions>

    <Button Grid.Row="0" Content="Click to bring the item18 in view" Click="Button_Click" Width="200" Height="40"/>

    <syncfusion:TileViewControl x:Name="tileViewControl"
                                Grid.Row="2" 
                                IsVirtualizing="True"                     
                                RowCount="4" 
                                ColumnCount="4"
                                HorizontalScrollBarVisibility="Visible"
                                VerticalScrollBarVisibility="Visible" >
        <syncfusion:TileViewItem x:Name="item1" Header="1" Content="1"/>
        <syncfusion:TileViewItem x:Name="item2" Header="2" Content="2"/>
        <syncfusion:TileViewItem x:Name="item3" Header="3" Content="3"/>
        <syncfusion:TileViewItem x:Name="item4" Header="4" Content="4"/>
        <syncfusion:TileViewItem x:Name="item5" Header="5" Content="5"/>
        <syncfusion:TileViewItem x:Name="item6" Header="6" Content="6"/>
        <syncfusion:TileViewItem x:Name="item7" Header="7" Content="7"/>
        <syncfusion:TileViewItem x:Name="item8" Header="8" Content="8"/>
        <syncfusion:TileViewItem x:Name="item9" Header="9" Content="9"/>
        <syncfusion:TileViewItem x:Name="item10" Header="10" Content="10"/>
        <syncfusion:TileViewItem x:Name="item11" Header="11" Content="11"/>
        <syncfusion:TileViewItem x:Name="item12" Header="12" Content="12"/>
        <syncfusion:TileViewItem x:Name="item13" Header="13" Content="13"/>
        <syncfusion:TileViewItem x:Name="item14" Header="14" Content="14"/>
        <syncfusion:TileViewItem x:Name="item15" Header="15" Content="15"/>
        <syncfusion:TileViewItem x:Name="item16" Header="16" Content="16"/>
        <syncfusion:TileViewItem x:Name="item17" Header="17" Content="17"/>
        <syncfusion:TileViewItem x:Name="item18" Header="18" Content="18"/>
        <syncfusion:TileViewItem x:Name="item19" Header="19" Content="19"/>
        <syncfusion:TileViewItem x:Name="item20" Header="20" Content="20"/>
        <syncfusion:TileViewItem x:Name="item21" Header="21" Content="21"/>
        <syncfusion:TileViewItem x:Name="item22" Header="22" Content="22"/>
        <syncfusion:TileViewItem x:Name="item23" Header="23" Content="23"/>
        <syncfusion:TileViewItem x:Name="item24" Header="24" Content="24"/>
        <syncfusion:TileViewItem x:Name="item25" Header="25" Content="25"/>
        <syncfusion:TileViewItem x:Name="item26" Header="26" Content="26"/>
        <syncfusion:TileViewItem x:Name="item27" Header="27" Content="27"/>
        <syncfusion:TileViewItem x:Name="item28" Header="28" Content="28"/>
        <syncfusion:TileViewItem x:Name="item29" Header="29" Content="29"/>
        <syncfusion:TileViewItem x:Name="item30" Header="30" Content="30"/>
    </syncfusion:TileViewControl>

</Grid>

{% endhighlight %}
{% highlight C# %}

private void Button_Click(object sender, RoutedEventArgs e)
{
    tileViewControl.BringIntoView(item18);
}

{% endhighlight %}
{% endtabs %}

### BringIntoView using Index

The below example shows how to bring the `TileViewItem` into view using the specified index.

{% tabs %}
{% highlight C# %}

private void Button_Click(object sender, RoutedEventArgs e)
{
    tileViewControl.BringIntoView(22);
}

{% endhighlight %}
{% endtabs %}

### BringIntoView using ViewModel

The below example shows how to bring the `TileViewItem` into view using a model value from ViewModel.

{% tabs %}
{% highlight XAML %}

<Grid>
    <Grid.RowDefinitions>
        <RowDefinition Height="50"/>
        <RowDefinition Height="50"/>
        <RowDefinition Height="*"/>
    </Grid.RowDefinitions>

    <Button Grid.Row="0" Content="Click to Bring the item in view" Click="Button_Click" Width="150" Height="40"/>

    <syncfusion:TileViewControl Name="tileViewControl"
                                Grid.Row="2" 
                                RowCount="4" 
                                ColumnCount="4"
                                IsVirtualizing="True"
                                HorizontalScrollBarVisibility="Visible"
                                VerticalScrollBarVisibility="Visible"
                                ItemsSource="{Binding TileViewItems}">
        <syncfusion:TileViewControl.ItemContainerStyle>
            <Style TargetType="{x:Type syncfusion:TileViewItem}">
                <Setter Property="Header" Value="{Binding Header}" />
                <Setter Property="Content" Value="{Binding Content}"/>
                <Setter Property="TileViewItemState" Value="{Binding State, Mode=TwoWay, UpdateSourceTrigger=PropertyChanged}"/>
                <Setter Property="CloseButtonVisibility" Value="Visible"/>
            </Style>
        </syncfusion:TileViewControl.ItemContainerStyle>
    </syncfusion:TileViewControl>

</Grid>

{% endhighlight %}
{% highlight C# %}

//Model.cs
public class Model :INotifyPropertyChanged
{
    public string Header { get; set; }
    public string Content { get; set; }
    
    private TileViewItemState state;
    
    public TileViewItemState State
    {
        get { return state; }
        set
        {
            state = value;
            NotifyPropertyChanged("State");
        }
    }

    public event PropertyChangedEventHandler PropertyChanged;

    private void NotifyPropertyChanged(String propertyName)
    {
        PropertyChanged?.Invoke(this, new PropertyChangedEventArgs(propertyName));
    }
    
    public Model()
    {
    }
}


//ViewModel.cs
public class ViewModel : NotificationObject
{
    private ObservableCollection<Model> tileViewItems;
    public ObservableCollection<Model> TileViewItems
    {
        get { return tileViewItems; }
        set
        {
            tileViewItems = value;
            this.RaisePropertyChanged(nameof(TileViewItems));
        }
    }

    public ViewModel()
    {
        tileViewItems = new ObservableCollection<Model>();
        PopulateCollection();
    }

    public void PopulateCollection()
    {
        for(int i = 1; i <= 50; i++)
        {
            TileViewItems.Add(new Model() { Header = "Item " + i, Content = "Content " + i, State = TileViewItemState.Normal });
        }
    }
}


//MainWindow.xaml.cs
private void Button_Click(object sender, RoutedEventArgs e)
{
    var viewmodel = this.DataContext as ViewModel;
    tileViewControl.BringIntoView(viewmodel.TileViewItems[25]);
}

{% endhighlight %}
{% endtabs %}
