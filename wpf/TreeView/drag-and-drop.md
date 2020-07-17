---
layout: post
title: Drag and drop with WPF TreeView control | Syncfusion
description: Learn here about drag and drop between the TreeViewNodes with Syncfusion WPF TreeView (SfTreeView) control and  drag and drop related events. 
platform: wpf
control: SfTreeView
documentation: ug
---

# Drag and drop in WPF TreeView (SfTreeView)

TreeView allows drag and drop the items within the treeview control by setting the [AllowDragging](https://help.syncfusion.com/cr/wpf/Syncfusion.SfTreeView.WPF~Syncfusion.UI.Xaml.TreeView.SfTreeView~AllowDragging.html) property as `true`. It is also possible to drag and drop the items between treeview and other controls such as `ListView` and `SfDataGrid`. 

{% tabs %}
{% highlight xaml %}
<treeview:SfTreeView
    Name="sfTreeView"
    AllowDragging="True"
    ChildPropertyName="Childs"
    ItemsSource="{Binding Nodes1}" />
{% endhighlight %}
{% highlight c# %}
sfTreeView.AllowDragging = true;
{% endhighlight %}
{% endtabs %}

While dropping, the dragged items can be added above or below to the target item based on drag indicator position.

![Drag and drop items in wpf treeview](DragDrop_images/DragDrop_image1)

## Dragging multiple items

SfTreeView allows to drag multiple selected items. To enable multiple selection, set the [SfTreeView.SelectionMode](https://help.syncfusion.com/cr/wpf/Syncfusion.SfTreeView.WPF~Syncfusion.UI.Xaml.TreeView.SfTreeView~SelectionMode.html) as `Multiple` or `Extended`. 

![Drag and drop items in wpf treeview](DragDrop_images/DragDrop_image2)
## Drag and drop events

SfTreeView triggers the following events when drag and drop:

### ItemDragStarting event

[ItemDragStarting](https://help.syncfusion.com/cr/wpf/Syncfusion.SfTreeView.WPF~Syncfusion.UI.Xaml.TreeView.SfTreeView~ItemDragStarting_EV.html) event occurs when you starting to drag the items in treeview. The [TreeViewItemDragStartingEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.SfTreeView.WPF~Syncfusion.UI.Xaml.TreeView.TreeViewItemDragStartingEventArgs.html)  has the following member, which provides information for the `ItemDragStarting` event.

* [Data](https://help.syncfusion.com/cr/wpf/Syncfusion.SfTreeView.WPF~Syncfusion.UI.Xaml.TreeView.TreeViewItemDragStartingEventArgs~Data.html) : Gets or Sets a data object that contains the data associated while dragging the items. 
* [DraggingNodes](https://help.syncfusion.com/cr/wpf/Syncfusion.SfTreeView.WPF~Syncfusion.UI.Xaml.TreeView.TreeViewItemDragStartingEventArgs~DraggingNodes.html) : Gets the collection of [TreeViewNode](https://help.syncfusion.com/cr/wpf/Syncfusion.SfTreeView.WPF~Syncfusion.UI.Xaml.TreeView.Engine.TreeViewNode.html) which are dragged.If you set the Data property, the value of DraggingNodes property will be `null`.
* [Cancel](https://help.syncfusion.com/cr/wpf/Syncfusion.SfTreeView.WPF~Syncfusion.UI.Xaml.TreeView.TreeViewItemDragStartingEventArgs~Cancel.html) : Gets or sets a value indicating whether dragging should be canceled.

{% tabs %}
{% highlight c# %}
sfTreeView.ItemDragStarting += SfTreeView_ItemDragStarting;

private void SfTreeView_ItemDragStarting(object sender, Syncfusion.UI.Xaml.TreeView.TreeViewItemDragStartingEventArgs e)
{
    
}

{% endhighlight %}
{% endtabs %}

### ItemDragStarted event

[ItemDragStarted](https://help.syncfusion.com/cr/wpf/Syncfusion.SfTreeView.WPF~Syncfusion.UI.Xaml.TreeView.SfTreeView~ItemDragStarted_EV.html)  event occurs after started the dragging, in treeview. The [TreeViewItemDragStartedEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.SfTreeView.WPF~Syncfusion.UI.Xaml.TreeView.TreeViewItemDragStartedEventArgs.html)  has the following member, which provides information for the `ItemDragStarted` event.

* [Data](https://help.syncfusion.com/cr/wpf/Syncfusion.SfTreeView.WPF~Syncfusion.UI.Xaml.TreeView.TreeViewItemDragStartedEventArgs~Data.html) : Gets a data object that contains the data associated while dragging the items. 
* [DraggingNodes](https://help.syncfusion.com/cr/wpf/Syncfusion.SfTreeView.WPF~Syncfusion.UI.Xaml.TreeView.TreeViewItemDragStartedEventArgs~DraggingNodes.html) : Gets the collection of [TreeViewNode](https://help.syncfusion.com/cr/wpf/Syncfusion.SfTreeView.WPF~Syncfusion.UI.Xaml.TreeView.Engine.TreeViewNode.html) which are dragged.

{% tabs %}
{% highlight c# %}
sfTreeView.ItemDragStarted += SfTreeView_ItemDragStarted;

private void SfTreeView_ItemDragStarted(object sender, Syncfusion.UI.Xaml.TreeView.TreeViewItemDragStartedEventArgs e)
{
   
}
{% endhighlight %}
{% endtabs %}

### ItemDragOver event

[ItemDragOver](https://help.syncfusion.com/cr/wpf/Syncfusion.SfTreeView.WPF~Syncfusion.UI.Xaml.TreeView.SfTreeView~ItemDragOver_EV.html) event occurs continuously while item is dragged within the targeted SfTreeView. The [TreeViewItemDragOverEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.SfTreeView.WPF~Syncfusion.UI.Xaml.TreeView.TreeViewItemDragOverEventArgs.html) has the following members, which provide information for the `ItemDragOver` event.

* [Data](https://help.syncfusion.com/cr/wpf/Syncfusion.SfTreeView.WPF~Syncfusion.UI.Xaml.TreeView.TreeViewItemDragOverEventArgs~Data.html) : Gets a data object that contains the data associated while dragging the items. 
* [DraggingNodes](https://help.syncfusion.com/cr/wpf/Syncfusion.SfTreeView.WPF~Syncfusion.UI.Xaml.TreeView.TreeViewItemDragOverEventArgs~DraggingNodes.html) : Gets the collection of [TreeViewNode](https://help.syncfusion.com/cr/wpf/Syncfusion.SfTreeView.WPF~Syncfusion.UI.Xaml.TreeView.Engine.TreeViewNode.html) which are dragged.
* [DragSource](https://help.syncfusion.com/cr/wpf/Syncfusion.SfTreeView.WPF~Syncfusion.UI.Xaml.TreeView.TreeViewItemDragOverEventArgs~DragSource.html) : Gets the source of the transferred data.
* [DropPosition](https://help.syncfusion.com/cr/wpf/Syncfusion.SfTreeView.WPF~Syncfusion.UI.Xaml.TreeView.TreeViewItemDragOverEventArgs~DropPosition.html) : Gets or sets the position where dragged nodes are going to be dropped.
* [TargetNode](https://help.syncfusion.com/cr/wpf/Syncfusion.SfTreeView.WPF~Syncfusion.UI.Xaml.TreeView.TreeViewItemDragOverEventArgs~TargetNode.html) : Gets the node where the dragged nodes are going to be dropped.

{% tabs %}
{% highlight c# %}
sfTreeView.ItemDragOver += SfTreeView_ItemDragOver;
private void SfTreeView_ItemDragOver(object sender, Syncfusion.UI.Xaml.TreeView.TreeViewItemDragOverEventArgs e)
{
  
}
{% endhighlight %}
{% endtabs %}


### ItemDropping event

[ItemDropping](https://help.syncfusion.com/cr/wpf/Syncfusion.SfTreeView.WPF~Syncfusion.UI.Xaml.TreeView.SfTreeView~ItemDropping_EV.html) event occurs when item is dropping within the targeted SfTreeView. The [TreeViewItemDroppingEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.SfTreeView.WPF~Syncfusion.UI.Xaml.TreeView.TreeViewItemDroppingEventArgs.html) has the following members, which provide information for the `ItemDropping` event.

* [Data](https://help.syncfusion.com/cr/wpf/Syncfusion.SfTreeView.WPF~Syncfusion.UI.Xaml.TreeView.TreeViewItemDroppingEventArgs~Data.html) : Gets a data object that contains the data associated while dragging the items. 
* [DraggingNodes](https://help.syncfusion.com/cr/wpf/Syncfusion.SfTreeView.WPF~Syncfusion.UI.Xaml.TreeView.TreeViewItemDroppingEventArgs~DraggingNodes.html) : Gets the collection of [TreeViewNode](https://help.syncfusion.com/cr/wpf/Syncfusion.SfTreeView.WPF~Syncfusion.UI.Xaml.TreeView.Engine.TreeViewNode.html) which are dragged.
* [DragSource](https://help.syncfusion.com/cr/wpf/Syncfusion.SfTreeView.WPF~Syncfusion.UI.Xaml.TreeView.TreeViewItemDroppingEventArgs~DragSource.html) : Gets the source of the transferred data.
* [DropPosition](https://help.syncfusion.com/cr/wpf/Syncfusion.SfTreeView.WPF~Syncfusion.UI.Xaml.TreeView.TreeViewItemDroppingEventArgs~DropPosition.html) : Gets or sets the position where dragged nodes are going to be dropped.
* [Handled](https://help.syncfusion.com/cr/wpf/Syncfusion.SfTreeView.WPF~Syncfusion.UI.Xaml.TreeView.TreeViewItemDroppingEventArgs~Handled.html) : Gets or sets a value indicating whether the event is handled. If this event is handled, dragged nodes will not be dropped to TreeView.
* [TargetNode](https://help.syncfusion.com/cr/wpf/Syncfusion.SfTreeView.WPF~Syncfusion.UI.Xaml.TreeView.TreeViewItemDroppingEventArgs~TargetNode.html) : Gets the node where the dragged nodes are going to be dropped.

{% tabs %}
{% highlight c# %}
sfTreeView.ItemDropping += SfTreeView_ItemDropping;

private void SfTreeView_ItemDropping(object sender, Syncfusion.UI.Xaml.TreeView.TreeViewItemDroppingEventArgs e)
{
    
}
{% endhighlight %}
{% endtabs %}

### ItemDropped event

[ItemDropped](https://help.syncfusion.com/cr/wpf/Syncfusion.SfTreeView.WPF~Syncfusion.UI.Xaml.TreeView.SfTreeView~ItemDropped_EV.html) event occurs when item is dropped within the targeted SfTreeView. The [TreeViewItemDroppedEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.SfTreeView.WPF~Syncfusion.UI.Xaml.TreeView.TreeViewItemDroppedEventArgs.html) has the following members, which provide information for the `Drop` event.
* [Data](https://help.syncfusion.com/cr/wpf/Syncfusion.SfTreeView.WPF~Syncfusion.UI.Xaml.TreeView.TreeViewItemDroppedEventArgs~Data.html) : Gets a data object that contains the data associated while dragging the items. 
* [DraggingNodes](https://help.syncfusion.com/cr/wpf/Syncfusion.SfTreeView.WPF~Syncfusion.UI.Xaml.TreeView.TreeViewItemDroppedEventArgs~DraggingNodes.html) : Gets the collection of [TreeViewNode](https://help.syncfusion.com/cr/wpf/Syncfusion.SfTreeView.WPF~Syncfusion.UI.Xaml.TreeView.Engine.TreeViewNode.html) which are dragged.
* [DragSource](https://help.syncfusion.com/cr/wpf/Syncfusion.SfTreeView.WPF~Syncfusion.UI.Xaml.TreeView.TreeViewItemDroppedEventArgs~DragSource.html) : Gets the source of the transferred data.
* [DropPosition](https://help.syncfusion.com/cr/wpf/Syncfusion.SfTreeView.WPF~Syncfusion.UI.Xaml.TreeView.TreeViewItemDroppedEventArgs~DropPosition.html) : Gets the position where dragged nodes are dropped.
* [TargetNode](https://help.syncfusion.com/cr/wpf/Syncfusion.SfTreeView.WPF~Syncfusion.UI.Xaml.TreeView.TreeViewItemDroppedEventArgs~TargetNode.html) : Gets the node where the dragged nodes are dropped.

{% tabs %}
{% highlight c# %}
sfTreeView.ItemDropped += SfTreeView_ItemDropped;

private void SfTreeView_ItemDropped(object sender, Syncfusion.UI.Xaml.TreeView.TreeViewItemDroppedEventArgs e)
{
   
}

{% endhighlight %}
{% endtabs %}

## Customizing the drag and drop operation

### Disable dragging of certain items in WPF TreeView

You can restrict the dragging of certain nodes in SfTreeView by using the  [SfTreeView.ItemDragStarting](https://help.syncfusion.com/cr/wpf/Syncfusion.SfTreeView.WPF~Syncfusion.UI.Xaml.TreeView.SfTreeView~ItemDragStarting_EV.html) event.

{% tabs %}
{% highlight c# %}
sfTreeView.ItemDragStarting += SfTreeView_ItemDragStarting;

private void SfTreeView_ItemDragStarting(object sender, Syncfusion.UI.Xaml.TreeView.TreeViewItemDragStartingEventArgs e)
{
    var record = e.DraggingNodes[0].Content as Model;
    if (record.Header == "Feature Schedule")
        e.Cancel = true;
}

{% endhighlight %}
{% endtabs %}

### Disable dropping on certain items in WPF TreeView

You can restrict the dropping the items on certain nodes in SfTreeView by using the [SfTreeView.ItemDropping](https://help.syncfusion.com/cr/wpf/Syncfusion.SfTreeView.WPF~Syncfusion.UI.Xaml.TreeView.SfTreeView~ItemDropping_EV.html) event.

{% tabs %}
{% highlight c# %}
 sfTreeView.ItemDropping += SfTreeView_ItemDropping;

private void SfTreeView_ItemDropping(object sender, Syncfusion.UI.Xaml.TreeView.TreeViewItemDroppingEventArgs e)
{
    var record = e.TargetNode.Content as Model;
    if (record.Header == "Home Remodel Folder")
        e.Handled = true;
}
{% endhighlight %}
{% endtabs %}

### Customize the drop position

You can customize the drop position of dragging nodes in SfTreeView by using the [SfTreeView.ItemDropping](https://help.syncfusion.com/cr/wpf/Syncfusion.SfTreeView.WPF~Syncfusion.UI.Xaml.TreeView.SfTreeView~ItemDropping_EV.html) event.

{% tabs %}
{% highlight c# %}
sfTreeView.ItemDropping += SfTreeView_ItemDropping;

private void SfTreeView_ItemDropping(object sender, Syncfusion.UI.Xaml.TreeView.TreeViewItemDroppingEventArgs e)
{
    var record = e.TargetNode.Content as Model;
    if (record.Header == "Home Remodel Folder")
        e.DropPosition = Syncfusion.UI.Xaml.TreeView.DropPosition.DropAsChild;
}

{% endhighlight %}
{% endtabs %}

### Customizing drag Popup

To customize the draggable popup, use the [DragPreviewTemplate](https://help.syncfusion.com/cr/wpf/Syncfusion.SfTreeView.WPF~Syncfusion.UI.Xaml.TreeView.SfTreeView~DragPreviewTemplate.html) property in the SfTreeView. The DataContext of DragPreviewTemplate is [TreeViewDragInfo](https://help.syncfusion.com/cr/wpf/Syncfusion.SfTreeView.WPF~Syncfusion.UI.Xaml.TreeView.TreeViewDragInfo.html).

{% tabs %}
{% highlight xaml %}
<syncfusion:ChromelessWindow.Resources>
    <DataTemplate x:Key="dragPreviewTemplate">
        <Border BorderBrush="Gray" BorderThickness="1">
            <Grid Background="SkyBlue">
                <Grid.RowDefinitions>
                    <RowDefinition />
                    <RowDefinition/>
                </Grid.RowDefinitions>
                <TextBlock Grid.Row="0" Margin="5,2,5,0"
                VerticalAlignment="Center" Text="DropPosition:"/>
                <TextBlock Grid.Row="1"
                Margin="5,0,5,2"
                VerticalAlignment="Center"
                Text="{Binding DragCaption}" FontWeight="Bold"/>
            </Grid>
        </Border>            
    </DataTemplate>    
</syncfusion:ChromelessWindow.Resources>

<treeview:SfTreeView
    Name="sfTreeView"
    AllowDragging="True"
    ChildPropertyName="Childs"
    DragPreviewTemplate="{StaticResource dragPreviewTemplate}"
    ItemsSource="{Binding Nodes1}" />

{% endhighlight %}
{% endtabs %}

![Drag and drop items in wpf treeview](DragDrop_images/DragDrop_image3)

## Drag and drop between two TreeView's

You can customize the dragging operation between two treeview by using the [SfTreeView.ItemDragStarting](https://help.syncfusion.com/cr/wpf/Syncfusion.SfTreeView.WPF~Syncfusion.UI.Xaml.TreeView.SfTreeView~ItemDragStarting_EV.html) , [SfTreeView.ItemDropping](https://help.syncfusion.com/cr/wpf/Syncfusion.SfTreeView.WPF~Syncfusion.UI.Xaml.TreeView.SfTreeView~ItemDropping_EV.html) and [SfTreeView.ItemDropped](https://help.syncfusion.com/cr/wpf/Syncfusion.SfTreeView.WPF~Syncfusion.UI.Xaml.TreeView.SfTreeView~ItemDropped_EV.html) events.

{% tabs %}
{% highlight c# %}

AssociatedObject.sfTreeView1.ItemDragStarting += SfTreeView1_ItemDragStarting;    
AssociatedObject.sfTreeView1.ItemDropping += SfTreeView1_ItemDropping;
AssociatedObject.sfTreeView2.ItemDropping += SfTreeView2_ItemDropping;
AssociatedObject.sfTreeView2.ItemDropped += SfTreeView1_ItemDropped;
    
 /// <summary>
 /// Customizing the ItemStarting event
 /// </summary>
 /// <param name="sender"></param>
 /// <param name="e"></param>
 private void SfTreeView1_ItemDragStarting(object sender, Syncfusion.UI.Xaml.TreeView.TreeViewItemDragStartingEventArgs e)
 {
     //Restrict the dragging for certain node
     var record = e.DraggingNodes[0].Content as Model;
     if (record.Header == "Feature Schedule")
         e.Cancel = true;
 }

 /// <summary>
 /// Customizing the ItemDropping event
 /// </summary>
 /// <param name="sender"></param>
 /// <param name="e"></param>
 private void SfTreeView1_ItemDropping(object sender, Syncfusion.UI.Xaml.TreeView.TreeViewItemDroppingEventArgs e)
 {
     //Restrict the dropping in first treeview
     e.Handled = true;
 }

 /// <summary>
 /// Customizing the ItemDropping event
 /// </summary>
 /// <param name="sender"></param>
 /// <param name="e"></param>
 private void SfTreeView2_ItemDropping(object sender, Syncfusion.UI.Xaml.TreeView.TreeViewItemDroppingEventArgs e)
 {
     //Restrict the dropping for drop position as above
     if (e.DropPosition == Syncfusion.UI.Xaml.TreeView.DropPosition.DropAbove)
         e.Handled = true;

     //Restrict the dropping on certain nodes
     var record = e.TargetNode.Content as Model;
     if (record.Header == "My Folders")
         e.Handled = true;
 }

 /// <summary>
 /// Customize the ItemDropped event
 /// </summary>
 /// <param name="sender"></param>
 /// <param name="e"></param>
 private void SfTreeView1_ItemDropped(object sender, Syncfusion.UI.Xaml.TreeView.TreeViewItemDroppedEventArgs e)
 {
     var parentNode = e.TargetNode.ParentNode;
     var collection = parentNode.ChildNodes;
     var record = e.DraggingNodes[0].Content as Model;
     int count = 0;
     foreach (var child in parentNode.ChildNodes)
     {
         var childNode = child.Content as Model;
         if (childNode.Header == record.Header)
         {
             count++;
             if (count > 1)
             {
                // Remove dropped node if the parent has the same node in it
                 collection.Remove(child);
                 return;
             }

         }
     }
 }

{% endhighlight %}
{% endtabs %}

![Drag and drop items in wpf treeview](DragDrop_images/DragDrop_image4)

N> View sample in [GitHub](https://github.com/syncfusion/wpf-demos/tree/master/TreeView/DragAndDrop)