# Context Menu

In graphical user interface (GUI), a ContextMenu is a type of Menu that appears when you perform right-click operation. Nested level of Context Menu items can be created. Diagram provided some in-build ContextMenu items and allows to define custom menu items.

Default Context Menu

The ContentMenu Constraint helps you to enable/disable the context menu. Diagram provides some default context menu items to ease the execution of some frequently used commands. 

![](ContextMenu_images/ContextMenu_img1.jpeg)


The following code illustrates how to enable/disable the default context menu items.

<table>
<tr>
<td>
//Disable context menu<br/><br/>diagram.Constraints = GraphConstraints.Default & ~GraphConstraints.ContextMenu;<br/><br/>//Enable context menu<br/><br/>diagram.Constraints = GraphConstraints.Default | GraphConstraints.ContextMenu;<br/><br/><br/><br/></td></tr>
</table>
****Customize Context Menu

Apart from the default ContextMenu items, you can define some additional menu items by using Menu property of SfDiagram, Node and Connector. Those additional items have to be defined and added to MenuItems. 

The following code example illustrates how to add custom context menu items to Menu property of SfDiagram.

<table>
<tr>
<td>
DiagramMenuItem menu = new DiagramMenuItem() <br/><br/>{<br/><br/>Content = "Delete", <br/><br/>Command = (diagram.Info as IGraphInfo).Commands.Delete,<br/><br/>Icon = @"pack://application:,,,/WpfApplication1;component/delete.png"<br/><br/>};<br/><br/>Diagram.Menu.MenuItems.Add(menu);<br/><br/></td></tr>
</table>


![](ContextMenu_images/ContextMenu_img2.jpeg)


Menu for Node and Connector

The default value of Menu property for Node and Connector is null.

The following code example illustrates how to set ContextMenu and ContextMenuitems to Node.

<table>
<tr>
<td>
node.Constraints = node.Constraints | NodeConstraints.Menu;<br/><br/>node.Menu = new DiagramMenu();<br/><br/>node.Menu.MenuItems=new ObservableCollection<DiagramMenuItem>();<br/><br/>DiagramMenuItem mi = new DiagramMenuItem()<br/><br/>{<br/><br/>Content = "Delete",<br/><br/>Icon = @"pack://application:,,,/WpfApplication1;component/delete.png",<br/><br/>Command = (diagram.Info as IGraphInfo).Commands.Delete<br/><br/>};<br/><br/>(node.Menu.MenuItems as ICollection<DiagramMenuItem>).Add(mi);<br/><br/></td></tr>
</table>
![](ContextMenu_images/ContextMenu_img3.jpeg)


You can be notified with events when you click the custom menu items. The following code example illustrates the how to define the event for custom context menu.

<table>
<tr>
<td>
menu.ClickedEvent += menu_ClickedEvent;<br/><br/>private void menu_ClickedEvent(object sender, MenuItemClickedEventArgs args)<br/><br/>{<br/><br/>//Source – in which object Event get fired<br/><br/>//Item-  MenuItem     <br/><br/>}<br/><br/><br/><br/></td></tr>
</table>
Context Menu Events

You would be notified with events when you click the menu items. The following code example illustrates how to define those events.

<table>
<tr>
<td>
(Diagram.Info as IGraphInfo).MenuItemClickedEvent += MainPage_MenuItemClickedEvent;<br/><br/>void MainPage_MenuItemClickedEvent(object sender, MenuItemClickedEventArgs args)<br/><br/>{<br/><br/>//Source – in which object Event get fired<br/><br/>//Item-  MenuItem     <br/><br/>}<br/><br/><br/><br/></td></tr>
</table>
