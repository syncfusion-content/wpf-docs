---
layout: post
title: TreeViewVirtualization | Syncfusion
description: This section explains about how to reduce the loading time of the treeviewitems in TreeView for syncfusion Essential Wpf. 
platform: wpf
control: TreeViewAdv
documentation: ug
---
# Virtualization in WPF TreeView(TreeViewAdv).

The TreeViewVirtualization feature enables users to reduce the loading time of TreeViewItems regardless of the items count.

**VirtualizationMode:**

Sets the virtualization mode for TreeViewItems. If VirtualizationMode is set to Normal, virtualization logic is handled internally. If VirtualizationMode is set to Extended, then the class used for creating the business object for the TreeViewItem has to implement the IVirtualTree interface.

## VirtualizationMode is Normal

Virtualization is processed internally (without IVirtualTree).

{% tabs %}

{% highlight XAML %}

<syncfusion:TreeViewAdv Name="treeViewAdv" ItemsSource="{Binding MyItems}" IsVirtualizing="True" VirtualizationMode="Normal" >
</syncfusion:TreeViewAdv>

{% endhighlight %}

{% highlight C# %}

treeViewAdv.IsVirtualizing = true;
treeViewAdv.VirtualizationMode = VirtualizationMode.Normal;

{% endhighlight %}

{% highlight VB %}

treeViewAdv.IsVirtualizing = True
treeViewAdv.VirtualizationMode = VirtualizationMode.Normal

{% endhighlight %}

{% endtabs %}  

## VirtualizationMode is extended

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

{% highlight C# %}

treeViewAdv.IsVirtualizing = true;
treeViewAdv.VirtualizationMode = VirtualizationMode.Extended;

{% endhighlight %}

{% highlight VB %}

treeViewAdv.IsVirtualizing = True
treeViewAdv.VirtualizationMode = VirtualizationMode.Extended

{% endhighlight %}

{% endtabs %}  

### Implementing IVirtualTree interface

**ViewModel class:**

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

Public Class ViewModel
Public Property MyItems() As ObservableCollection(Of MyTreeView)
Public Sub New()
MyItems = New ObservableCollection(Of MyTreeView)()
For i As Integer = 0 To 999
Dim myitem As New MyTreeView() With {.Header = "Module " & i.ToString()}
For j As Integer = 0 To 99
Dim _myitem As New MyTreeView() With {.Header = "Sub Module " & j.ToString()}
myitem.Items.Add(_myitem)
Next j
MyItems.Add(myitem)
Next i
End Sub
End Class

{% endhighlight %}

{% endtabs %}  

**Model class with IVirtualTree**

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

Public Class Model
Implements IVirtualTree
Public Sub New()
items_Renamed = New ObservableCollection(Of Model)()
End Sub
Private header_Renamed As String
Public ReadOnly Property Header() As String
[Get]
If True Then
Return header_Renamed
End If
[Set]
If True Then
header_Renamed = value
End If
End Property
Private items_Renamed As ObservableCollection(Of Model)
Public ReadOnly Property Items() As ObservableCollection(Of Model)
[Get]
If True Then
Return items_Renamed
End If
[Set]
If True Then
items_Renamed = value
End If
End Property
Public Property ExtentHeight() As Double
Public Property IsExpanded() As Boolean
Public Property ItemsCount() As Integer
Public Property Parent() As IVirtualTree
Public Property IsSelected() As Boolean
End Class

{% endhighlight %}

{% endtabs %}  

