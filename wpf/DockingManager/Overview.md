---
layout: post
title: Overview
description: overview
platform: wpf
control: DockingManager
documentation: ug
---

# Overview

The DockingManager control implements an architecture that allows child controls to be docked to any part of a window as in Microsoft Visual Studio. You can add the DockingManager control as a child to your windows and add the child elements to this control to dock them. The dock panels containing the child elements can be interactively dragged to any area within the window, with the advanced support of effective visual cues. These windows can also be floated, tabbed, and auto hidden at run time.

Features

* DockingManager supports different dock states such as Docking, Floating, AutoHide and Document.
* Multiple Document Interface (MDI)/Tabbed Document Interface(TDI) windows are available in Docking Manager .
* Built-in Dock Fill mode to manage the layout.
* Various in-built window switchers available for navigating in between the windows 
* In-built Context Menu support such as Tablist context menu and Tabitem context menu support. 
* Docking support in all possible ways for the docking elements.
* WFH support for the DockingManager controls.
* Complete layout support.
* Support for Resizing Splitters.
* Support for several built-in skins.
* Different types of auto hide animation such as Fade, Scale or Slide.
* Complete bendability support for customizing appearance of docking windows.
* Complete support for customizing behavior of docking windows.
* ToolTip support for all default buttons.
* Localization support.
* Different types of dragging modes such as Border, Shade and Content Dragging.
* Content Previewer support like Vista in tabbed dock mode.
* Complete Drag provider customization support is available.
* Complete serialization support of docking states.
## Control Structure




{ ![](Overview_images/Overview_img1.png) | markdownify }
{:.image }


Visual Tree: 

{ ![](Overview_images/Overview_img2.png) | markdownify }
{:.image }


## Class Diagram



