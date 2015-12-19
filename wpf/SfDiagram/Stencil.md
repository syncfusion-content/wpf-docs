# Stencil

Stencil has a collection of Symbols. Stencil is used to clone the desired symbol by dragging it from the Stencil and dropping it into the SfDiagram. Each symbol can be grouped together by using the SymbolGroupProvider and filteres by using the SymbolFilterProvider through delegates.

<table>
<tr>
<td>
xmlns:stencil="clr-namespace:Syncfusion.UI.Xaml.Diagram.Stencil;assembly=Syncfusion.SfDiagram.Wpf"<br/><br/><br/><br/></td></tr>
</table>
![](Stencil_images/Stencil_img1.jpeg)


Key Terms Table

<table>
<tr>
<td>
Key Terms<br/><br/></td><td>
Description<br/><br/></td></tr>
<tr>
<td>
Symbol<br/><br/></td><td>
To visualize the items in Stencil.<br/><br/></td></tr>
</table>
Properties Table

<table>
<tr>
<td>
Properties<br/><br/></td><td>
Description<br/><br/></td></tr>
<tr>
<td>
SymbolGroups<br/><br/></td><td>
Collection of SymbolGroupProvider To Group the Symbols based on the MappingName Property.<br/><br/></td></tr>
<tr>
<td>
SymbolFilters<br/><br/></td><td>
Collection of SymbolFilterProvider To filter/Hide the Symbols based on MappingName Property.<br/><br/></td></tr>
<tr>
<td>
SymbolSource<br/><br/></td><td>
ItemSource for Stencil to populate the SymbolGroups with symbol.<br/><br/></td></tr>
</table>
Symbol

Symbol is used to implement the ISymbol interface. The ISymbol interface consists of two properties to visualize symbols in Stencil:

Symbol and SymbolTemplate

<table>
<tr>
<td>
public class SymbolItem : ISymbol<br/><br/>{<br/><br/>public object Symbol { get; set; }<br/><br/>public object Key { get; set; }<br/><br/>public DataTemplate SymbolTemplate { get; set; }<br/><br/>public ISymbol Clone()<br/><br/>{<br/><br/>return new SymbolItem()<br/><br/>{<br/><br/>Symbol = this.Symbol,<br/><br/>SymbolTemplate = this.SymbolTemplate,<br/><br/>};<br/><br/>}<br/><br/>public object GroupName { get; set; }<br/><br/>}<br/><br/><br/><br/></td></tr>
</table>
Adding the Symbol

The following example illustrates how to add the Symbol into a Collection:

1. Create the ISymbol with Symbol and SymbolTemplate properties.
<table>
<tr>
<td>
<br/><local:SymbolItem GroupName="Flow Chart" Symbol="FlowChart_Star" <br/><br/>SymbolTemplate="{StaticResource FlowChart_Star}"/><br/><br/><br/><br/></td></tr>
</table>
2. Define the SymbolTemplate.
<table>
<tr>
<td>
<br/><DataTemplate x:Key="FlowChart_Star"><br/><br/><Path Style="{StaticResource SymbolStyle}" Data="M 9,2 11,7 17,7 12,10 14,15 9,12   <br/><br/>4,15 6,10 1,7 7,7 Z" Stretch="Fill"/><br/><br/></DataTemplate><br/><br/><br/><br/></td></tr>
</table>
3. Add the ISymbol into the Collection.
<table>
<tr>
<td>
<br/>public class SymbolCollection : ObservableCollection<ISymbol><br/><br/>{<br/><br/>}<br/><br/><br/><br/></td></tr>
</table>
<table>
<tr>
<td>
<local:SymbolCollection x:Key="symbolcollection"><br/><br/><local:SymbolItem GroupName="Flow Chart" Symbol="FlowChart_Star" <br/><br/>SymbolTemplate="{StaticResource FlowChart_Star}"/><br/><br/></local:SymbolCollection><br/><br/><br/><br/></td></tr>
</table>
![](Stencil_images/Stencil_img2.jpeg)


This Collection will be the SymbolSource to the Stencil. Based on the SymbolSource, the Stencil will populate the Symbols.

Add Node, Connector and Group to Stencil

