---
layout: post
title: Varies interactions of stencil in WPF Diagram control | Syncfusion
description: Learn here all about varies interaction on stencil in Syncfusion WPF Diagram (SfDiagram) control ports.
platform: wpf
control: SfDiagram
documentation: ug
---

# Stencil interactions in WPF Diagram (SfDiagram)

Stencil symbols can be selected, dragged, and reordered over stencil control.

## Symbol selection

Stencil offers the flexibility to select either a single symbol or multiple symbols simultaneously, allowing you to easily place them on the diagram surface. You can control the symbol selection mode using the [`SymbolSelectionMode`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Stencil.Stencil.html#Syncfusion_UI_Xaml_Diagram_Stencil_Stencil_SymbolSelectionMode) property within the 'Stencil' class. This capability enables users to switch between single and multiple symbol selections to align with their preferences. By default, the stencil allows the selection of multiple symbols.

|SelectionMode|Description|
|----------|-----------|
| Single | Only one symbol can be selected at a time |
| Multiple | Multiple symbols can be selected either using ctrl key or using rubber band selection |

### Single selection

A symbol can be selected by clicking on that symbol. During single click, all previously selected items will be cleared.

![Symbol single selection](Stencil_images/SymbolSingleSelection.png)

### Multiple selection

Multiple elements can be selected with the following ways:

1. Ctrl+click

By holding down the Ctrl key and clicking each symbol that you want to select or deselect allows you to select or deselect multiple symbols.

2. Rubber band selection

Clicking and dragging on the stencil area allows you to create a rectangular region. The elements that are covered under the rectangular region are selected at the end.

![Rubber band selection](Stencil_images/SymbolRubberbandSelection.gif)

### Duplicate symbols

#### Duplicate the symbols within the Symbol Group:

Stencil allows users to duplicate symbols within the [SymbolGroup](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Stencil.SymbolGroup.html) by holding down the Ctrl key and dragging and dropping the symbol to your desired location within the current symbol group.

![WithinAGroup](Stencil_images/DuplicateSymbolsWithinGroup.gif)

#### Duplicate the symbols from one symbol group to another symbol group:
 
Stencil allows users to clone symbols from one [SymbolGroup](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Stencil.SymbolGroup.html) to another by dragging them while holding the Ctrl key and dropping them onto the symbol group header.

![OneGroupToAnotherGroup](Stencil_images/DuplicateSymbolToAnotherGroup.gif)

## Symbol reordering

Stencil provides support to reorder the symbols within the specific [SymbolGroup](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Stencil.SymbolGroup.html). By default, symbols reordering will be enabled. Symbol reordering can be disabled by removing `AllowDragDrop` constraint from
[`StencilConstraints`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.StencilConstraints.html) property of stencil class.

{% highlight C# %}

//Enables the the symbols reordering.
stencil.StencilConstraints |= StencilConstraints.AllowDragDrop;

//Disables the symbols reordering.
stencil.StencilConstraints &= ~StencilConstraints.AllowDragDrop;

{% endhighlight %}

![Symbol reordering](Stencil_images/SymbolReordering.gif)

## Events

* The `ExpandedEvent` and `CollapsedEvent` are notified to provide interactions in the SymbolGroup. To explore about arguments, refer to this [SymbolGroupExpandCollapseEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Stencil.SymbolGroupExpandCollapseEventArgs.html) class.

* The `DragEnterEvent` notifies when an element enters into the diagram from a stencil.
* The `DragLeaveEvent` notifies when an element leaves from the diagram.
* The `DragOverEvent` notifies when an element drag over another diagram element.
* The `ItemDropEventEvent` notifies when an element is dropped on the diagram. 

To explore about arguments, refer to this [ItemDropEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.ItemDropEventArgs.html) class.

## Preview for drag and drop

When you drag an item from the stencil to the diagram, a preview of the dragged item will be displayed. Preview of the item can be enabled or disabled by using `ShowPreview` constraint from [`StencilConstraints`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.StencilConstraints.html) property.

{% highlight C# %}

//Enables the drag and drop preview.
stencil.Constraints = stencil.Constraints | StencilConstraints.ShowPreview;

//Disables the drag and drop preview.
stencil.Constraints = stencil.Constraints & ~StencilConstraints.ShowPreview;

{% endhighlight %}

Here, the stencil is an instance of Stencil.

![Preview](Stencil_images/ShowPreview.png)

### Customization of preview for drag and drop

You can customize the preview content by overriding the [PrepareDragDropPreview](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Stencil.Stencil.html#Syncfusion_UI_Xaml_Diagram_Stencil_Stencil_PrepareDragDropPreview) method of the stencil. You can also define your customized preview to the [`SymbolPreview`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Stencil.Stencil.html#Syncfusion_UI_Xaml_Diagram_Stencil_Stencil_SymbolPreview) property of the stencil.

{% tabs %}
{% highlight C# %}
public class CustomStencil : Stencil
{
    //Virtual method to customize the preview of dragging the symbol from a stencil.
    protected override void PrepareDragDropPreview()
    {
        this.SymbolPreview = new ContentPresenter()
        {
            Content = new Rectangle()
            {
                Width = 50,
                Height = 50,
                Fill = new SolidColorBrush(Colors.SteelBlue)
            }
        };
    }
}

{% endhighlight %}
{% endtabs %}

![CustomPreview](Stencil_images/CustomShowPreview.png)

## Restrict the node dropped on Diagram

The diagram provides support to cancel the drag and drop operation from the stencil to the diagram in two ways:

* Using the `Cancel` argument of `ItemDropEventArgs`. For example, if you need to restrict drop for a particular node or based on some condition, then this argument will allow you to achieve the same. To explore about arguments, refer to the [ItemDropEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.ItemDropEventArgs.html).
 
* When the ESC key is pressed.

The following code example explains how to cancel item drop of basic shapes from the stencil.

{% tabs %}
{% highlight xaml %}
<!--Initialize the custom stencil-->
<local:CustomStencil x:Name="stencil" Title="Shapes"
ExpandMode="ZeroOrMore" BorderBrush="#dfdfdf" BorderThickness="1">
</local:CustomStencil>
{% endhighlight %}
{% highlight C# %}
//Creating the diagram instance.
SfDiagram diagram = new SfDiagram();
//Hook the item drop event of diagram.
(diagram.Info as IGraphInfo).ItemDropEvent += MainWindow_ItemDropEvent;
private void MainWindow_ItemDropEvent(object sender, ItemDropEventArgs args)
{
    //To cancel item drop if symbols are basic shapes.
    if (args.ItemSource == Cause.Stencil && args.Source is INode && (args.Source as INode).Key.ToString() == "Basic Shapes")
    {
        args.Cancel = true;
    }
}

{% endhighlight %}
{% endtabs %}

Nodes that are added in the Basic Shapes category will not be added on the diagram page when it dropped.

## Symbol dragging outside diagram bounds

By default, the cursor appears as a block cursor when dragging the symbol (from stencil) outside the diagram bounds. The SfDiagram provides supports to drag the elements within the given limitations. For details, please refer to this [DragLimit](https://help.syncfusion.com/wpf/diagram/scroll-settings/draglimit) to restrict the symbol dragging outside the limited area.

![Block cursor](Stencil_images/BlockCursor.gif)

## Preserving the node template when dragging and dropping

The Diagram control allows you to drag and drop elements from a stencil using the serialization and deserialization approach, but it does not serialize the framework properties like the [`Content`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.NodeViewModel.html#Syncfusion_UI_Xaml_Diagram_NodeViewModel_Content) and [`ContentTemplate`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.NodeViewModel.html#Syncfusion_UI_Xaml_Diagram_NodeViewModel_ContentTemplate) properties. So, you need to retain templates as a resource and reassign them once it loaded back in the diagram. This can be achieved by using the `ItemAddedEvent` to restore the `Content` and `ContentTemplate` property values.

{% tabs %}
{% highlight C# %}

private void MainWindow_ItemAdded(object sender, ItemAddedEventArgs args) 
{ 
    if(args.Item is CustomNode) 
    { 
        CustomNode node = args.Item as CustomNode;
        //content and contenttemplate returns null, so we have used the CustomContent and CustomContentTemplate properties to restore its values. 
        node.Content = node.CustomContent; 
        node.ContentTemplate = App.Current.MainWindow.Resources[node.CustomContentTemplate] as DataTemplate; 
    } 
} 

![Content Template](Stencil_images/SymbolContentTemplate.png)

{% endhighlight %}
{% endtabs %}

[View Sample in GitHub](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/Stencil/Stencil%20Drag%20Drop%20Template)

## Keyboard Support for Stencil in WPF Diagram

The Stencil in WPF Diagram (SfDiagram) provides support for interacting with its elements using keyboard shortcuts. By default, certain built-in commands are bound to specific key combinations to enhance user efficiency. 

The following table illustrates the list of commands along with their associated key gestures:

| Shortcut Key | Command               | Description                                                                   |
|--------------|-----------------------|-------------------------------------------------------------------------------|
| Ctrl + X     | Cut                   | Cut the selected symbols from the symbol group                                |
| Ctrl + C     | Copy                  | Copy the selected symbols to the clipboard                                    |
| Ctrl + V     | Paste                 | Paste the symbol from the clipboard into the symbol group                     |
| Ctrl + A     | SelectAll             | Select all the symbols in the current symbol group                            |
| Escape       | UnSelect              | Deselect any selected symbols in the symbol group                             |
| Delete       | Delete                | Delete the selected symbols                                                   |
| UpArrow      | MoveUp                | Move the selection to the symbol above in the symbol group                    |
| DownArrow    | MoveDown              | Move the selection to the symbol below in the symbol group                    |
| RightArrow   | MoveRight             | Move the selection to the symbol to the right in the symbol group             |
| LeftArrow    | MoveLeft              | Move the selection to the symbol to the left in the symbol group              |
| Home         | MoveToFirstInRow      | Move the selection to the first symbol in the current row of the symbol group |
| End          | MoveToLastInRow       | Move the selection to the last symbol in the current row of the symbol group  |
| Page Up      | MoveToFirstInColumn   | Move the selection to the first symbol in the current column of the symbol group| 
| Page Down    | MoveToLastInColumn    | Move the selection to the last symbol in the current column of the symbol group |




## See also

[How to refresh the stencil with new collection or new symbol?](https://support.syncfusion.com/kb/article/8714/how-to-refresh-stencil-with-new-collection-or-symbol-in-wpf-diagram)

[How to restrict the symbol dropping from the SymbolPalette?](https://support.syncfusion.com/kb/article/9919/how-to-restrict-the-symbol-dropping-from-the-symbolpalette-in-the-wpf-diagram-sfdiagram)

[How to create parent and child relationship by drag and drop nodes?](https://support.syncfusion.com/kb/article/10008/how-to-create-parent-and-child-relationship-by-drag-and-drop-nodes-in-wpf-diagram-sfdiagram)

[How to expand all symbol groups in stencil?](https://support.syncfusion.com/kb/article/5492/how-to-expand-all-symbol-groups-in-wpf-diagram-sfdiagram)