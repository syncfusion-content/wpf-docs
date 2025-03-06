---
layout: post
title: Editing in WPF TreeView control | Syncfusion®
description: Learn here all about Editing support in Syncfusion® WPF TreeView (SfTreeView) control, its elements and more.
platform: wpf
control: SfTreeView
documentation: ug
---

# Editing in WPF TreeView (SfTreeView)

The TreeView provides support for editing and it can be enabled or disabled by using [SfTreeView.AllowEditing](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.SfTreeView.html#Syncfusion_UI_Xaml_TreeView_SfTreeView_AllowEditing) property. You can enter edit mode in a node by pressing <kbd>F2</kbd> key and also by single click or double click by setting [EditTrigger](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.SfTreeView.html#Syncfusion_UI_Xaml_TreeView_SfTreeView_EditTrigger) property. The editing changes in a node will be committed only when user move to next node or pressing <kbd>Enter</kbd> key.

It is necessary to define [EditTemplate](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.SfTreeView.html#Syncfusion_UI_Xaml_TreeView_SfTreeView_EditTemplate) / [EditTemplateSelector](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.SfTreeView.html#Syncfusion_UI_Xaml_TreeView_SfTreeView_EditTemplateSelector) for bound mode, to enable editing. For UnboundMode, textbox will be loaded in edit mode by default.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfTreeView x:Name="sfTreeView" 
                               ItemsSource="{Binding Items}"    
                               ChildPropertyName="Files"
                               AutoExpandMode="RootNodes"
                               AllowEditing="True"
                               >
    <syncfusion:SfTreeView.ItemTemplate>
        <DataTemplate>
            <TextBlock Text="{Binding Name}" VerticalAlignment="Center"/>
        </DataTemplate>
    </syncfusion:SfTreeView.ItemTemplate>
    <syncfusion:SfTreeView.EditTemplate>
        <DataTemplate>
            <TextBox Text="{Binding Name}" 
					 VerticalContentAlignment="Center" 
                     Margin="-4,0,-4,0"
                     Height="{Binding ItemHeight,ElementName=sfTreeView}" />
        </DataTemplate>
    </syncfusion:SfTreeView.EditTemplate>
</syncfusion:SfTreeView>
{% endhighlight %}
{% highlight c# %}
sfTreeView.AllowEditing = true;
{% endhighlight %}
{% endtabs %}

![WPF TreeView in Edit Mode](Editing_images/wpf-treeview-in-edit-mode.png)

## Edit mode

By default, you can move to edit mode by pressing <kbd>F2</kbd> key. TreeView allows you to edit the node in single click(Tap) or double click(DoubleTap) by setting [EditTrigger](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.SfTreeView.html#Syncfusion_UI_Xaml_TreeView_SfTreeView_EditTrigger) property.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfTreeView x:Name="sfTreeView" 
                       ItemsSource="{Binding Countries}"
                       AutoExpandMode="RootNodes"
                       EditTrigger="DoubleTap"
                       AllowEditing="True"/>

{% endhighlight %}
{% highlight c# %}

this.sfTreeView.EditTrigger = Syncfusion.UI.Xaml.TreeView.TreeViewEditTrigger.DoubleTap;

{% endhighlight %}
{% endtabs %}

## Programmatic Editing

### Begin the editing

The TreeView allows you to edit the node programmatically by calling the [BeginEdit](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.SfTreeView.html#Syncfusion_UI_Xaml_TreeView_SfTreeView_BeginEdit_Syncfusion_UI_Xaml_TreeView_Engine_TreeViewNode_) method.

{% tabs %}
{% highlight c# %}
this.sfTreeView.Loaded += TreeView_Loaded;

private void TreeView_Loaded(object sender, RoutedEventArgs e)
{
    this.sfTreeView.BeginEdit(this.sfTreeView.Nodes[0]);
}
{% endhighlight %}
{% endtabs %}

N> [CurrentItem](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.SfTreeView.html#Syncfusion_UI_Xaml_TreeView_SfTreeView_CurrentItem) is set to the node when the BeginEdit is called.

### End the editing

You can call [EndEdit](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.SfTreeView.html#Syncfusion_UI_Xaml_TreeView_SfTreeView_EndEdit_Syncfusion_UI_Xaml_TreeView_Engine_TreeViewNode_) method to programmatically end the editing for specific node.

{% tabs %}
{% highlight c# %}
this.sfTreeView.Loaded += TreeView_Loaded;

private void TreeView_Loaded(object sender, RoutedEventArgs e)
{
    this.sfTreeView.EndEdit(this.sfTreeView.Nodes[0]);
}
{% endhighlight %}
{% endtabs %}

## Revert the edited changes while pressing Escape key

By default, TreeView does not have support for rollback the changes when pressing the <kbd>ESC</kbd> key while editing the TreeView node. But it supports to rollback the changes when an underlying data object implements the [IEditableObject](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.ieditableobject?redirectedfrom=MSDN&view=net-5.0) interface.

The user can take a backup of existing data of a node in the [BeginEdit](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.ieditableobject.beginedit?redirectedfrom=MSDN&view=net-5.0#System_ComponentModel_IEditableObject_BeginEdit) method and can change the existing data to the current data in the [CancelEdit](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.ieditableobject.canceledit?redirectedfrom=MSDN&view=net-5.0#System_ComponentModel_IEditableObject_CancelEdit) method to rollback the changes.

The below code snippet explains the simple implementation of IEditableObject interface to rollback the changes.

{% tabs %}
{% highlight c# %}
public class Country : INotifyPropertyChanged, IEditableObject
{
    private bool isSelected;
    internal string name;
    private ObservableCollection<State> states;
    internal Country backUpData;
    private Country currentData;

    public Country()
    {
	
    }

    public Country(string name):base()
    {
        this.currentData = new Country();
        this.currentData.name = name;
        this.currentData.isSelected = false;
    }


    public ObservableCollection<State> States
    {
        get 
        { 
            return states; 
        }
        set
        {
            states = value;
            RaisedOnPropertyChanged("States");
        }
    }

    public string Name
    {
        get
        { 
            return this.currentData.name; 
        }
        set
        {
            this.currentData.name = value;
            RaisedOnPropertyChanged("Name");
        }
    }

    public bool IsSelected
    {
        get 
        { 
            return this.currentData.isSelected; 
        }
        set
        {
            this.currentData.isSelected = value;
            RaisedOnPropertyChanged("IsSelected");
        }
    }



    public event PropertyChangedEventHandler PropertyChanged;

    public void RaisedOnPropertyChanged(string _PropertyName)
    {
        if (PropertyChanged != null)
        {
            PropertyChanged(this, new PropertyChangedEventArgs(_PropertyName));
        }
    }


    public void BeginEdit()
    {
        Debug.WriteLine("BeginEdit is Called.");
        backUpData = new Country();
        backUpData.name = this.currentData.name;
        backUpData.isSelected = this.currentData.isSelected;
    }

    public void CancelEdit()
    {
        Debug.WriteLine("CancelEdit is Called.");
        this.currentData = backUpData;
    }

    public void EndEdit()
    {
        Debug.WriteLine("EndEdit is Called.");
    }
}
{% endhighlight %}
{% endtabs %}

N> View sample in [GitHub](https://github.com/syncfusion/wpf-demos/blob/master/treeview/Views/EditingDemo.xaml)

## Events

### ItemBeginEdit Event

The [ItemBeginEdit](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.SfTreeView.html#Syncfusion_UI_Xaml_TreeView_SfTreeView_ItemBeginEdit) event occurs when the node enters edit mode. The [TreeViewItemBeginEditEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.TreeViewItemBeginEditEventArgs.html) has the following members which provides information about the `ItemBeginEdit` event.

* [Node](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.TreeViewItemEditEventArgs.html#Syncfusion_UI_Xaml_TreeView_TreeViewItemEditEventArgs_Node) : Gets the [TreeViewNode](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.Engine.TreeViewNode.html) which is being edited.

You can cancel the editing of certain nodes using custom logic within this event by setting `TreeViewItemBeginEditEventArgs.Cancel` as true.

{% tabs %}
{% highlight c# %}
sfTreeView.ItemBeginEdit += TreeView_ItemBeginEdit;

private void TreeView_ItemBeginEdit(object sender, TreeViewItemBeginEditEventArgs e)
{
    if (e.Node.Content == "Grains")
		e.Cancel = true;
}
{% endhighlight %}
{% endtabs %}

### ItemEndEdit Event

The [ItemEndEdit](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.SfTreeView.html#Syncfusion_UI_Xaml_TreeView_SfTreeView_ItemEndEdit) event occurs when the node leaves the edit mode. The [TreeViewItemEndEditEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.TreeViewItemEndEditEventArgs.html) has the following members which provides information about the `ItemEndEdit` event.

* [Node](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.TreeViewItemEditEventArgs.html#Syncfusion_UI_Xaml_TreeView_TreeViewItemEditEventArgs_Node) : Gets the [TreeViewNode](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.Engine.TreeViewNode.html) which is being edited.

You can cancel the editing from being ended for certain nodes using custom logic within this event by setting `TreeViewItemEndEditEventArgs.Cancel` as true.

{% tabs %}
{% highlight c# %}
sfTreeView.ItemEndEdit += TreeView_ItemEndEdit;

private void TreeView_ItemEndEdit(object sender, TreeViewItemEndEditEventArgs e)
{
	if (e.Node.Content == "Cereals")
		e.Cancel = true;
}
{% endhighlight %}
{% endtabs %}

N> You can refer to our [WPF TreeView](https://www.syncfusion.com/wpf-controls/treeview) feature tour page for its groundbreaking feature representations. You can also explore our [WPF TreeView example](https://github.com/syncfusion/wpf-demos) to knows how to represents hierarchical data in a tree-like structure with expand and collapse node options.