1. Create a custom class (SymbolItem in this example) that derives ISymbol and implements necessary things.
<table>
<tr>
<td>
<br/>public class SymbolItem : ISymbol<br/><br/>{<br/><br/>public object Symbol { get; set; }<br/><br/>public object GroupName { get; set; }<br/><br/>public DataTemplate SymbolTemplate { get; set; }<br/><br/>public ISymbol Clone()<br/><br/>{<br/><br/>return new SymbolItem()<br/><br/>{<br/><br/>Symbol = this.Symbol,<br/><br/>SymbolTemplate = this.SymbolTemplate<br/><br/>};<br/><br/>}<br/><br/>public object Key { get; set; }<br/><br/>}<br/><br/><br/><br/></td></tr>
</table>
1. Create a Node ,Connector and Group and to SymbolCollection
<table>
<tr>
<td>
<br/><!--Collection of Symbols--><br/><br/><sync:SymbolCollection><br/><br/><!--ISymbol--><br/><br/><local:SymbolItem GroupName="Nodes"><br/><br/><local:SymbolItem.Symbol><br/><br/><!--NodeViewModel--><br/><br/><sync:NodeViewModel UnitHeight="50" UnitWidth="50" OffsetX="200" OffsetY="200" ShapeStyle="{StaticResource nodestyle}"><br/><br/><sync:NodeViewModel.Shape><br/><br/><RectangleGeometry Rect="10,10,10,10"></RectangleGeometry><br/><br/></sync:NodeViewModel.Shape><br/><br/></sync:NodeViewModel><br/><br/></local:SymbolItem.Symbol><br/><br/></local:SymbolItem><br/><br/><local:SymbolItem GroupName="Connectors"><br/><br/><local:SymbolItem.Symbol><br/><br/><!--ConnectorViewModel--><br/><br/><sync:ConnectorViewModel ConnectorGeometryStyle="{StaticResource connectorstyle}" SourcePoint="100,100" TargetPoint="200,200"/><br/><br/></local:SymbolItem.Symbol><br/><br/></local:SymbolItem><br/><br/><local:SymbolItem GroupName="Groups"><br/><br/><local:SymbolItem.Symbol><br/><br/><!--GroupViewModel--><br/><br/><sync:GroupViewModel><br/><br/><!--GroupViewModel.Nodes--><br/><br/><sync:GroupViewModel.Nodes><br/><br/><sync:NodeCollection><br/><br/><sync:NodeViewModel UnitHeight="50" UnitWidth="50" OffsetX="300" OffsetY="300" ShapeStyle="{StaticResource nodestyle}"><br/><br/><sync:NodeViewModel.Shape><br/><br/><EllipseGeometry RadiusX="10" RadiusY="10"/><br/><br/></sync:NodeViewModel.Shape><br/><br/></sync:NodeViewModel><br/><br/></sync:NodeCollection><br/><br/></sync:GroupViewModel.Nodes><br/><br/><!--GroupViewModel.Connectors--><br/><br/><sync:GroupViewModel.Connectors><br/><br/><sync:ConnectorCollection><br/><br/><sync:ConnectorViewModel ConnectorGeometryStyle="{StaticResource connectorstyle}"<br/><br/>SourcePoint="100,100" TargetPoint="200,200"/><br/><br/></sync:ConnectorCollection><br/><br/></sync:GroupViewModel.Connectors><br/><br/></sync:GroupViewModel><br/><br/></local:SymbolItem.Symbol><br/><br/></local:SymbolItem><br/><br/></sync:SymbolCollection><br/><br/></td></tr>
</table>
2. Add SymbolCollection to SymbolSource of Stencil
<table>
<tr>
<td>
<br/><stencil:Stencil x:Name="stencil" ExpandMode="All"><br/><br/><stencil:Stencil.SymbolSource><br/><br/><!--Collection of Symbols--><br/><br/><sync:SymbolCollection><br/><br/><!—from Step2--><br/><br/></sync:SymbolCollection><br/><br/></stencil:Stencil.SymbolSource><br/><br/><!--SymbolGroup--><br/><br/><stencil:Stencil.SymbolGroups><br/><br/><stencil:SymbolGroups><br/><br/><!--To Map Symbols based on GroupName--><br/><br/><stencil:SymbolGroupProvider MappingName="GroupName"/><br/><br/></stencil:SymbolGroups><br/><br/></stencil:Stencil.SymbolGroups><br/><br/></stencil:Stencil><br/><br/></td></tr>
</table>
![](Stencil_images/Stencil_img3.jpeg)


SymbolGroup

