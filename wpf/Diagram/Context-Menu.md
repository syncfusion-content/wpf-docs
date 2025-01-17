---
layout: post
title: Context Menu in WPF Diagram control | Syncfusion
description: Learn here all about Context Menu support in Syncfusion WPF Diagram (SfDiagram) control, its elements and more.
platform: wpf
control: SfDiagram
documentation: ug
---

# Context Menu in WPF Diagram (SfDiagram)

In graphical user interface (GUI), a ContextMenu is a type of Menu that appears when you perform right-click operation. Nested level of Context Menu items can be created. Diagram provided some in-built ContextMenu items and allows to define custom menu items.

## Default Context Menu

The `ContextMenu` Constraint helps you to enable/disable the context menu. The following code illustrates how to enable/disable the default context menu items.

{% tabs %}
{% highlight C# %}

//Disable context menu
diagram.Constraints = GraphConstraints.Default & ~GraphConstraints.ContextMenu;

//Enable context menu
diagram.Constraints = GraphConstraints.Default | GraphConstraints.ContextMenu;

{% endhighlight %}
{% endtabs %}

Diagram provides some default context menu items to ease the execution of some frequently used commands. 

![Default Menu](Context-Menu_images/Context-Menu_img1.png)

## Customize Context Menu

* Apart from the default ContextMenu items, you can define some additional menu items by using `Menu` property of SfDiagram, Node and Connector. Those additional items have to be defined and added to `MenuItems` Property. 

* The `Content` property allows you to set Content for the context menu item.

* The `Icon` property allows you to set icon for the context menu item.

* The `Command` property of the Context menu item allows you to define command for it.

* The `IsSeparator` property defines the horizontal lines that are used to separate the menu items. You cannot select the separators. You can enable separators to group the menu items using the `IsSeparator` property.

The following code example illustrates how to add custom context menu items to Menu property of SfDiagram.

{% tabs %}
{% highlight C# %}

DiagramMenuItem menu = new DiagramMenuItem() 
{
	Content = "Delete", 
	Command = (diagram.Info as IGraphInfo).Commands.Delete,
	Icon = @"pack://application:,,,/delete.ico"
};
diagram.Menu.MenuItems.Add(menu);

{% endhighlight %}
{% endtabs %}

![Custom Menu](Context-Menu_images/Context-Menu_img2.png)

### Menu for Node and Connector

The default value of Menu property for Node and Connector is null.The following code example illustrates how to set ContextMenu and ContextMenuItems to Node.

{% tabs %}
{% highlight C# %}

node.Constraints = node.Constraints | NodeConstraints.Menu;
node.Constraints = node.Constraints & ~NodeConstraints.InheritMenu;
node.Menu = new DiagramMenu();
node.Menu.MenuItems=new ObservableCollection<DiagramMenuItem>();
DiagramMenuItem mi = new DiagramMenuItem()
{
	Content = "Delete",
	Command = (diagram.Info as IGraphInfo).Commands.Delete,
	Icon = @"pack://application:,,,/delete.ico"
};
(node.Menu.MenuItems as ICollection<DiagramMenuItem>).Add(mi);

{% endhighlight %}
{% endtabs %}

![Node Custom Menu](Context-Menu_images/Context-Menu_img3.png)

[View Sample in GitHub](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/ContextMenu) 

## Events

* `MenuItemClickedEvent`will invoke when you click the menu items. To explore about arguments, refer to [MenuItemClickedEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.MenuItemClickedEventArgs.html)

The following code example illustrates how to define those events.

{% tabs %}
{% highlight C# %}

(diagram.Info as IGraphInfo).MenuItemClickedEvent += 
	MainPage_MenuItemClickedEvent;

void MainPage_MenuItemClickedEvent(object sender, 
	MenuItemClickedEventArgs args)
{
	//Source – in which object Event get fired
    //Item - MenuItem
}

{% endhighlight %}
{% endtabs %}

* `MenuOpening` event will notify when you perform right click on Diagram/Node/Connector.To explore about arguments, refer to [MenuOpeningEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.MenuOpeningEventArgs.html).

## See Also

[How to customize the context menu?](https://www.syncfusion.com/kb/10467/how-to-customize-the-contextmenu-in-wpf-sfdiagram)

[How to display images, image URI and shapes for menu items icon?](https://support.syncfusion.com/kb/article/13009/how-to-display-images-image-uri-and-shapes-for-menu-items-icon-in-wpf-diagram)

[How to add icon to context menu item?](https://support.syncfusion.com/kb/article/10986/how-to-add-icon-to-context-menu-item-in-wpf-diagram-sfdiagram)

[How to Add Textbox as a SubMenuItem in WPF SfDiagram?](https://support.syncfusion.com/kb/article/18494/how-to-add-textbox-as-a-submenuitem-in-wpf-sfdiagram)

[How can I display different context menus for various types of diagram elements and the diagram area in the WPF Diagram (SfDiagram)?](https://support.syncfusion.com/kb/article/18236/how-can-i-display-different-context-menus-for-various-types-of-diagram-elements-and-the-diagram-area-in-the-wpf-diagram-sfdiagram)

[How to add a node as a child of a container using the context menu in the WPF Diagram (SfDiagram)?](https://support.syncfusion.com/kb/article/18053/how-to-add-a-node-as-a-child-of-a-container-using-the-context-menu-in-the-wpf-diagram-sfdiagram)

[How to display the paste context menu only after cutting or copying nodes in a diagram in WPF Diagram (SfDiagram)?](https://support.syncfusion.com/kb/article/17759/how-to-display-the-paste-context-menu-only-after-cutting-or-copying-nodes-in-a-diagram-in-wpf-diagram-sfdiagram)

[How to enable or disable custom context menu items based on a node's selection in WPF Diagram (SfDiagram) ?](https://support.syncfusion.com/kb/article/17784/how-to-enable-or-disable-custom-context-menu-items-based-on-a-nodes-selection-in-wpf-diagram-sfdiagram-)

[How to add a container as parent of the selected node using the context menu in the WPF Diagram (SfDiagram)?](https://support.syncfusion.com/kb/article/17747/how-to-add-a-container-as-parent-of-the-selected-node-using-the-context-menu-in-the-wpf-diagram-sfdiagram)

[How to set a shortcut key for menu items in the Context Menu in WPF Diagram (SfDiagram)?](https://support.syncfusion.com/kb/article/14975/how-to-set-a-shortcut-key-for-menu-items-in-the-context-menu-in-wpf-diagram-sfdiagram)

[How to change the annotation content of a node using context menu in WPF Diagram (SfDiagram)?](https://support.syncfusion.com/kb/article/14962/how-to-change-the-annotation-content-of-a-node-using-context-menu-in-wpf-diagram-sfdiagram)

[How to implement color palette functionality using context menu in WPF Diagram (SfDiagram)?](https://support.syncfusion.com/kb/article/14963/how-to-implement-color-palette-functionality-using-context-menu-in-wpf-diagram-sfdiagram)

[How to display images, image URI and shapes for menu items icon in WPF Diagram?](https://support.syncfusion.com/kb/article/13009/how-to-display-images-image-uri-and-shapes-for-menu-items-icon-in-wpf-diagram)

[How to add icon to context menu item in WPF Diagram (SfDiagram)?](https://support.syncfusion.com/kb/article/10986/how-to-add-icon-to-context-menu-item-in-wpf-diagram-sfdiagram)
