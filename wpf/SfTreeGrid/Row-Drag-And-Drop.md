---
layout: post
title: Row Drag and Drop | TreeGrid | WPF | Syncfusion
description: This section explains about drag and drop the rows in TreeGrid
platform: wpf
control: SfTreeGrid
documentation: ug
---

#Row drag-and-drop

SfTreeGrid allows row drag and drop within and between controls by setting [AllowDraggingRows](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid~AllowDraggingRows.html) and [AllowDrop](https://msdn.microsoft.com/en-us/library/system.windows.uielement.allowdrop(v=vs.110).aspx) properties to true. It is also possible to drag and drop between treegrid and other controls like ListView, TreeView. SfTreeGrid allows dropping when `AllowDrop` is true and allows dragging when `AllowDraggingRows` is true.

{% tabs %}
{% highlight xml %}
<syncfusion:SfTreeGrid Name="sfTreeGrid" 
                               AllowDraggingRows="True" 
                               AllowDrop="True" 
                               ChildPropertyName="ReportsTo" 
                               AutoGenerateColumns="False"                                  
                               ItemsSource="{Binding Employees}"
                               ParentPropertyName="ID"
                               SelfRelationRootValue="-1" />
{% endhighlight %}
{% highlight c# %}
sfTreeGrid.AllowDraggingRows = true;
sfTreeGrid.AllowDrop = true;
{% endhighlight %}
{% endtabs %}

![Drag and drop window while dragging in WPF treegrid](Row-Drag-and-Drop_images/Row-Drag-and-Drop_img1.jpeg)


While dropping, the dragged node(s) can be added above or below or as a child node based on its drop position. For example, if you dropped node at the bottom of targeted node, it will be added below the targeted node and if you are dropping over the targeted node, it will be added as child of that targeted node.

![Drap and drop row as child](Row-Drag-and-Drop_images/Row-Drag-and-Drop_img2.jpeg)

N> Drag indicators will not be shown when drop position is set as “Drop as child”.

## Drag multiple nodes

SfTreeGrid allows user to drag multiple selected nodes. You can enable multiple selection by setting [SfTreeGrid.SelectionMode](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.SfGridBase~SelectionMode.html) to `Multiple` or `Extended`.

![Drag and drop multiple rows](Row-Drag-and-Drop_images/Row-Drag-and-Drop_img3.jpeg)

# Events

SfTreeGrid triggers the following events during drag and drop.

## DragStart

[DragStart](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.TreeGrid.TreeGridRowDragDropController~DragStart_EV.html) event occurs when you start to drag the node in treegrid. The [TreeGridRowDragStartEventArgs](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.TreeGrid.TreeGridRowDragStartEventArgs.html) has the following member which provides information for `DragStart` event.

[DraggingNodes](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.TreeGrid.TreeGridRowDragStartEventArgs~DraggingNodes.html): Gets the TreeNode which contains the data associated while dragging the rows.
  
{% tabs %}
{% highlight c# %}
sfTreeGrid.RowDragDropController.DragStart += RowDragDropController_DragStart;

private void RowDragDropController_DragStart(object sender, Syncfusion.UI.Xaml.TreeGrid.TreeGridRowDragStartEventArgs e)
{
            
}
{% endhighlight %}
{% endtabs %}

## DragOver

[DragOver](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.TreeGrid.TreeGridRowDragDropController~DragOver_EV.html) event occurs continuously while tree node is dragged within the target treegrid. The [TreeGridRowDragStartEventArgs](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.TreeGrid.TreeGridRowDragStartEventArgs.html) has the following member which provides information for `DragOver` event.

[Data](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.TreeGrid.TreeGridRowDragDropEventArgsBase~Data.html): Gets or sets a data object that contains the data associated while dragging the rows.

[DropPosition](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.TreeGrid.TreeGridRowDragDropEventArgsBase~DropPosition.html): Gets a value indicating the drop position which is based on dropped location.

[IsFromOutSideSource](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.TreeGrid.TreeGridRowDragDropEventArgsBase~IsFromOutSideSource.html): Gets a value indicating whether the dragging item is from same TreeGrid or not.

[ShowDragUI](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.TreeGrid.TreeGridRowDragOverEventArgs~ShowDragUI.html): Gets or sets a value indicating the default Dragging UI.  

[TargetNode](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.TreeGrid.TreeGridRowDragDropEventArgsBase~TargetNode.html): Gets a value indicating the target node which is going to drop.

{% tabs %}
{% highlight c# %}
sfTreeGrid.RowDragDropController.DragOver += RowDragDropController_DragOver;
private void RowDragDropController_DragOver(object sender, Syncfusion.UI.Xaml.TreeGrid.TreeGridRowDragOverEventArgs e)
{

}
{% endhighlight %}
{% endtabs %}

## DragLeave

[DragLeave](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.TreeGrid.TreeGridRowDragDropController~DragLeave_EV.html) event occurs when leave a drag-and-drop operation. The [TreeGridRowDragStartEventArgs](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.TreeGrid.TreeGridRowDragStartEventArgs.html) has the following member which provides information for `DragLeave` event.

[Data](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.TreeGrid.TreeGridRowDragDropEventArgsBase~Data.html): Gets or sets a data object that contains the data associated while dragging the rows.

[DropPosition](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.TreeGrid.TreeGridRowDragDropEventArgsBase~DropPosition.html): Gets a value indicating the drop position which is based on dropped location.

[IsFromOutSideSource](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.TreeGrid.TreeGridRowDragDropEventArgsBase~IsFromOutSideSource.html): Gets a value indicating whether the dragging item is from same TreeGrid or not.

[TargetNode](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.TreeGrid.TreeGridRowDragDropEventArgsBase~TargetNode.html): Gets a value indicating the target node which is going to drop.

{% tabs %}
{% highlight c# %}
this.sfTreeGrid.RowDragDropController.DragLeave += RowDragDropController_DragLeave;
private void RowDragDropController_DragLeave(object sender, Syncfusion.UI.Xaml.TreeGrid.TreeGridRowDragLeaveEventArgs e)
{

}
{% endhighlight %}
{% endtabs %}

## Drop

[Drop](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.TreeGrid.TreeGridRowDragDropController~Drop_EV.html) event occurs when a record is dropping within the target treegrid. The [TreeGridRowDragStartEventArgs](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.TreeGrid.TreeGridRowDragStartEventArgs.html) has the following member which provides information for `Drop` event.

[Data](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.TreeGrid.TreeGridRowDragDropEventArgsBase~Data.html): Gets or sets a data object that contains the data associated while dragging the rows.

[DraggingNodes](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.TreeGrid.TreeGridRowDropEventArgs~DraggingNodes.html): Gets the tree node which contains the data associated while dragging the rows.  

[DropPosition](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.TreeGrid.TreeGridRowDragDropEventArgsBase~DropPosition.html): Gets a value indicating the drop position which is based on dropped location.

[IsFromOutSideSource](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.TreeGrid.TreeGridRowDragDropEventArgsBase~IsFromOutSideSource.html): Gets a value indicating whether the dragging item is from same treegrid or not.

[TargetNode](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.TreeGrid.TreeGridRowDragDropEventArgsBase~TargetNode.html): Gets a value indicating the target node which is going to drop.

{% tabs %}
{% highlight c# %}
this.sfTreeGrid.RowDragDropController.Drop += RowDragDropController_Drop;
private void RowDragDropController_Drop(object sender, Syncfusion.UI.Xaml.TreeGrid.TreeGridRowDropEventArgs e)
{

}
{% endhighlight %}
{% endtabs %}

## Dropped

[Dropped](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.TreeGrid.TreeGridRowDragDropController~Dropped_EV.html) event occurs when a record is dropped within the target treegrid.  The [TreeGridRowDragStartEventArgs](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.TreeGrid.TreeGridRowDragStartEventArgs.html) has the following member which provides information for `Dropped` event.

[Data](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.TreeGrid.TreeGridRowDragDropEventArgsBase~Data.html): Gets or sets a data object that contains the data associated while dragging the rows.

[DropPosition](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.TreeGrid.TreeGridRowDragDropEventArgsBase~DropPosition.html): Gets a value indicating the drop position which is based on dropped location.

[IsFromOutSideSource](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.TreeGrid.TreeGridRowDragDropEventArgsBase~IsFromOutSideSource.html): Gets a value indicating whether the dragging item is from same treegrid or not.

[TargetNode](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.TreeGrid.TreeGridRowDragDropEventArgsBase~TargetNode.html): Gets a value indicating the target node which is going to drop.

{% tabs %}
{% highlight c# %}
this.sfTreeGrid.RowDragDropController.Dropped += RowDragDropController_Dropped;
private void RowDragDropController_Dropped(object sender, Syncfusion.UI.Xaml.TreeGrid.TreeGridRowDroppedEventArgs e)
{

}
{% endhighlight %}
{% endtabs %}

# Drag-and-Drop between SfTreeGrid and other controls

## Drag-and-Drop between ListView and SfTreeGrid

You can drag and drop the items between list view and treegrid. For this, you need to wire the [Drop](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.TreeGrid.TreeGridRowDragDropController~Drop_EV.html) event from [TreeGridRowDragDropController ](https://help.syncfusion.com/cr/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.TreeGrid.TreeGridRowDragDropController.html)class.

{% tabs %}
{% highlight c# %}
this.AssociatedObject.sfTreeGrid.RowDragDropController.Drop += RowDragDropController_Drop;

private void RowDragDropController_Drop(object sender, Syncfusion.UI.Xaml.TreeGrid.TreeGridRowDropEventArgs e)
{
    if (e.IsFromOutSideSource)
    {
        var item = e.Data.GetData("ListViewRecords") as ObservableCollection<object>;
        var record = item[0] as EmployeeInfo;
        var dropPosition = e.DropPosition.ToString();
        var newItem = new EmployeeInfo();

        var rowIndex = AssociatedObject.sfTreeGrid.ResolveToRowIndex(e.TargetNode.Item);
        int nodeIndex = (int)rowIndex;
        if (dropPosition != "None" && rowIndex != -1)
        {
            if (AssociatedObject.sfTreeGrid.View is TreeGridSelfRelationalView)
            {
                var treeNode = AssociatedObject.sfTreeGrid.GetNodeAtRowIndex(rowIndex);

                if (treeNode == null)
                    return;
                var data = treeNode.Item;
                AssociatedObject.sfTreeGrid.SelectionController.SuspendUpdates();
                var itemIndex = -1;

                TreeNode parentNode = null;

                if (dropPosition == "DropBelow" || dropPosition == "DropAbove")
                {
                    parentNode = treeNode.ParentNode;

                    if (parentNode == null)
                        newItem = new EmployeeInfo() { FirstName = record.FirstName, LastName = record.LastName, ID = record.ID, Salary = record.Salary, Title = record.Title, ReportsTo = -1 };
                    else
                    {
                        var parent = parentNode.Item as EmployeeInfo;
                        newItem = new EmployeeInfo() { FirstName = record.FirstName, LastName = record.LastName, ID = record.ID, Salary = record.Salary, Title = record.Title, ReportsTo = parent.ID };
                    }
                }

                else if (dropPosition == "DropAsChild")
                {

                    if (!treeNode.IsExpanded)
                        AssociatedObject.sfTreeGrid.ExpandNode(treeNode);
                    parentNode = treeNode;
                    var parent = parentNode.Item as EmployeeInfo;
                    newItem = new EmployeeInfo() { FirstName = record.FirstName, LastName = record.LastName, ID = record.ID, Salary = record.Salary, Title = record.Title, ReportsTo = parent.ID };

                }
                IList sourceCollection = null;

                if (dropPosition == "DropBelow" || dropPosition == "DropAbove")
                {

                    if (treeNode.ParentNode != null)
                    {

                        var collection = AssociatedObject.sfTreeGrid.View.GetPropertyAccessProvider().GetValue(treeNode.ParentNode.Item, AssociatedObject.sfTreeGrid.ChildPropertyName) as IEnumerable;

                        sourceCollection = GetSourceListCollection(collection);
                    }

                    else
                    {

                        sourceCollection = GetSourceListCollection(AssociatedObject.sfTreeGrid.View.SourceCollection);
                    }
                    itemIndex = sourceCollection.IndexOf(data);

                    if (dropPosition == "DropBelow")
                    {
                        itemIndex += 1;
                    }
                }

                else if (dropPosition == "DropAsChild")
                {
                    var collection = AssociatedObject.sfTreeGrid.View.GetPropertyAccessProvider().GetValue(data, AssociatedObject.sfTreeGrid.ChildPropertyName) as IEnumerable;

                    sourceCollection = GetSourceListCollection(collection);

                    if (sourceCollection == null)
                    {
                        var list = data.GetType().GetProperty(AssociatedObject.sfTreeGrid.ChildPropertyName).PropertyType.CreateNew() as IList;

                        if (list != null)
                        {
                            AssociatedObject.sfTreeGrid.View.GetPropertyAccessProvider().SetValue(treeNode.Item, AssociatedObject.sfTreeGrid.ChildPropertyName, list);
                            sourceCollection = list;
                        }
                    }
                    itemIndex = sourceCollection.Count;
                }
                sourceCollection.Insert(itemIndex, newItem);
                AssociatedObject.sfTreeGrid.SelectionController.ResumeUpdates();
                (AssociatedObject.sfTreeGrid.SelectionController as TreeGridRowSelectionController).RefreshSelection();
                e.Handled = true;
            }
        }
(AssociatedObject.listView.ItemsSource as ObservableCollection<EmployeeInfo>).Remove(record as EmployeeInfo);
    }
}
{% endhighlight %}
{% endtabs %}

In ListView, you need to wire the PreviewMouseMove and Drop events.

{% tabs %}
{% highlight c# %}
this.AssociatedObject.listView.PreviewMouseMove += ListView_PreviewMouseMove;
this.AssociatedObject.listView.Drop += ListView_Drop;

private void ListView_Drop(object sender, DragEventArgs e)
{
    ObservableCollection<TreeNode> treeNodes = new ObservableCollection<TreeNode>();

    if (e.Data.GetDataPresent("Nodes"))
        treeNodes= e.Data.GetData("Nodes") as ObservableCollection<TreeNode>;

    EmployeeInfo item = new EmployeeInfo();

    if (treeNodes.Count == 0 ||treeNodes==null)
        return;
           
    foreach (var node in treeNodes)
    {
        (AssociatedObject.sfTreeGrid.ItemsSource as ObservableCollection<EmployeeInfo>).Remove(node.Item as EmployeeInfo);
        if (node.HasChildNodes)
        {
            list.Add(node.Item as EmployeeInfo);
            GetChildNodes(node);
        }
        else
        {
            list.Add(node.Item as EmployeeInfo);
        }
    }
            
    foreach (var listItem in list)
    {
        (this.AssociatedObject.DataContext as ViewModel).Employee.Add(listItem);
    }
    list.Clear();
}

private void ListView_PreviewMouseMove(object sender, System.Windows.Input.MouseEventArgs e)
{
    if (e.LeftButton == MouseButtonState.Pressed)
    {
        ListBox dragSource = null;
        var records = new ObservableCollection<object>();
        ListBox parent = (ListBox)sender;
        dragSource = parent;
        object data = GetDataFromListBox(dragSource, e.GetPosition(parent));

        records.Add(data);

        var dataObject = new DataObject();
        dataObject.SetData("ListViewRecords", records);
        dataObject.SetData("ListView", this.AssociatedObject.listView);

        if (data != null)
        {
            DragDrop.DoDragDrop(parent, dataObject, DragDropEffects.Move);
        }
    }
    e.Handled = true;
}
{% endhighlight %}
{% endtabs %}

You can download the sample [here](https://github.com/SyncfusionExamples/how-to-drag-and-drop-rows-in-wpf-between-listview-and-treegrid).

![Drag and drop between treeGrid and listview](Row-Drag-and-Drop_images/Row-Drag-and-Drop_img4.jpeg)

## Drag-and-Drop between TreeViewAdv and SfTreeGrid

You can drag and drop the items between tree view and treegrid. For this, you need to wire the [Drop](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.TreeGrid.TreeGridRowDragDropController~Drop_EV.html) and [DragStart](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.TreeGrid.TreeGridRowDragDropController~DragStart_EV.html) event from [TreeGridRowDragDropController](https://help.syncfusion.com/cr/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.TreeGrid.TreeGridRowDragDropController.html) class.

{% tabs %}
{% highlight c# %}
private void RowDragDropController_DragStart(object sender, TreeGridRowDragStartEventArgs e)
{
    e.Handled = true;
    var dataObject = new DataObject();
    dataObject.SetData("SourceTreeGrid", this.AssociatedObject.sfTreeGrid);
    dataObject.SetData("Nodes", e.DraggingNodes);
            
    foreach (var node in e.DraggingNodes)
    {
        if (node.HasChildNodes)
        {
            records.Add(node.Item as EmployeeInfo);
            GetChildNodes(node);
        }
        else
        {
            records.Add(node.Item as EmployeeInfo);
        }
    }

    dataObject.SetData(records);

    if(records!=null)
    DragDrop.DoDragDrop(this.AssociatedObject.sfTreeGrid, dataObject, DragDropEffects.Copy | DragDropEffects.Move);
    records.Clear();
}

private void RowDragDropController_Drop(object sender, TreeGridRowDropEventArgs e)
{
    if (e.IsFromOutSideSource)
    {
        ObservableCollection<object> item = e.Data.GetData(typeof(ObservableCollection<object>)) as ObservableCollection<object>;
        var record = item[0] as EmployeeInfo;
        var dropPosition = e.DropPosition.ToString();
        var newItem = new EmployeeInfo();

        var rowIndex = AssociatedObject.sfTreeGrid.ResolveToRowIndex(e.TargetNode.Item);
        int nodeIndex = (int)rowIndex;
        if (dropPosition != "None" && rowIndex != -1)
        {
            if (AssociatedObject.sfTreeGrid.View is TreeGridSelfRelationalView)
            {
                var treeNode = AssociatedObject.sfTreeGrid.GetNodeAtRowIndex(rowIndex);

                if (treeNode == null)
                    return;
                var data = treeNode.Item;
                AssociatedObject.sfTreeGrid.SelectionController.SuspendUpdates();
                var itemIndex = -1;

                TreeNode parentNode = null;

                if (dropPosition == "DropBelow" || dropPosition == "DropAbove")
                {
                    parentNode = treeNode.ParentNode;

                    if (parentNode == null)
                        newItem = new EmployeeInfo() { FirstName = record.FirstName, LastName = record.LastName, ID = record.ID, Salary = record.Salary, Title = record.Title, ReportsTo = -1 };
                    else
                    {
                        var parent = parentNode.Item as EmployeeInfo;
                        newItem = new EmployeeInfo() { FirstName = record.FirstName, LastName = record.LastName, ID = record.ID, Salary = record.Salary, Title = record.Title, ReportsTo = parent.ID };
                    }
                }

                else if (dropPosition == "DropAsChild")
                {

                    if (!treeNode.IsExpanded)
                        AssociatedObject.sfTreeGrid.ExpandNode(treeNode);
                    parentNode = treeNode;
                    var parent = parentNode.Item as EmployeeInfo;
                    newItem = new EmployeeInfo() { FirstName = record.FirstName, LastName = record.LastName, ID = record.ID, Salary = record.Salary, Title = record.Title, ReportsTo = parent.ID };

                }
                IList sourceCollection = null;

                if (dropPosition == "DropBelow" || dropPosition == "DropAbove")
                {

                    if (treeNode.ParentNode != null)
                    {

                        var collection = AssociatedObject.sfTreeGrid.View.GetPropertyAccessProvider().GetValue(treeNode.ParentNode.Item, AssociatedObject.sfTreeGrid.ChildPropertyName) as IEnumerable;

                        sourceCollection = GetSourceListCollection(collection);
                    }

                    else
                    {
                        sourceCollection = GetSourceListCollection(AssociatedObject.sfTreeGrid.View.SourceCollection);
                    }
                    itemIndex = sourceCollection.IndexOf(data);

                    if (dropPosition == "DropBelow")
                    {
                        itemIndex += 1;
                    }
                }

                else if (dropPosition == "DropAsChild")
                {
                    var collection = AssociatedObject.sfTreeGrid.View.GetPropertyAccessProvider().GetValue(data, AssociatedObject.sfTreeGrid.ChildPropertyName) as IEnumerable;

                    sourceCollection = GetSourceListCollection(collection);

                    if (sourceCollection == null)
                    {
                        var list = data.GetType().GetProperty(AssociatedObject.sfTreeGrid.ChildPropertyName).PropertyType.CreateNew() as IList;

                        if (list != null)
                        {
                            AssociatedObject.sfTreeGrid.View.GetPropertyAccessProvider().SetValue(treeNode.Item, AssociatedObject.sfTreeGrid.ChildPropertyName, list);
                            sourceCollection = list;
                        }
                    }
                    itemIndex = sourceCollection.Count;
                }
                sourceCollection.Insert(itemIndex, newItem);
                AssociatedObject.sfTreeGrid.SelectionController.ResumeUpdates();
                (AssociatedObject.sfTreeGrid.SelectionController as TreeGridRowSelectionController).RefreshSelection();
                e.Handled = true;
            }
        }
        (AssociatedObject.treeview.ItemsSource as ObservableCollection<EmployeeInfo>).Remove(record as EmployeeInfo);
    }
}
{% endhighlight %}
{% endtabs %}
In TreeViewAdv, you need to wire the Drop event,
{% tabs %}
{% highlight c# %}
private void Treeview_Drop(object sender, DragEventArgs e)
{
    ObservableCollection<TreeNode> treeNodes = new ObservableCollection<TreeNode>();

    if (e.Data.GetDataPresent("Nodes"))
        treeNodes = e.Data.GetData("Nodes") as ObservableCollection<TreeNode>;

    EmployeeInfo item = new EmployeeInfo();

    if (treeNodes.Count == 0 || treeNodes == null)
        return;

    foreach (var node in treeNodes)
    {
        (AssociatedObject.sfTreeGrid.ItemsSource as ObservableCollection<EmployeeInfo>).Remove(node.Item as EmployeeInfo);
    }
}
{% endhighlight %}
{% endtabs %}

You can download the sample [here](https://github.com/SyncfusionExamples/how-to-drag-and-drop-rows-in-wpf-between-treegrid-and-treeviewadv).

![Drag and drop between treegrid and treeviewadv](Row-Drag-and-Drop_images/Row-Drag-and-Drop_img5.jpeg)

# Customizing row drag-and-drop

SfTreeGrid processes row drag and drop operations in [TreeGridRowDragDropController](https://help.syncfusion.com/cr/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.TreeGrid.TreeGridRowDragDropController.html) class. You can customize the row drag and drop operations by using events in the[SfTreeGrid.RowDragDropController](https://help.syncfusion.com/cr/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.TreeGrid.TreeGridRowDragDropController.html).

## Auto expand the node on drag over

When drag over the tree node, if drop position is “Drop as child”, then you can auto expand the corresponding tree node by setting [TreeGridRowDragDropController.CanAutoExpand](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.TreeGrid.TreeGridRowDragDropController~CanAutoExpand.html) to `true`. It is also possible to control the delay in expanding the node when drag over using [TreeGridRowDragDropController.AutoExpandDelay](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.TreeGrid.TreeGridRowDragDropController~AutoExpandDelay.html) property. Its default value in 3 sec.

{% tabs %}
{% highlight c# %}
treeGrid.RowDragDropController.CanAutoExpand = true;
treeGrid.RowDragDropController.AutoExpandDelay = new TimeSpan(0, 0, 2);
{% endhighlight %}
{% endtabs %}

## Customize default drag UI

SfTreeGrid provides default UI for drag and drop. However, you can customize the drag UI using [RowDragDropTemplate](https://help.syncfusion.com/cr/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid~RowDragDropTemplate.html) property.

{% tabs %}
{% highlight xml %}
<DataTemplate x:Key="dragdroptemplate">
            <Border x:Name="border" Width="250"  
                            Background="#ececec" 
                            BorderBrush="#c8c8c8"  Height="60"
                            BorderThickness="1.2">

                <Grid  VerticalAlignment="Center" 
                          HorizontalAlignment="Left">
                    <Grid.RowDefinitions>
                        <RowDefinition Height="Auto"/>
                        <RowDefinition Height="Auto"/>
                        <RowDefinition Height="Auto"/>
                    </Grid.RowDefinitions>
                    <Grid.ColumnDefinitions>
                        <ColumnDefinition Width="Auto"/>
                        <ColumnDefinition Width="Auto"/>
                    </Grid.ColumnDefinitions>

                    <TextBlock Padding="12,0,0,0" Text="Dragging rows count :" FontSize="14" FontFamily="Segoe UI" 
                                       Foreground="#333333" FontWeight="Regular" Background="SkyBlue" />

                    <TextBlock Text="{Binding DraggingRecords.Count}" FontSize="14" 
                                       FontFamily="Segoe UI"
                                       FontWeight="Regular" 
                                       Foreground="#333333" 
                                       Grid.Column="1" Margin="-100,0,0,0"/>

                    <Separator  Grid.Row="1" Height="2" BorderBrush="#c8c8c8"
                                        HorizontalAlignment="Stretch"  BorderThickness="1"
                                        VerticalAlignment="Stretch"  Width="250"/>

                    <TextBlock Text="Drop status:" 
                                       Foreground="#333333"
                                       Padding="12,0,0,0" Background="SkyBlue"
                                       FontFamily="Segoe UI" 
                                       FontWeight="Regular" 
                                       FontSize="14"
                                       Grid.Row="2"/>

                    <TextBlock Text="{Binding DragStatus}" 
                                       FontSize="14"
                                       FontFamily="Segoe UI"
                                       FontWeight="Regular"
                                       Foreground="#333333" 
                                       Margin="-163,0,0,0"
                                       Grid.Row="2" 
                                       Grid.Column="1"/>
                </Grid>
            </Border>
 </DataTemplate>

   <syncfusion:SfTreeGrid Name="sfTreeGrid" AutoExpandMode="RootNodesExpanded" SelectionMode="Extended" AllowDraggingRows="True" AllowDrop="True" 
                               ChildPropertyName="ReportsTo" 
                               ItemsSource="{Binding Employees}"
                               ParentPropertyName="ID"
                               RowDragDropTemplate="{StaticResource DragDropTemplate}"
                               SelfRelationRootValue="-1" >
{% endhighlight %}
{% endtabs %}

![Customized drag and drop window](Row-Drag-and-Drop_images/Row-Drag-and-Drop_img6.jpeg)

## Disable dragging of certain nodes

You can restrict the dragging of specific node by using the DragStart event of the [TreeGridRowDragDropController](https://help.syncfusion.com/cr/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.TreeGrid.TreeGridRowDragDropController.html) class.

{% tabs %}
{% highlight c# %}
private void RowDragDropController_DragStart(object sender, Syncfusion.UI.Xaml.TreeGrid.TreeGridRowDragStartEventArgs e)
{
    var nodes = e.DraggingNodes;
    var node = nodes.FirstOrDefault(n => n.Level == 0);

    if (node != null)
        e.Handled = true;
}
{% endhighlight %}
{% endtabs %}

## Disable drop of certain nodes

You can restrict the drop of specific node by using the Drop event of the [TreeGridRowDragDropController](https://help.syncfusion.com/cr/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.TreeGrid.TreeGridRowDragDropController.html) class.

{% tabs %}
{% highlight c# %}
private void RowDragDropController_Drop(object sender, Syncfusion.UI.Xaml.TreeGrid.TreeGridRowDropEventArgs e)
{
    // Disable drop on leaf nodes.
    if (!e.TargetNode.HasChildNodes)
        e.Handled = true;
}
{% endhighlight %}
{% endtabs %}

## Disable Default Drag UI

You can disable the draggable popup by setting the  [ShowDragUI](https://help.syncfusion.com/cr/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.GridRowDragOverEventArgs~ShowDragUI.html) as false in the Drop event of [TreeGridRowDragDropController](https://help.syncfusion.com/cr/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.TreeGrid.TreeGridRowDragDropController.html) class.

{% tabs %}
{% highlight c# %}
private void RowDragDropController_DragOver(object sender, TreeGridRowDragOverEventArgs e)
{
    e.ShowDragUI = false;
}
{% endhighlight %}
{% endtabs %}