SymbolGroup is used group the Symbols in Stencil. The SymbolGroupProvider groups the symbols based on the MappingName property.

The following code example illustrates how to create a stencil

<table>
<tr>
<td>
<stencil:Stencil x:Name="stencil" SymbolSource="{StaticResource symbolcollection}"><br/><br/><stencil:Stencil.SymbolGroups><br/><br/><stencil:SymbolGroups><br/><br/><stencil:SymbolGroupProvider MappingName="GroupName"/><br/><br/></stencil:SymbolGroups><br/><br/></stencil:Stencil.SymbolGroups><br/><br/></stencil:Stencil><br/><br/><br/><br/></td></tr>
</table>
SymbolFilter 

This is used to filter the SymbolGroups in Stencil. SymbolFilterProvider is used for filtering the SymbolGroup by using Delegate. The desired Group can be displayed by using the SelectedFilter property.

The following code example shows how to define the SymbolFilter

<table>
<tr>
<td>
<stencil:Stencil.SymbolFilters><br/><br/><stencil:SymbolFilters><br/><br/><stencil:SymbolFilterProvider><br/><br/></stencil:SymbolFilterProvider><br/><br/></stencil:SymbolFilters><br/><br/></stencil:Stencil.SymbolFilters><br/><br/><br/><br/></td></tr>
</table>
The following code example shows how to define the SelectedFilter

<table>
<tr>
<td>
stencil.SelectedFilter = new SymbolFilterProvider() { Filter = Filter, Content = "Test" };<br/><br/><br/><br/></td></tr>
</table>
The following code example shows how to use Delegate for SymbolFilter

<table>
<tr>
<td>
private bool Filter(SymbolFilterProvider sender, ISymbol symbol)<br/><br/>{<br/><br/>if((symbol as SymbolItem).GroupName=="Flow Chart")<br/><br/>{<br/><br/>return true;<br/><br/>}<br/><br/>else<br/><br/>{<br/><br/>return false;<br/><br/>}<br/><br/>}<br/><br/><br/><br/></td></tr>
</table>
Symbol

Symbol is used to implement the ISymbol interface. The ISymbol interface consists of two properties to visualize symbols in the Stencil.

<table>
<tr>
<td>
Property<br/><br/></td><td>
Description<br/><br/></td></tr>
<tr>
<td>
Symbol<br/><br/></td><td>
Symbol accepts any object<br/><br/></td></tr>
<tr>
<td>
SymbolTemplate<br/><br/></td><td>
DataTemplate to visualize the symbol in Stencil<br/><br/></td></tr>
</table>


Preview for Drag and Drop

SfDiagram provides preview support for Stencil. When you drag an item from Stencil to Diagram, a preview of the dragged item will be displayed. You can enable or disable the preview support. You can also customize the preview.

Use Case Scenario

This feature displays a preview of the item you drag from Stencil, enabling you to identify the item you are dragging from the Stencil to the SfDiagram control. It also it gives a preview of the size and appearance of the item before it is dropped.

Enabling preview

To enable preview for the dragged item from Stencil, set the Constraints property of Stencil to ShowPreview. To disable preview, remove ShowPreview from Constraints property. By default, preview for drag and drop is enabled.

The following code example illustrates how to enable preview support

<table>
<tr>
<td>
//Enables the drag and drop preview.<br/><br/>stencil.Constraints = stencil.Constraints | StencilConstraints.ShowPreview;<br/><br/>//Disables the drag and drop preview.<br/><br/>stencil.Constraints = stencil.Constraints & ~StencilConstraints.ShowPreview;<br/><br/><br/><br/></td></tr>
</table>
Here, Stencil is an instance of Stencil.

![](Stencil_images/Stencil_img4.jpeg)


Customization of Preview for Drag and Drop

You can customize the preview content by overriding the PrepareDragDropPreview method of the Stencil feature. The following code example illustrates how to customize preview content.

<table>
<tr>
<td>
public class CustomStencil : Stencil<br/><br/>{<br/><br/>protected override void PrepareDragDropPreview()<br/><br/>{<br/><br/>this.SymbolPreview = new ContentPresenter()<br/><br/>{<br/><br/>Content = new Rectangle()<br/><br/>{<br/><br/>Width = 50,<br/><br/>Height = 50,<br/><br/>Fill = new SolidColorBrush(Colors.SteelBlue)<br/><br/>}<br/><br/>};<br/><br/>}<br/><br/>}<br/><br/><br/><br/></td></tr>
</table>
SymbolGroups

