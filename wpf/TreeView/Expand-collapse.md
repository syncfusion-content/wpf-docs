---
layout: post
title: Expand and Collapse in WPF TreeView control | Syncfusion
description: Learn here all about Expand and Collapse support in Syncfusion WPF TreeView (SfTreeView) control and more.
platform: wpf
control: SfTreeView
documentation: ug
---

# Expand and Collapse in WPF TreeView (SfTreeView)

The [WPF TreeView](https://www.syncfusion.com/wpf-controls/treeview) allows you to expand and collapse the nodes either by user interaction on the nodes or by programmatically. 

##  Expand Action Trigger

 Expanding and Collapsing of nodes can be performed either by tapping the expander view or in both expander view and content view by setting the [ExpandActionTrigger](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.SfTreeView.html#Syncfusion_UI_Xaml_TreeView_SfTreeView_ExpandActionTrigger) property.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfTreeView x:Name="sfTreeView"  ExpandActionTrigger="Node" />

{% endhighlight %}
{% highlight c# %}

// Expands by tapping both expander view and content view.
sfTreeView.ExpandActionTrigger = ExpandActionTrigger.Node;

{% endhighlight %}
{% endtabs %}

## Auto Expand Mode

By default, the treeview items will be in collapsed state. You can define how the nodes to be expanded while loading the TreeView by using [AutoExpandMode](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.SfTreeView.html#Syncfusion_UI_Xaml_TreeView_SfTreeView_AutoExpandMode) property.

The `AutoExpandMode` property is only applicable for bound mode. For Unbound mode you need to set `IsExpanded` property to `true` while creating the nodes, to be in expanded state while loading the TreeView.

* None : All items are collapsed when loaded.
* RootNodes : Expands only the root item when loaded.
* AllNodes : Expands all the items when loaded.

## Expand or collapse the nodes based on property of underlying data object

You can bind expand state of node to the bool property in underlying data object by using [IsExpandedPropertyName](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.Engine.HierarchyPropertyDescriptor.html#Syncfusion_UI_Xaml_TreeView_Engine_HierarchyPropertyDescriptor_IsExpandedPropertyName) property. TreeView updates the expanded of node when underlying data object property gets changed and vice versa.

{% tabs %}
{% highlight xaml %}

xmlns:treeviewengine="clr-namespace:Syncfusion.UI.Xaml.TreeView.Engine;assembly=Syncfusion.SfTreeView.WPF"

<syncfusion:SfTreeView x:Name="treeView"
         ItemsSource="{Binding Folders}">
    <syncfusion:SfTreeView.HierarchyPropertyDescriptors>        
        <treeviewengine:HierarchyPropertyDescriptor IsExpandedPropertyName="IsExpanded" ChildPropertyName="SubFiles" TargetType="{x:Type local:FileManager}" />
    </syncfusion:SfTreeView.HierarchyPropertyDescriptors>
</syncfusion:SfTreeView>

{% endhighlight %}
{% highlight c# %}

public class FileManager : INotifyPropertyChanged
{
    private string fileName;        
    private ObservableCollection<FileManager> subFiles;
    private bool isExpanded;

    public ObservableCollection<FileManager> SubFiles
    {
        get { return subFiles; }
        set
        {
            subFiles = value;
            RaisedOnPropertyChanged("SubFiles");
        }
    }

    public string ItemName
    {
        get { return fileName; }
        set
        {
            fileName = value;
            RaisedOnPropertyChanged("ItemName");
        }
    }

    public bool IsExpanded
    {
        get { return isExpanded; }
        set
        {
            isExpanded = value;
            RaisedOnPropertyChanged("IsExpanded");
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
}


public class FileManagerViewModel
{
    private ObservableCollection<FileManager> folders;

    public FileManagerViewModel()
    {
        GenerateSource();            
    }

    public ObservableCollection<FileManager> Folders
    {
        get { return folders; }
        set { this.folders = value; }
    }

    private void GenerateSource()
    {
        var fileManager = new ObservableCollection<FileManager>();
        
        var doc = new FileManager() { ItemName = "Documents", IsExpanded = true };
        var download = new FileManager() { ItemName = "Downloads",  IsExpanded = false };
        
        var pollution = new FileManager() { ItemName = "Environmental Pollution.docx"};
        var globalWarming = new FileManager() { ItemName = "Global Warming.ppt" };
        var sanitation = new FileManager() { ItemName = "Sanitation.docx"};
        var socialNetwork = new FileManager() { ItemName = "Social Network.pdf" };
        var youthEmpower = new FileManager() { ItemName = "Youth Empowerment.pdf" };

        var games = new FileManager() { ItemName = "Game.exe" };
        var tutorials = new FileManager() { ItemName = "Tutorials.zip" };
        var TypeScript = new FileManager() { ItemName = "TypeScript.7z"};
        var uiGuide = new FileManager() { ItemName = "UI-Guide.pdf"};
        
        doc.SubFiles = new ObservableCollection<FileManager>
        {
            pollution,
            globalWarming,
            sanitation,
            socialNetwork,
            youthEmpower
        };
     
        download.SubFiles = new ObservableCollection<FileManager>
        {
            games,
            tutorials,
            TypeScript,
            uiGuide
        };
    
        fileManager.Add(doc);
        fileManager.Add(download);
     
        folders = fileManager;
    }
}

{% endhighlight %}
{% endtabs %}

N> `IsExpandedPropertyName` property is not supported for unbound mode and it accepts only boolean type property.

## Programmatic Expand and Collapse

TreeView allows programmatic expand and collapse based on the [TreeViewNode](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.Engine.TreeViewNode.html) and level by using following methods.

* [ExpandNode(TreeViewNode item)](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.SfTreeView.html#Syncfusion_UI_Xaml_TreeView_SfTreeView_ExpandNode_Syncfusion_UI_Xaml_TreeView_Engine_TreeViewNode_) - Method to expand the particular `TreeViewNode` passed to it.
* [CollapseNode(TreeViewNode item)](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.SfTreeView.html#Syncfusion_UI_Xaml_TreeView_SfTreeView_CollapseNode_Syncfusion_UI_Xaml_TreeView_Engine_TreeViewNode_) - Method to collapse the particular `TreeViewNode` passed to it.
* [ExpandNodes(int level)](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.SfTreeView.html#Syncfusion_UI_Xaml_TreeView_SfTreeView_ExpandNodes_System_Int32_) - Method to expand the all items of level passed to it.
* [CollapseNodes(int level)](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.SfTreeView.html#Syncfusion_UI_Xaml_TreeView_SfTreeView_CollapseNodes_System_Int32_) - Method to expand the all items of level passed to it.

{% tabs %}
{% highlight c# %}
// Expands all the nodes of root level '0'
sfTreeView.ExpandNodes(0);

// Collapses all the nodes of root level '0'
sfTreeView.CollapseNodes(0);

// Expand a particular node.
sfTreeView.ExpandNode(node);

// Collapse a particular node.
sfTreeView.CollapseNode(node);

{% endhighlight %}
{% endtabs %}

### Expand and Collapse all the nodes

Expand and Collapse all the [TreeViewNode](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.Engine.TreeViewNode.html) programmatically at runtime by using the `SfTreeView.ExpandAll` method and `SfTreeView.CollapseAll` method.

{% tabs %}
{% highlight c# %}

//Expands all the nodes
sfTreeView.ExpandAll();

//Collapses all the nodes
sfTreeView.CollapseAll();

{% endhighlight %}
{% endtabs %}

## Expand and Collapse using Keyboard

TreeView allows to expand and collapse the nodes by using right and left arrows keys. To expand a node, press the right arrow key and to collapse a node, press the left arrow key on the focused item.

## Events

TreeView exposes following events to handle expanding and collapsing of items.

* [NodeCollapsing](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.SfTreeView.html) - It occurs when a node is being collapsed.
* [NodeExpanding](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.SfTreeView.html) - It occurs when a node is being expanded.
* [NodeCollapsed](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.SfTreeView.html) - It occurs when a node is collapsed.
* [NodeExpanded](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.SfTreeView.html) - It occurs when a node is expanded.

The expanding and collapsing interactions can be handled with the help of `NodeCollapsing` and `NodeExpanding` events and expanded and collapsed interactions can be handled with help of `NodeCollapsed` and `NodeExpanded` events.

 N> You can refer to our [WPF TreeView](https://www.syncfusion.com/wpf-controls/treeview) feature tour page for its groundbreaking feature representations. You can also explore our [WPF TreeView example](https://github.com/syncfusion/wpf-demos) to knows how to represents hierarchical data in a tree-like structure with expand and collapse node options.                                                                                                                                                                                                                             
