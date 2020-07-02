---
layout: post
title: WPF TreeView Items Dragging | Syncfusion
description: This section describes about how to perform drag and drop operations in Syncfusion WPF TreeView(TreeViewAdv).
platform: wpf
control: TreeViewAdv
documentation: ug
---
# Dragging TreeView Items

TreeViewAdv control enables to drag TreeView items from one location to another. This is done by enabling the AllowDragDrop property.

Use the following code to enable this property

{% tabs %}

{% highlight XAML %}

<syncfusion:TreeViewAdv Name="treeViewAdv" AllowDragDrop="True" >
<syncfusion:TreeViewItemAdv Name="treeviewitem" Header="Marital Status" >
<syncfusion:TreeViewItemAdv Header="Single"/>
<syncfusion:TreeViewItemAdv Header="Married"/>
<syncfusion:TreeViewItemAdv Header="Married with Children"/>
</syncfusion:TreeViewItemAdv>
<syncfusion:TreeViewItemAdv Header="Baby Vaccines" Name="item2"  >
<syncfusion:TreeViewItemAdv Header="Hepatitis B"/>
<syncfusion:TreeViewItemAdv Header="Tetanus"/>
<syncfusion:TreeViewItemAdv Header="Polio"/>
<syncfusion:TreeViewItemAdv Header="Measles"/>
</syncfusion:TreeViewItemAdv>
<syncfusion:TreeViewItemAdv Header="Country Information" />
</syncfusion:TreeViewAdv>

{% endhighlight %}

{% highlight C# %}

//set allow drag and drop
treeViewAdv.AllowDragDrop = true;

{% endhighlight %}

{% highlight VB %}

'set allow drag and drop
treeViewAdv.AllowDragDrop = True

{% endhighlight %}

{% endtabs %}  

![Dragged the WPF TreeView item from one location to another](Dragging_treeview_items_images/Dragging_treeview_items_img1.jpeg)


## Transparent dragging image

The TreeViewAdv control provides support to change the opacity of an element being dragged. By using the DraggingContainerOpacity property,we can change the opacity value of the dragged element. It is useful to be able to view the content behind the dragged element.

{% tabs %}

{% highlight XAML %}

<syncfusion:TreeViewAdv Name="treeViewAdv" AllowDragDrop="True" DraggingContainerOpacity="0.4" >
<syncfusion:TreeViewItemAdv Name="treeviewitem" Header="Marital Status" >
<syncfusion:TreeViewItemAdv Header="Single"/>
<syncfusion:TreeViewItemAdv Header="Married"/>
<syncfusion:TreeViewItemAdv Header="Married with Children"/>
</syncfusion:TreeViewItemAdv>
<syncfusion:TreeViewItemAdv Header="Baby Vaccines" Name="item2"  >
<syncfusion:TreeViewItemAdv Header="Hepatitis B"/>
<syncfusion:TreeViewItemAdv Header="Tetanus"/>
<syncfusion:TreeViewItemAdv Header="Polio"/>
<syncfusion:TreeViewItemAdv Header="Measles"/>
</syncfusion:TreeViewItemAdv>
<syncfusion:TreeViewItemAdv Header="Country Information" />
</syncfusion:TreeViewAdv>

{% endhighlight %}

{% highlight C# %}

//set DraggingContainerOpacity
treeViewAdv.DraggingContainerOpacity = 0.4;

{% endhighlight %}

{% highlight VB %}

'set DraggingContainerOpacity
treeViewAdv.DraggingContainerOpacity = 0.4

{% endhighlight %}

{% endtabs %}  

![Dragging the WPF TreeView item with transparent image](Dragging_treeview_items_images/Dragging_treeview_items_img2.jpeg)

## Fake drag indicator

Fake Drag Indicator to indicate where TreeViewItemAdv may be placed during drag and drop operations. This is achieved by enabling the “IsFakeDragIndicator” property.

The following code example can be used to set this property

{% tabs %}

{% highlight XAML %}

<syncfusion:TreeViewAdv Name="treeViewAdv" IsFakeDragIndicator="True">
<syncfusion:TreeViewItemAdv Name="treeviewitem" Header="Marital Status" >
<syncfusion:TreeViewItemAdv Header="Single"/>
<syncfusion:TreeViewItemAdv Header="Married"/>
<syncfusion:TreeViewItemAdv Header="Married with Children"/>
</syncfusion:TreeViewItemAdv>
<syncfusion:TreeViewItemAdv Header="Baby Vaccines" Name="item2"  >
<syncfusion:TreeViewItemAdv Header="Hepatitis B"/>
<syncfusion:TreeViewItemAdv Header="Tetanus"/>
<syncfusion:TreeViewItemAdv Header="Polio"/>
<syncfusion:TreeViewItemAdv Header="Measles"/>
</syncfusion:TreeViewItemAdv>
<syncfusion:TreeViewItemAdv Header="Country Information" />
</syncfusion:TreeViewAdv>

{% endhighlight %}

{% highlight C# %}

//set FakeDragIndicator is true
treeViewAdv.IsFakeDragIndicator = true;

{% endhighlight %}

{% highlight VB %}

'set FakeDragIndicator is true
treeViewAdv.IsFakeDragIndicator = True

{% endhighlight %}

{% endtabs %}  

![Dragged the fake WPF TreeView items from one location to another](Dragging_treeview_items_images/Dragging_treeview_items_img3.jpeg)