The SymbolGroupProvider groups the symbols into SymbolGroup based on the MappingName property.

<table>
<tr>
<td>
Name<br/><br/></td><td>
Description<br/><br/></td></tr>
<tr>
<td>
MappingName<br/><br/></td><td>
Used to group the symbols by mapping this property to the custom property of Symbols.<br/><br/></td></tr>
</table>
The following code example illustrates how to create a SymbolGroup

<table>
<tr>
<td>
<stencil:Stencil x:Name="stencil" SymbolSource="{StaticResource symbolcollection}"><br/><br/><stencil:Stencil.SymbolGroups><br/><br/><stencil:SymbolGroups><br/><br/><stencil:SymbolGroupProvider MappingName="GroupName"/><br/><br/></stencil:SymbolGroups><br/><br/></stencil:Stencil.SymbolGroups><br/><br/></stencil:Stencil><br/><br/><br/><br/></td></tr>
</table>
Expand or Collapse SymbolGroup

Expand and Collapse can be performed on SymbolGroup (updating the Visibility of the Symbols) based on the ExpandMode property. It includes the following options. The default option is One.

<table>
<tr>
<td>
S.No<br/><br/></td><td>
Expand Mode<br/><br/></td><td>
Description<br/><br/></td></tr>
<tr>
<td>
1.<br/><br/></td><td>
One <br/><br/></td><td>
Always one SymbolGroup is in expanded state.<br/><br/></td></tr>
<tr>
<td>
2.<br/><br/></td><td>
OneOrMore<br/><br/></td><td>
At least one SymbolGroup is in expanded state.<br/><br/></td></tr>
<tr>
<td>
3.<br/><br/></td><td>
ZeroOrOne<br/><br/></td><td>
Not more than a single SymbolGroup is in expanded state. All ‘SymbolGroup’ can be in collapsed state.<br/><br/></td></tr>
<tr>
<td>
4<br/><br/></td><td>
ZeroOrMore<br/><br/></td><td>
Any number of SymbolGroup can be in the expanded state. All ‘SymbolGroup’ can be in collapsed state.<br/><br/></td></tr>
<tr>
<td>
5.<br/><br/></td><td>
All<br/><br/></td><td>
All the SymbolGroup is in expanded state.<br/><br/></td></tr>
</table>
SymbolFilters

SymboFilterProvider is used to filter or hide the symbols by using delegates. SymbolFilters are the collection of SymbolFilterProvider.

The following code example shows how to create and add the SymbolFilter. Based on the return Boolean value of the SymbolFilter delegate, the corresponding item is reoved from Stencil. When a SymbolGroup does not have any Symbols, the corresponding SymbolGroup is also removed.

<table>
<tr>
<td>
private void CreateFilters()<br/><br/>{<br/><br/>stencil.SymbolFilters = new SymbolFilters();<br/><br/>SymbolFilterProvider allFilter = new SymbolFilterProvider<br/><br/>{<br/><br/>Content = "All",<br/><br/>Filter = SymbolFilter<br/><br/>};<br/><br/>SymbolFilterProvider kitchenFilter = new SymbolFilterProvider<br/><br/>{<br/><br/>Content = "Kitchen",<br/><br/>Filter = SymbolFilter<br/><br/>};<br/><br/>stencil.SymbolFilters.Add(addFilter);<br/><br/>stencil.SymbolFilters.Add(kitchenFilter);<br/><br/>}<br/><br/>// sender: used to get the selected SymbolFilters<br/><br/>private bool SymbolFilter(SymbolFilterProvider sender, ISymbol symbol)<br/><br/>{<br/><br/>if (sender.Content.ToString() == "All")<br/><br/>{<br/><br/>return true;<br/><br/>}<br/><br/>if ((symbol as SymbolItem).GroupName == sender.Content.ToString())<br/><br/>{<br/><br/>return true;<br/><br/>}<br/><br/>return false;<br/><br/>}<br/><br/><br/><br/></td></tr>
</table>
SelectedFilter

There can be multiple SymbolFilters, but only one filter can be selected at a time. These SymbolFilters are visually represented in a combo box. When the selected item is changed in the combo box, SelectedFilter is updated accordingly.

![](Stencil_images/Stencil_img5.jpeg)


