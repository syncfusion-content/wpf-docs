---
layout: post
title: Data Binding in WPF TabControl | Syncfusion
description: Learn here about the Data Binding support in Syncfusion WPF TabControl and how to bind the properties.
platform: wpf
control: TabControl
documentation: ug
---

# Data Binding in WPF TabControl

The [TabControl](https://help.syncfusion.com/cr/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.TabControlExt.html) can bound to an external source to auto create tabs and display the data using `ItemsSource` property.

## Binding ItemsSource

The TabControl auto generates the tabitem's based on the data source set to [TabControlExt.ItemsSource](https://docs.microsoft.com/en-us/dotnet/api/system.windows.controls.itemscontrol.itemssource?redirectedfrom=MSDN&view=netframework-4.8#System_Windows_Controls_ItemsControl_ItemsSource).

N> TabControl auto creates the tabitem's only if [ItemTemplate](https://docs.microsoft.com/en-us/dotnet/api/system.windows.controls.itemscontrol.itemtemplate?view=netframework-4.8) or `HeaderTemplate` in [ItemContainerStyle](https://docs.microsoft.com/en-us/dotnet/api/system.windows.controls.itemscontrol.itemcontainerstyle?view=netframework-4.8) property is defined.

If the data source implements [INotifyCollectionChanged](https://msdn.microsoft.com/en-us/library/System.Collections.Specialized.INotifyCollectionChanged) interface, then TabControl will automatically refresh the UI when item is added, removed or cleared in the collection. When an item is added or removed in [ObservableCollection](https://docs.microsoft.com/en-us/dotnet/api/system.collections.objectmodel.observablecollection-1?redirectedfrom=MSDN&view=netframework-4.8), TabControl automatically refresh the UI as `ObservableCollection` implements `INotifyCollectionChanged`. But when an item is added or removed in List, TabControl will not refresh the UI automatically.

To bind `ItemsSource` to TabControl, you need to have collection with data object which holds header and content details.

Here, Model class defined with Header and Content properties and ViewModel class has TabItems property.

**Model.cs:**

{% tabs %}

{% highlight C# %}

public class Model
{
    private string header;
    public string Header
    {
        get { return header; }
        set
        {
            header = value;
            this.RaisePropertyChanged("Header");
        }
    }
    private string content;
    public string Content
    {
        get { return content; }
        set
        {
            content = value;
            this.RaisePropertyChanged("Content");
        }
    }
    public Model()
    {
    }
}

{% endhighlight %}

{% endtabs %}

**ViewModel.cs:**

{% tabs %}

{% highlight C# %}

public class ViewModel : NotificationObject
{
    private ObservableCollection<Model> tabItems;
    public ObservableCollection<Model> TabItems
    {
        get { return tabItems; }
        set 
        { 
            tabItems = value;
            this.RaisePropertyChanged("TabItems"); 
        }
    }
    public ViewModel()
    {
        tabItems = new ObservableCollection<Model>();
        PopulateCollection();
    }
    private void PopulateCollection()
    {
        Model model = new Model() { Header = "tab1", Content="First tab" };
        tabItems.Add(model);    
    }
}

{% endhighlight %}

{% endtabs %}

In the below code, `ViewModel` bound to TabControl and `ItemContainerStyle.HeaderTemplate` and `ItemTemplate` are defined to populate TabControl with content and header.

{% tabs %}

{% highlight XAML %}

<Window.DataContext>
        <local:ViewModel />
</Window.DataContext>
 <Grid>
    <syncfusion:TabControlExt X:Name="tabControl" 
                              Height="100" Width="280" 
                              ItemsSource="{Binding TabItems}" />
        <syncfusion:TabControlExt.ItemContainerStyle>
            <Style TargetType="syncfusion:TabItemExt">
                <Setter Property="HeaderTemplate">
                    <Setter.Value>
                        <DataTemplate>
                            <TextBlock Text="{Binding Header, Mode=TwoWay}" />
                        </DataTemplate>
                    </Setter.Value>
                </Setter>
                <Setter Property="Content" Value="{Binding Content, Mode=TwoWay}" />
            </Style>
        </syncfusion:TabControlExt.ItemContainerStyle>
    </syncfusion:TabControlExt>
</Grid>

{% endhighlight %}

{% endtabs %}

Another way, using `ItemTemplate` property.

{% tabs %}

{% highlight XAML %}

<Window.DataContext>
        <local:ViewModel />
</Window.DataContext>
<Grid>
    <syncfusion:TabControlExt x:Name="tabControl"  
                              ItemsSource="{Binding TabItems}">
        <syncfusion:TabControlExt.ItemTemplate>
            <DataTemplate>
                <TextBlock Text="{Binding Header, Mode=TwoWay}" />
            </DataTemplate>
        </syncfusion:TabControlExt.ItemTemplate>            
        <syncfusion:TabControlExt.ItemContainerStyle>
            <Style TargetType="syncfusion:TabItemExt">
                <Setter Property="Content" Value="{Binding Content, Mode=TwoWay}" />
            </Style>
        </syncfusion:TabControlExt.ItemContainerStyle>
    </syncfusion:TabControlExt>
</Grid>

{% endhighlight %}

{% endtabs %}


## TabItem Header

When you are auto generating tabitem's using `ItemsSource`, you need to set [TabControlExt.ItemContainerStyle](https://docs.microsoft.com/en-us/dotnet/api/system.windows.controls.itemscontrol.itemcontainerstyle?view=netframework-4.8) and set the tabitem name using [TabItemExt.HeaderTemplate](https://docs.microsoft.com/en-us/dotnet/api/system.web.ui.webcontrols.templatefield.headertemplate?view=netframework-4.8). Otherwise, TabItem header will display the data object class name which is associated with tabitem.

{% tabs %}

{% highlight XAML %}

<Window.DataContext>
        <local:ViewModel />
</Window.DataContext>
<Grid>
    <syncfusion:TabControlExt x:Name="tabControl" 
                          Height="100" Width="280" 
                          ItemsSource="{Binding TabItems}">
        <syncfusion:TabControlExt.ItemContainerStyle>
            <Style TargetType="syncfusion:TabItemExt">
                <Setter Property="HeaderTemplate">
                    <Setter.Value>
                        <DataTemplate>
                            <TextBlock Text="{Binding Header, Mode=TwoWay}" />
                        </DataTemplate>
                    </Setter.Value>
                </Setter>
            </Style>
        </syncfusion:TabControlExt.ItemContainerStyle>
    </syncfusion:TabControlExt>
</Grid>

{% endhighlight %}

{% endtabs %}

Another way, using `ItemTemplate` property.

When you are auto generating tabitem's using ItemsSource, you need to set [TabControlExt.ItemTemplate](https://docs.microsoft.com/en-us/dotnet/api/system.windows.controls.itemscontrol.itemtemplate?view=netframework-4.8). Otherwise, TabItem header will display the data object class name which is associated with tabitem.

{% tabs %}

{% highlight XAML %}

<Window.DataContext>
        <local:ViewModel />
</Window.DataContext>
<Grid>
    <syncfusion:TabControlExt x:Name="tabControl" 
                          Height="100" Width="280" 
                          ItemsSource="{Binding TabItems}">
        <syncfusion:TabControlExt.ItemTemplate>
            <DataTemplate>
                <TextBlock Text="{Binding Header}"/>
            </DataTemplate>
        </syncfusion:TabControlExt.ItemTemplate>
    </syncfusion:TabControlExt>
</Grid>

{% endhighlight %}

{% endtabs %}

Here, Model class defined with Header property and ViewModel class has TabItems property.

**Model.cs:**

{% tabs %}

{% highlight C# %}

public class Model : NotificationObject
{
    public Model()
    {
    }
    private string header;
    public string Header
    {
        get { return header; }
        set
        {
            header = value;
            this.RaisePropertyChanged("Header");
        }
    }
}

{% endhighlight %}

{% endtabs %}

**ViewModel.cs:**

{% tabs %}

{% highlight C# %}

public class ViewModel : NotificationObject
{
    private ObservableCollection<Model> tabItems;
    public ObservableCollection<Model> TabItems
    {
        get { return tabItems; }
        set { tabItems = value; }
    }
    public ViewModel()
    {
        tabItems = new ObservableCollection<Model>();
        PopulateCollection();
    }
    private void PopulateCollection()
    {
        Model model = new Model() { Header = "tab1" };
        Model model1 = new Model() { Header = "tab2" };
        tabItems.Add(model);
        tabItems.Add(model1);
    }
}

{% endhighlight %}

{% endtabs %}

![Added header to tabitem in WPF TabControl](Databinding_images/wpf-tabcontrol-binding_header.png)

## TabItem content

When you are auto generating tabitem's using `ItemsSource`, You need to set [TabControlExt.ItemContainerStyle](https://docs.microsoft.com/en-us/dotnet/api/system.windows.controls.itemscontrol.itemcontainerstyle?view=netframework-4.8). Otherwise, TabItem content will display the data object class name which is associated with tabitem.

{% tabs %}

{% highlight XAML %}

<Window.DataContext>
        <local:ViewModel />
</Window.DataContext>
<Grid>
    <syncfusion:TabControlExt x:Name="tabControl" 
                          Height="100" Width="280" 
                          ItemsSource="{Binding TabItems}"
                          >
        <syncfusion:TabControlExt.ItemContainerStyle>
            <Style TargetType="syncfusion:TabItemExt" >
                <Setter Property="Content" Value="{Binding Content, Mode=TwoWay}" />            
            </Style>
        </syncfusion:TabControlExt.ItemContainerStyle>
    </syncfusion:TabControlExt>    
</Grid>

{% endhighlight %}

{% endtabs %}

Here, Model class defined with Content property and ViewModel class has TabItems property.

**Model.cs:**

Create a Model class with tabitem property.

{% tabs %}

{% highlight C# %}

private string content;
public string Content
{
    get { return content; }
    set
    {
        content = value;
        this.RaisePropertyChanged("Content");
    }
}

{% endhighlight %}

{% endtabs %}


**ViewModel.cs:**

{% tabs %}

{% highlight C# %}

public class ViewModel : NotificationObject
{
    private ObservableCollection<Model> tabItems;
    public ObservableCollection<Model> TabItems
    {
        get { return tabItems; }
        set { tabItems = value; }
    }
    public ViewModel()
    {
        tabItems = new ObservableCollection<Model>();
        PopulateCollection();
    }
    private void PopulateCollection()
    {
        Model model = new Model() { Header = "tab1", Content="First tab" };
        Model model1 = new Model() { Header = "tab2", Content="Second tab" };
        tabItems.Add(model);
        tabItems.Add(model1);
    }
}

{% endhighlight %}

{% endtabs %}

![Added content to tabitem in WPF TabControl](Databinding_images/wpf-tabcontrol-binding_content.png)
