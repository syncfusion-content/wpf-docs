---
layout: post
title: TreeViewVirtualization
description: TreeViewVirtualization
platform: wpf
control: TreeViewAdv
documentation: ug
---
# TreeViewVirtualization

The TreeViewVirtualization feature enables users to reduce the loading time of TreeViewItems regardless of the items count.

VirtualizationMode: Sets the virtualization mode for TreeViewItems. If VirtualizationMode is set to Normal, virtualization logic is handled internally. If VirtualizationMode is set to Extended, then the class used for creating the business object for the TreeViewItem has to implement the IVirtualTree interface.

## VirtualizationMode is Normal

Virtualization is processed internally (without IVirtualTree).

{% tabs %}

{% highlight XAML %}
<syncfusion:TreeViewAdv Name="treeViewAdv" ItemsSource="{Binding MyItems}" IsVirtualizing="True" VirtualizationMode="Normal" >

</syncfusion:TreeViewAdv>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}
treeViewAdv.IsVirtualizing = true;

treeViewAdv.VirtualizationMode = VirtualizationMode.Normal;

{% endhighlight %}

{% highlight VB %}

{% endhighlight %}

{% endtabs %}  


## VirtualizationMode is Extended

IVirtualTree interface has to be implemented by the class creating the business object for TreeViewItem.

{% tabs %}

{% highlight XAML %}
<syncfusion:TreeViewAdv Name="treeViewAdv" AllowDragDrop="True" IsVirtualizing="True" VirtualizationMode="Extended" >

<syncfusion:TreeViewAdv.DataContext>

<local:ViewModel />

</syncfusion:TreeViewAdv.DataContext>

<syncfusion:TreeViewAdv.ItemTemplate>

<HierarchicalDataTemplate  ItemsSource="{Binding Items}">

<TextBlock Text="{Binding Header}"/>

</HierarchicalDataTemplate>

</syncfusion:TreeViewAdv.ItemTemplate>

</syncfusion:TreeViewAdv>


{% endhighlight %}

{% endtabs %}

{% highlight C# %}
treeViewAdv.IsVirtualizing = true;

treeViewAdv.VirtualizationMode = VirtualizationMode.Extended;

{% endhighlight %}

{% highlight VB %}

{% endhighlight %}

{% endtabs %}  

### Implementing IVirtualTree Interface:

**ViewModel** **class****:******

{% tabs %}

{% highlight C# %}
public class ViewModel

{

public ObservableCollection<MyTreeView> MyItems

{

get;

set;

}

public ViewModel()

{

MyItems = new ObservableCollection<MyTreeView>();

for (int i = 0; i < 1000; i++)

{

MyTreeView myitem = new MyTreeView() { Header = "Module " + 

i.ToString() };

for (int j = 0; j < 100; j++)

{

MyTreeView _myitem = new MyTreeView() { Header = "Sub Module " + j.ToString() };

myitem.Items.Add(_myitem);

}

MyItems.Add(myitem);

}

}

}

{% endhighlight %}

{% highlight VB %}

{% endhighlight %}

{% endtabs %}  

**Model** **class** **with** **IVirtualTree******

{% tabs %}

{% highlight C# %}
public class Model : IVirtualTree

{

public Model()

{

items = new ObservableCollection<Model>();

}

private string header;

public string Header

{

Get

{

return header;

}

Set

{

header = value;

}

}

private ObservableCollection<Model> items;

public ObservableCollection<Model> Items

{

Get

{

return items;

}

Set

{

items = value;

}

}

public double ExtentHeight

{

get;

set;

}

public bool IsExpanded

{

get;

set;

}

public int ItemsCount

{

get;

set;

}

public IVirtualTree Parent

{

get;

set;

}

public bool IsSelected

{

get;

set;

}

}

{% endhighlight %}

{% highlight VB %}

{% endhighlight %}

{% endtabs %}  