{ ![http://help.syncfusion.com/ug_82/WPFUI_Tools/Images/Docking_Class.png](Overview_images/Overview_img3.png) | markdownify }
{:.image }


## Properties, Methods and Events

### Properties

#### Dependency Properties

_Dependency properties tables_

<table>
<tr>
<th>
Properties </th><th>
Description</th><th>
Type</th><th>
Accepted Value</th><th>
Reference</th></tr>
<tr>
<td>
ActiveWindow</td><td>
Gets/Sets the Active window for the DockingManager. The element assigned to this property will be displayed as an Activewindow.</td><td>
FrameworkElement</td><td>
</td><td>
Using ActiveWindow Property</td></tr>
<tr>
<td>
AutoHideAnimationMode</td><td>
Gets/Sets the AutoHideAnimationMode such as Scale, Fade  and Slide</td><td>
AutoHideAnimationMode</td><td>
FadeScaleSlide</td><td>
Using AutoHide Animation Modes</td></tr>
<tr>
<td>
AutoHideTabsMode</td><td>
Gets/Sets the AutoHideTabsMode which specifies when the group of tabbed children or only the activewindow of the tabbed group needs to be autohidden.</td><td>
AutoHideTabsMode</td><td>
AutoHideActiveAutoHideGroup</td><td>
Auto Hide Mode</td></tr>
<tr>
<td>
AutoHideVisibility</td><td>
Gets/Sets whether AutoHide button is visible or not.</td><td>
Bool</td><td>
</td><td>
AutoHide Visibility</td></tr>
<tr>
<td>
AwlButtonTemplate</td><td>
Gets/Sets the  ControlTemplate for Awl Toggle button.</td><td>
ControlTemplate</td><td>
</td><td>
Editing Styles and Templates Using Expression Blend</td></tr>
<tr>
<td>
BottomDragProvider</td><td>
Gets/Sets BottomDragProvider ControlTemplate for DockingManager.</td><td>
ControlTemplate</td><td>
</td><td>
Customizing the Drag Provider</td></tr>
<tr>
<td>
CloseButtonTemplate</td><td>
Gets/Sets the Close button template for Dock , Float AutoHide child</td><td>
ControlTemplate</td><td>
</td><td>
Customizing Close Button</td></tr>
<tr>
<td>
CloseTabs</td><td>
Gets/Sets CloseTabsMode, which specifies whether the ActiveWindow of the tab group needs to be closed or if the Entire tabbed group needs to be closed while clicking the close button.</td><td>
CloseTabModes</td><td>
CloseActiveCloseAll</td><td>
Closing Options for Tabbed Windows</td></tr>
<tr>
<td>
CollapseDefaultContextMenuItems</td><td>
Gets/Sets the value indicating whether to hide/show the default context menu items while right clicking on the DockingManager child headers.</td><td>
bool</td><td>
</td><td>
Collapse Default MenuItems</td></tr>
<tr>
<td>
ContainerMode</td><td>
Gets/Sets the TDI/MDI Modes for the Document child.</td><td>
DocumentContainerMode</td><td>
MDITDI</td><td>
Document State Child</td></tr>
<tr>
<td>
Children</td><td>
Gets the collection which holds the children of the DockingManager</td><td>
LogicalElementCollection</td><td>
</td><td>
Creating DockingManager Control</td></tr>
<tr>
<td>
CenterDragProvider</td><td>
Gets/Sets the ControlTemplate for Center drag Provider.</td><td>
ControlTemplate</td><td>
</td><td>
Customizing the Drag Provider</td></tr>
<tr>
<td>
ClientControl</td><td>
Holds the FrameworkElement, which is displayed in the ClientControl area of DockingManager.</td><td>
UIElement</td><td>
</td><td>
Hosting a Client Control</td></tr>
<tr>
<td>
DockedElementTabbedHostStyle</td><td>
Gets/Sets the DockedElementTabbedHost Style, which acts as a container for Docked Children</td><td>
Style</td><td>
</td><td>
DockHost Style</td></tr>
<tr>
<td>
DockFill</td><td>
Gets/Sets the value which specifies whether the docked children need to be filled in the whole client area of DockingManager.</td><td>
bool</td><td>
</td><td>
Using DockFill</td></tr>
<tr>
<td>
DockHeaderStyle</td><td>
Gets/Sets the style for Docked child header.</td><td>
Style</td><td>
</td><td>
Dock Window Header Style</td></tr>
<tr>
<td>
DockTabAlignment</td><td>
Gets/Sets the DockTabAlignment, which specifies the position of the tabbed child tabcontrol (top,bottom,left,right)</td><td>
Dock</td><td>
* Bottom* Top* Left* Right<br></td><td>
Tab Strip Placement</td></tr>
<tr>
<td>
DraggingType</td><td>
Gets/Sets the DraggingType, which specifies the type of Dragging of Float child (BorderDragging,NormalDragging,ShadowDragging) .</td><td>
DraggingType</td><td>
* BorderDragging* NormalDragging* ShadowDragging<br></td><td>
Using Drag modes</td></tr>
<tr>
<td>
ElementBorderThickness</td><td>
Gets/Sets the value indicating the Docked Child Border Thickness.</td><td>
Thickness</td><td>
</td><td>
Border Thickness of Child Elements</td></tr>
<tr>
<td>
EndDockHeaderHeight</td><td>
Gets the AutoHidden Window Height.</td><td>
double</td><td>
</td><td>
EndDockHeaderHeight</td></tr>
<tr>
<td>
FlipItems</td><td>
Gets the Collection of DockingManager children without duplication of elements.</td><td>
List<FrameworkElement></td><td>
</td><td>
How to use FlipItems property</td></tr>
<tr>
<td>
FloatWindowBorderBrush</td><td>
Gets/Sets the Brush value for FloatWindow Border.</td><td>
Brush</td><td>
</td><td>
FloatWindow Customization</td></tr>
<tr>
<td>
FloatWindowBorderThickness</td><td>
Gets/Sets the FloatWindowBorderThickness property, which specifies the border thickness of FloatWindow.</td><td>
Thickness</td><td>
</td><td>
Border Thickness of Child Elements</td></tr>
<tr>
<td>
FloatWindowHeaderBackground</td><td>
Gets/Sets the FloatWindowHeaderBackground property, which specifies the header background for docked window.</td><td>
Brush</td><td>
</td><td>
Editing Styles and Templates Using Expression Blend</td></tr>
<tr>
<td>
FloatWindowHeaderForeground</td><td>
Gets/Sets the FloatWindowHeaderForeground property, which specifies the header foreground for docked window.</td><td>
Brush</td><td>
</td><td>
FloatWindow Customization</td></tr>
<tr>
<td>
FloatWindowMouseOverBorderBrush</td><td>
Gets/Sets the FloatWindowMouseOverBorderBrush property, which specifies the Border brush when the mouse is rolled-over on the floatwindow.</td><td>
Brush</td><td>
</td><td>
FloatWindow Customization</td></tr>
<tr>
<td>
FloatWindowSelectedBorderBrush</td><td>
Gets/Sets the FloatWindowSelectedBorderBrush property, which specifies the selected border brush of active  FloatWindow</td><td>
Brush</td><td>
</td><td>
FloatWindow Customization</td></tr>
<tr>
<td>
FloatWindowSelectedHeaderBackground</td><td>
Gets/Sets the FloatWindowSelectedHeaderBackground property, which specifies the selected header background of FloatWindow.</td><td>
Brush</td><td>
</td><td>
FloatWindow Customization</td></tr>
<tr>
<td>
FloatWindowSelectedHeaderForeground</td><td>
Gets/Sets the FloatWindowSelectedHeaderForeground property, which specifies the selected header foreground.</td><td>
Brush</td><td>
</td><td>
FloatWindow Customization</td></tr>
<tr>
<td>
FloatWindowStyle</td><td>
Gets/Sets the Style property for the the FloatWindow</td><td>
Style</td><td>
</td><td>
FloatWindow Customization</td></tr>
<tr>
<td>
FloatWindowTemplate</td><td>
Gets/Sets the ControlTemplate for FloatWindow.</td><td>
ControlTemplate</td><td>
</td><td>
FloatWindow Customization</td></tr>
<tr>
<td>
IsRollupFloatWindow</td><td>
Gets/Sets IsRollUpFloatWindow, which enables/disables the rollup of FloatWindow when the header is clicked.</td><td>
bool</td><td>
</td><td>
Using of IsRollUpFloatWindow</td></tr>
<tr>
<td>
IsTDIDragDropEnabled</td><td>
Gets/Sets the IsTDIDragDropEnabled, which enables/disables the drag drop of TDI items</td><td>
bool</td><td>
</td><td>
How to disable Drag & Drop of TDI items</td></tr>
<tr>
<td>
LeftDragProvider</td><td>
Gets/Sets the Control Template for LeftDragProvider</td><td>
ControlTemplate</td><td>
</td><td>
Customizing the Drag Provider</td></tr>
<tr>
<td>
ShowTabItemContextMenu</td><td>
Gets/Sets the value indicating whether TabItemContextMenu can be shown or not.</td><td>
bool</td><td>
</td><td>
Customizing Document Tab Control and MDI Document</td></tr>
<tr>
<td>
ShowTabListContextMenu</td><td>
Gets/Sets the value indicating whether  TabListContextMenu can be shown or not.</td><td>
bool</td><td>
</td><td>
Customizing Document Tab Control and MDI Document</td></tr>
<tr>
<td>
SplitterBackground</td><td>
Gets/Sets the Splitter background which is between the Docked children.</td><td>
Brush</td><td>
</td><td>
How to set splitter background and size</td></tr>
<tr>
<td>
SwitchMode</td><td>
Gets/Sets the SwitchMode for Ctrl+Tab navigation of child.</td><td>
Switch Mode Enum</td><td>
</td><td>
SwitchMode usage</td></tr>
<tr>
<td>
TabControlStyle</td><td>
Gets/Sets the style for the TabControl, which holds the tabbed children. </td><td>
Style</td><td>
</td><td>
TabControl and TabItem Styles</td></tr>
<tr>
<td>
TabItemBorderThickness</td><td>
Gets/Sets the Tabitem border thickness for tabbed children.</td><td>
Thickness</td><td>
</td><td>
Border Thickness of Child Elements</td></tr>
<tr>
<td>
TabItemsBackground</td><td>
Gets/Sets the TabItem background for tabbed children.</td><td>
Brush</td><td>
</td><td>
Editing Styles and Templates Using Expression Blend</td></tr>
<tr>
<td>
TabItemsBorderThicknessSelected</td><td>
Gets/Sets the TabItems border thickness for the selected tabbed child.</td><td>
Thickness</td><td>
</td><td>
Border Thickness of Child Elements</td></tr>
<tr>
<td>
TabItemStyle</td><td>
Gets/Sets the TabItem style for tabbed children.</td><td>
Style</td><td>
</td><td>
Tab control and Tab Item Styles</td></tr>
<tr>
<td>
TabPanelBorderThickness</td><td>
Gets/Sets the TabPanelBorderThickness for Tabcontrol, which holds the tabbed children.</td><td>
Thickness</td><td>
</td><td>
Border Thickness of Child Elements</td></tr>
<tr>
<td>
TDIFullScreenMode</td><td>
Gets/Sets the TDIFullScreenMode property, which is used to enable /disable the fullscreen mode for Document tab control in DockingManager.</td><td>
bool</td><td>
</td><td>
How to use FullScreen mode</td></tr>
<tr>
<td>
UseAdornerDragProvider</td><td>
Gets/Sets the value indicating whether to use Adorner Drag Provider instead of Popup DragProvider.</td><td>
bool</td><td>
</td><td>
Using Adorner Drag Provider and Adorner FloatWindow</td></tr>
<tr>
<td>
UseAdornerFloatWindow</td><td>
Gets/Sets the value indicating whether to use Adorner FloatWindow instead of Popup floatWindow.</td><td>
bool</td><td>
</td><td>
Using Adorner Drag Provider and Adorner FloatWindow</td></tr>
<tr>
<td>
UseDocumentContainer</td><td>
Gets/Sets the value, which enables the Document State children in DockingManager.</td><td>
bool</td><td>
</td><td>
Document State Child</td></tr>
<tr>
<td>
UseInteropCompatibilityMode</td><td>
Gets/Sets the value indicating whether to use WFH as child content.</td><td>
bool</td><td>
</td><td>
Hosting Windows Form control in DockingManager</td></tr>
</table>
#### Attached Properties

_Attached properties table_

<table>
<tr>
<td>
Properties</td><td>
Description</td><td>
Type</td><td>
Values</td></tr>
<tr>
<td>
AnimationDelay</td><td>
Specifies the Autohide Animation delay for each child element.</td><td>
Duration</td><td>
</td></tr>
<tr>
<td>
CanAutoHide</td><td>
Specifies whether the child element can be hidden automatically or not.</td><td>
bool</td><td>
* True* False<br></td></tr>
<tr>
<td>
CanDock</td><td>
Specifies whether the child element can be docked or not.</td><td>
bool</td><td>
* True* False<br></td></tr>
<tr>
<td>
CanClose</td><td>
Specifies whether the child element can be closed or not.</td><td>
bool</td><td>
* True* False<br></td></tr>
<tr>
<td>
CanDrag</td><td>
Specifies whether the child can be dragged from Dock to Float state.</td><td>
bool</td><td>
* True* False<br></td></tr>
<tr>
<td>
CanFloat</td><td>
Specifies whether the child element is Floatable or not.</td><td>
bool</td><td>
* True* False<br></td></tr>
<tr>
<td>
CustomMenuItems</td><td>
Specifies items on the { [CustomMenuitem](http://help.syncfusion.com/ug_91/User%20Interface/WPF/Tools/default.htm?turl=Documents%2F3105262providingcustommenuitems.htm) | markdownify } collection to  provide user menu items to choose from, for the header context menu for child element.</td><td>
CustomMenuItemCollection</td><td>
</td></tr>
<tr>
<td>
DesiredHeightInDockedMode</td><td>
Specifies the DesiredHeight of the child element in Docked State.</td><td>
double</td><td>
</td></tr>
<tr>
<td>
DesiredWidthInDockedMode</td><td>
Specifies the DesiredWidth of the child element in Docked State.</td><td>
double</td><td>
</td></tr>
<tr>
<td>
DockAbility</td><td>
Specifies the dockability of the child element, while docking it in the internal DockedElementTabbedHost. Refer to { [Dockability](http://help.syncfusion.com/ug_91/User%20Interface/WPF/Tools/default.htm?turl=Documents%2F31088dockabilityofchild.htm) | markdownify } for more information.</td><td>
DockAbility</td><td>
* {{ '_All_' | markdownify }}* {{ '_Bottom_' | markdownify }}* {{ '_Horizontal_' | markdownify }}* {{ '_Left_' | markdownify }}* {{ '_None_' | markdownify }}* {{ '_Right_' | markdownify }}* {{ '_Tabbed_' | markdownify }}* {{ '_Top_' | markdownify }}* Vertical<br></td></tr>
<tr>
<td>
DockHeaderPresenter</td><td>
Specifies the DockHeaderPresenter object for the specified child. { [DockHeaderPresenter](http://help.syncfusion.com/ug_91/User%20Interface/WPF/Tools/default.htm?turl=Documents%2F31067dockwindowheaderstyle.htm) | markdownify } acts as a Header container for the parent window.</td><td>
DockHeaderPresenter</td><td>
</td></tr>
<tr>
<td>
DockingManager</td><td>
Specifies the DockingManager parent, which holds that child element.</td><td>
DockingManager</td><td>
</td></tr>
<tr>
<td>
DockFill</td><td>
Specifies whether child can be filled in the remaining client area of { [DockingManager](http://help.syncfusion.com/ug_91/User%20Interface/WPF/Tools/default.htm?turl=Documents%2F31095detectwhetherthewindowishostedindockingmanager.htm) | markdownify }.</td><td>
bool</td><td>
* True* False<br></td></tr>
<tr>
<td>
DocumentMDIHeaderStyle</td><td>
Specifies the Document { [MDI Header Style](http://help.syncfusion.com/ug_91/User%20Interface/WPF/Tools/default.htm?turl=Documents%2F31052717documentmdiheaderstyle.htm) | markdownify } for the DockingManager children.</td><td>
Style</td><td>
</td></tr>
<tr>
<td>
DocumentTabControlStyle</td><td>
Specifies the DocumentTabControl style which holds the { [Document tab](http://help.syncfusion.com/ug_91/User%20Interface/WPF/Tools/default.htm?turl=Documents%2F31052715documenttabcontrolstyle.htm) | markdownify } children.</td><td>
Style</td><td>
</td></tr>
<tr>
<td>
DocumentTabItemStyle</td><td>
Specifies the Document TabItem Style.</td><td>
Style</td><td>
</td></tr>
<tr>
<td>
FloatingWindowRect</td><td>
Specifies the Rect bounds for Floatwindow of a child element.</td><td>
Rect</td><td>
</td></tr>
<tr>
<td>
FloatWindowHeight</td><td>
Specifies the height of the Float Window of a child element.</td><td>
double</td><td>
</td></tr>
<tr>
<td>
FloatWindowWidth</td><td>
Specifies the width of the Float Window of a child element.</td><td>
double</td><td>
</td></tr>
<tr>
<td>
Header</td><td>
Specifies the Header for the Children of DockingManager.</td><td>
object</td><td>
</td></tr>
<tr>
<td>
HeaderTemplate</td><td>
Specifies the { [Header Control](http://help.syncfusion.com/ug_91/User%20Interface/WPF/Tools/default.htm?turl=Documents%2F31063customizingheadertemplate.htm) | markdownify } Template for DockingManager.</td><td>
DataTemplate</td><td>
</td></tr>
<tr>
<td>
HostSize</td><td>
Specifies the { [DockedElementTabbedHost Size](http://help.syncfusion.com/ug_91/User%20Interface/WPF/Tools/default.htm?turl=Documents%2F31089getsetdockedelementtabbedhostsize.htm) | markdownify }, which acts as a container for Docked Children.</td><td>
Size</td><td>
</td></tr>
<tr>
<td>
Icon</td><td>
Specifies the icon for Document Child in { [MDI mode](http://help.syncfusion.com/ug_91/User%20Interface/WPF/Tools/default.htm?turl=Documents%2F31098setheadericonformdiwindow.htm) | markdownify }.</td><td>
Brush</td><td>
</td></tr>
<tr>
<td>
IsContextMenuButtonVisible</td><td>
Specifies the visibility of the Contextmenu button for the individual children of DockingManager.</td><td>
bool</td><td>
* True* False<br></td></tr>
<tr>
<td>
IsContextMenuVisible</td><td>
Specifies the visibility of the ContextMenu for the individual children of DockingManager.</td><td>
bool</td><td>
* True* False<br></td></tr>
<tr>
<td>
IsRollupFloatWindow</td><td>
Specifies the { [rollup behavior](http://help.syncfusion.com/ug_91/User%20Interface/WPF/Tools/default.htm?turl=Documents%2F310813rollingthefloatwindowup.htm) | markdownify } for individual Float child in DockingManager.</td><td>
bool</td><td>
* True* False<br></td></tr>
<tr>
<td>
NoHeader</td><td>
Specifies whether to display the headers of Docked children or not.</td><td>
bool</td><td>
* True* False<br></td></tr>
<tr>
<td>
SideInDockedMode</td><td>
Specifies the DockSide while the child is in Docked State with respect to the parent.</td><td>
DockSide</td><td>
* Top* Left* Right* Bottom* Tabbed <br></td></tr>
<tr>
<td>
SideInFloatMode</td><td>
Specifies the DockSide while the child is in Float State with respect to the parent.</td><td>
DockSide</td><td>
* Top* Left* Right* Bottom* Tabbed <br></td></tr>
<tr>
<td>
TargetNameInDockMode</td><td>
Specifies the target of the child element (which needs to be docked), in the Dock State of the child.</td><td>
string</td><td>
</td></tr>
<tr>
<td>
TargetNameInFloatMode</td><td>
Specifies the target of the child that needs to be docked in the Float { [state of the child](http://help.syncfusion.com/ug_91/User%20Interface/WPF/Tools/default.htm?turl=Documents%2F310512layoutthechild.htm) | markdownify }.</td><td>
string</td><td>
</td></tr>
<tr>
<td>
SizetoContentInFloat</td><td>
Specifies whether the FloatWindow needs to be sized to its child content.</td><td>
bool</td><td>
* True* False<br></td></tr>
<tr>
<td>
State</td><td>
Specifies the state of children of the DockingManager.</td><td>
DockState</td><td>
* Dock* Float* Document* AutoHidden* Hidden <br></td></tr>
<tr>
<td>
SideTabItemBackground</td><td>
Gets or sets the value for SideTabItemBackground</td><td>
Brush</td><td>
</td></tr>
<tr>
<td>
SideTabItemForeground</td><td>
Gets or sets the value for SideTabItemForeground</td><td>
Brush</td><td>
</td></tr>
</table>


### Methods

_Methods table_

<table>
<tr>
<th>
Methods</th><th>
Description</th><th>
Reference</th></tr>
<tr>
<td>
ActivateWindow(string name)</td><td>
Used to make a docking child as an ActiveWindow using the name of the child.</td><td>
Interactive Features</td></tr>
<tr>
<td>
DeleteDockState()</td><td>
Used to delete the State Persistence entries in registry.</td><td>
How to Clear StatePersistance Entries?</td></tr>
<tr>
<td>
DeleteDockState(string path)</td><td>
Delete the given Persistence file where DockState is saved.</td><td>
How to Clear StatePersistance Entries?</td></tr>
<tr>
<td>
DeleteInternalIsolatedStorage()</td><td>
Delete the Persistence file stored in Isolated Storage.</td><td>
How to Clear StatePersistance Entries?</td></tr>
<tr>
<td>
LoadDockState()</td><td>
Loads the DockState from the isolated storage. </td><td>
State Persistence in DockingManager</td></tr>
<tr>
<td>
LoadDockState(string path)</td><td>
Loads the Dockstate from the specified file.</td><td>
State Persistence in DockingManager</td></tr>
<tr>
<td>
LoadDockState(BinaryFormatter serializer)</td><td>
Loads the Dockstate from the given BinaryFormatter.</td><td>
State Persistence in DockingManager</td></tr>
<tr>
<td>
LoadDockState(IFormatter formatter,StorageFormat format,string path)</td><td>
Load the DockState from the given filename.</td><td>
State Persistence in DockingManager</td></tr>
<tr>
<td>
LoadDockState(IsolatedStorageFile isofile,string Filename)</td><td>
Loads the Dockstate from given isolated storage filename.</td><td>
State Persistence in DockingManager</td></tr>
<tr>
<td>
LoadDockState(TextReader reader)</td><td>
Loads the DockState from TextReader.</td><td>
State Persistence in DockingManager</td></tr>
<tr>
<td>
LoadDockState(XMLTextReader reader)</td><td>
Loads the Dockstate from XMLTextReader.</td><td>
State Persistence in DockingManager</td></tr>
<tr>
<td>
SetMDILayout(MDILayout layout)</td><td>
Sets the MDILayout for Document child (Cascade, Horizontal, Vertical)</td><td>
Setting MDI Layout</td></tr>
<tr>
<td>
SaveDockState()</td><td>
Saves the DockState of in IsolatedStorage location.</td><td>
State Persistence in DockingManager</td></tr>
<tr>
<td>
SaveDockState(BinaryFormatter serializer)</td><td>
Saves the DockState in the given BinaryFormatter object.</td><td>
State Persistence in DockingManager</td></tr>
<tr>
<td>
SaveDockState(IFormatter formatter,StorageFormat format,string path)</td><td>
Saves the Dockstate in the given formatter with storage format.</td><td>
State Persistence in DockingManager</td></tr>
<tr>
<td>
SaveDockState(IsolatedStorageFile isofile,string Filename)</td><td>
Saves the DockState in the given Isolated storage file name.</td><td>
State Persistence in DockingManager</td></tr>
<tr>
<td>
SaveDockState(TextReader reader)</td><td>
Saves the Dockstate in given TextReader object.</td><td>
State Persistence in DockingManager</td></tr>
<tr>
<td>
SaveDockState(XMLTextReader reader)</td><td>
Saves the Dockstate in given XMLTextReader object.</td><td>
State Persistence in DockingManager</td></tr>
<tr>
<td>
SaveDockState(string path)</td><td>
Saves the DockState in given file path.</td><td>
State Persistence in DockingManager</td></tr>
</table>
### Events

_Events table_

<table>
<tr>
<th>
Events</th><th>
Description</th><th>
Reference</th></tr>
<tr>
<td>
ActiveWindowChanged</td><td>
This event is raised whenever the ActiveWindow property has changed.</td><td>
Interactive Features</td></tr>
<tr>
<td>
AutoHideAnimationStarts</td><td>
This event is raised whenever AutoHide animation is triggered.</td><td>
AutoHide Animation  Start /Stop Events</td></tr>
<tr>
<td>
AutoHideAnimationStops</td><td>
This Event is raised after the AutoHideAnimationStarts event.</td><td>
AutoHide Animation  Start /Stop Events</td></tr>
<tr>
<td>
CloseAllTabs</td><td>
This event is raised whenever CloseAll Document tab menu is clicked.</td><td>
Triggering Actions while closing the TDI / MDI items</td></tr>
<tr>
<td>
CloseButtonClick</td><td>
This Event is raised whenever CloseButton of Document child has been clicked.</td><td>
Triggering Actions while closing the TDI / MDI items</td></tr>
<tr>
<td>
CloseOtherTabs</td><td>
This Event is raised whenever CloseAllButThis menu item is clicked from context menu of Document tab childs.</td><td>
Triggering Actions while closing the TDI / MDI items</td></tr>
<tr>
<td>
ContainerModeChanged</td><td>
This Event is raised whenever ContainerMode is changed.</td><td>
Dealing with States</td></tr>
<tr>
<td>
ContextMenuItemClick</td><td>
This Event is raised whenever Context Menu Item which is available when right click on child headers has been clicked.</td><td>
Default Context Menu</td></tr>
<tr>
<td>
DockStateChanged</td><td>
This event is raised whenever State Attached Property has been changed.</td><td>
How to detecting the closing of a DockingManagerchild?</td></tr>
<tr>
<td>
ShowTabItemContextMenuChanged</td><td>
This event is raised whenever ShowTabItemContextMenu property has been changed.</td><td>
DocumentTabControlStyle</td></tr>
<tr>
<td>
ShowTabListContextMenuChanged</td><td>
This event is raised whenever ShowTabListContextMenu property has been changed.</td><td>
DocumentTabControlStyle</td></tr>
<tr>
<td>
SidePanelBorderThicknessChanged</td><td>
This event is raised whenever SidePanelBorderThickness property has been changed.</td><td>
Border Thickness of Child Elements</td></tr>
<tr>
<td>
SplitterBackgroundChanged</td><td>
This event is raised whenever SplitterBackground property has been changed.</td><td>
How to set splitter background and size</td></tr>
<tr>
<td>
SwitchModeChanged</td><td>
This event is raised whenever SwitchMode property has been changed.</td><td>
Different Keyboard Navigation Modes</td></tr>
<tr>
<td>
TabItemBorderThicknessChanged</td><td>
This event is raised whenever TabItemBorderThickness property has been changed.</td><td>
Border Thickness of Child Elements</td></tr>
<tr>
<td>
TabItemsBorderThicknessSelectedChanged</td><td>
This event is raised whenever TabItemsBorderThicknessSelected property has been changed.</td><td>
Border Thickness of Child Elements</td></tr>
<tr>
<td>
TabPanelBorderThicknessChanged</td><td>
This event is raised whenever TabPanelBorderThicknessChanged has been changed.</td><td>
Border Thickness of Child Elements</td></tr>
<tr>
<td>
TargetNameInDockedModeChanged</td><td>
This event is raised when TargetNameInDockedMode attached property has been changed.</td><td>
Layout of the child</td></tr>
<tr>
<td>
TargetNameInFloatModeChanged</td><td>
This event is raised when TargetNameInFloatMode attached property has been changed.</td><td>
Layout of the child</td></tr>
</table>


