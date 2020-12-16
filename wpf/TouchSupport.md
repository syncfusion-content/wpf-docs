---
layout: post
title: Touch support for Syncfusion WPF controls
description: Learn here about the touch supports for Syncfusion Essential Studio WPF controls and touch Gestures.
platform: WPF
control: General
documentation: ug
---

# Touch Support

## Gesture

Gestures determine whether a finger or stylus has moved over a control. Syncfusion WPF controls support the following touch gestures: Tap, Swipe, Pinch, and Hold.<br/>
This table shows the gesture mappings for each control.

<table>
<tr>
<th>Category</th>
<th>Control</th>
<th>Swipe</th>
<th>Pinch</th>
<th>Tap</th>
<th>Hold</th>
</tr>

<tr>
<td>GRIDS</td>
<td>Cell Grid</td>
<td>-</td>
<td>-</td>
<td>-</td>
<td>-</td>
</tr>

<tr>
<td></td>
<td>Data Grid</td>
<td>Selection, Scrolling and Drag Drop</td>
<td>-</td>
<td>Click and Select</td>
<td>Right-Click</td>
</tr>

<tr>
<td></td>
<td>Tree Grid</td>
<td>Selection, Scrolling and Drag Drop</td>
<td>-</td>
<td>Click and Select</td>
<td>Right-Click</td>
</tr>

<tr>
<td></td>
<td>Property Grid</td>
<td>-</td>
<td>-</td>
<td>Click</td>
<td>-</td>
</tr>

<tr>
<td></td>
<td>Spreadsheet</td>
<td>Scrolling and Resizing</td>
<td>Zoom in & Zoom out</td>
<td>Click and Selection</td>
<td>Right Click</td></tr>

<tr>
<td>DATA VISUALIZATION</td>
<td>Charts</td>
<td>Panning, Scrolling, Annotation resizing, dragging</td>
<td>Zooming</td>
<td>ToolTip, Series selection, Segment selection, Annotation text editing, Annotation selection</td>
<td>-</td>
</tr>

<tr>
<td></td><td>
Sunburst Chart</td>
<td>-</td>
<td>-</td>
<td>Click and Select</td>
<td>-</td>
</tr>

<tr>
<td></td>
<td>Smith Chart</td>
<td>-</td>
<td>-</td>
<td>Click</td>
<td>-</td>
</tr>

<tr>
<td></td>
<td>Kanban</td>
<td>Panning/Scrolling, Dragging</td>
<td>-</td>
<td>Column collapse/expand</td>
<td>Hold to select the card for dragging</td>
</tr>

<tr>
<td></td>
<td>Diagramming</td>
<td>Diagram: Pan/Scroll, MultipleSelect, Drop, Zoom, Connect.<br/>
Stencil: Drag & Drop.<br/>
Node and Annotation: Drag, Resize, Rotate, Connect.<br/>
Connector: Segment editing, Connect.<br/>
Port: Drag, Connect.</td>
<td>Zoom</td>
<td>Select</td>
<td>Context Menu</td>
</tr>

<tr>
<td></td>
<td>Maps</td>
<td>-</td>
<td>Pan</td>
<td>Click and Select</td>
<td>-</td>
</tr>

<tr>
<td></td>
<td>Treemap</td>
<td>-</td>
<td>-</td>
<td>Click</td>
<td>-</td>
</tr>

<tr>
<td></td>
<td>Scheduler</td>
<td>View swiping, Scrolling and Dragging </td>
<td>-</td>
<td>Tap support for Cell selection , Appointment selection and Double tap support to appointment editor.</td>
<td>-</td>
</tr>

<tr>
<td></td>
<td>Linear Gauge</td>
<td>-</td>
<td>-</td>
<td>-</td>
<td>-</td>
</tr>

<tr>
<td></td>
<td>Digital Gauge</td>
<td>-</td>
<td>-</td>
<td>-</td>
<td>-</td>
</tr>

<tr>
<td></td>
<td>Radial Gauge</td>
<td>-</td>
<td>-</td>
<td>-</td>
<td>-</td>
</tr>

<tr>
<td></td>
<td>Bullet Graph</td>
<td>-</td>
<td>-</td>
<td>Click</td>
<td>-</td>
</tr>

<tr>
<td></td>
<td>Gantt</td>
<td>Selection and drag and drop</td>
<td>-</td>
<td>Click and Select</td>
<td>Select</td>
</tr>

<tr>
<td></td>
<td>Range Navigator</td>
<td>Scroll</td>
<td>-</td>
<td>Range selection</td>
<td>-</td>
</tr>

<tr>
<td></td>
<td>Sparkline</td>
<td>-</td>
<td>-</td>
<td>Click</td>
<td>-</td>
</tr>

<tr>
<td></td>
<td>Surface Chart</td>
<td>-</td>
<td>-</td>
<td>Click</td>
<td>-</td>
</tr>

<tr>
<td></td>
<td>Barcode</td>
<td>NA</td>
<td>NA</td>
<td>NA</td>
<td>NA</td>
</tr>

<tr>
<td></td>
<td>Heat Map</td>
<td>Pan/Scroll</td>
<td>-</td>
<td>-</td>
<td>-</td>
</tr>

<tr>
<td>DATA SCIENCE</td>
<td>Predictive Analytics</td>
<td>NA</td>
<td>NA</td>
<td>NA</td>
<td>NA</td>
</tr>

<tr>
<td>LAYOUT</td>
<td>Ribbon</td>
<td>Swipe</td>
<td>-</td>
<td>Click</td>
<td>Context Menu</td>
</tr>

<tr>
<td></td>
<td>Docking Manager</td>
<td>Swipe to rearrange Tab order in Tabbed and Document state windows.</td>
<td>-</td>
<td>Tap to select the active window of DockingManager.<br/>
Double tab to float the active window</td>
<td>Hold any docking window header Context menu opened</td>
</tr>

<tr>
<td></td>
<td>Document Container</td>
<td>Swipe to rearrange TDI mode Items</td>
<td>-</td>
<td>Tap to select the active document window</td>
<td>Hold any document window header Context menu opened</td>
</tr>

<tr>
<td></td>
<td>Tile View</td>
<td>Swipe to reorder the tile items</td>
<td>-</td>
<td>Tap to select the item</td>
<td>-</td>
</tr>

<tr>
<td></td>
<td>Carousel</td>
<td>To view the next or previous items</td>
<td>-</td>
<td>Click and select the item</td>
<td>-</td>
</tr>

<tr>
<td></td>
<td>Tab Splitter</td>
<td>Swipe to move the splitter</td>
<td>-</td>
<td>Tap to select the item</td>
<td>Hold on TabBarSplitterItem to open the context menu</td>
</tr>

<tr>
<td></td>
<td>Chromeless Window</td>
<td>Move</td>
<td>-</td>
<td>Select</td>
<td>-</td>
</tr>

<tr>
<td></td>
<td>Card View</td>
<td>-</td>
<td>-</td>
<td>Click and Select</td>
<td>-</td>
</tr>

<tr>
<td></td>
<td>Accordion</td>
<td>-</td>
<td>-</td>
<td>Tap to select the accordion item and expand or collapse item</td>
<td>-</td>
</tr>

<tr>
<td></td>
<td>Grid Splitter</td>
<td>Swipe to move the splitter horizontally or vertically</td>
<td>-</td>
<td>-</td>
<td>-</td>
</tr>

<tr>
<td>EDITORS</td>
<td>Autocomplete</td>
<td>Scroll</td>
<td>-</td>
<td>Select</td>
<td>-</td>
</tr>

<tr>
<td></td>
<td>Textbox</td>
<td>Move</td>
<td>-</td>
<td>double tab to select the word</td>
<td>Hold to open the default context menu</td>
</tr>

<tr>
<td></td>
<td>Currency Textbox</td>
<td>Move</td>
<td>-</td>
<td>double tab to select the word</td>
<td>Hold to open the default context menu</td>
</tr>

<tr>
<td></td>
<td>Double Textbox</td>
<td>Move</td>
<td>-</td>
<td>double tab to select the word</td>
<td>Hold to open the default context menu</td>
</tr>

<tr>
<td></td>
<td>Integer Textbox</td>
<td>Move</td>
<td>-</td>
<td>double tab to select the word</td>
<td>Hold to open the default context menu</td>
</tr>

<tr>
<td></td>
<td>Date Picker</td>
<td>Swipe to change the dates</td>
<td>-</td>
<td>click to select the date</td>
<td>-</td>
</tr>

<tr>
<td></td>
<td>Time Picker</td>
<td>Swipe to change the dates</td>
<td>-</td>
<td>click to select the date</td>
<td>-</td>
</tr>

<tr>
<td></td>
<td>Date Time Editor</td>
<td>Swipe</td>
<td>-</td>
<td>Select</td>
<td>-</td>
</tr>

<tr>
<td></td>
<td>Button Adv</td>
<td>-</td>
<td>-</td>
<td>Click</td>
<td>-</td>
</tr>

<tr>
<td></td>
<td>Masked Textbox</td>
<td>-</td>
<td>-</td>
<td>Click and Select</td>
<td>Context Menu</td>
</tr>

<tr>
<td></td>
<td>Percent Textbox</td>
<td>-</td>
<td>-</td>
<td>double tab to select the word</td>
<td>Hold to open the default context menu</td>
</tr>

<tr>
<td></td>
<td>RichTextBox</td>
<td>Swipe left/right to scroll the pages horizontally.<br/>
Swipe up/down to scroll the pages vertically</td>
<td>Zoom in/out</td>
<td>Click and select</td>
<td>-</td>
</tr>

<tr>
<td></td>
<td>Timespan Editor</td>
<td>-</td>
<td>-</td>
<td>-</td>
<td>-</td>
</tr>

<tr>
<td></td>
<td>Numeric Updown</td>
<td>Selection</td>
<td>-</td>
<td>Tap up down button to change the values</td>
<td>Hold to open the default context menu</td>
</tr>

<tr>
<td></td>
<td>Domain Updown</td>
<td>-</td>
<td>-</td>
<td>Tap up down button to change the values</td>
<td>-</td>
</tr>

<tr>
<td></td>
<td>Combobox</td>
<td>Swipe</td>
<td>-</td>
<td>Click and Select</td>
<td>-</td>
</tr>

<tr>
<td></td>
<td>Range Slider</td>
<td>Swipe horizontally or vertically to change minimum and maximum range values</td>
<td>-</td>
<td>Tap to increase or decrease the values based on step value.</td>
<td>-<</td>
</tr>

<tr>
<td></td>
<td>Radial Slider</td>
<td>Swipe to change change the slider positions</td>
<td>-</td>
<td>Tap to update the selected value</td>
<td>-</td>
</tr>

<tr>
<td></td>
<td>Color Picker</td>
<td>-</td>
<td>-</td>
<td>Click</td>
<td>-</td>
</tr>

<tr>
<td></td>
<td>Color Palette</td>
<td>Swipe</td>
<td>-</td>
<td>Select</td>
<td>-</td>
</tr>

<tr>
<td></td>
<td>Color Picker Palette</td>
<td>Swipe</td>
<td>-</td>
<td>Click</td>
<td>-</td>
</tr>

<tr>
<td></td>
<td>Calculator</td>
<td>-</td>
<td>-</td>
<td>Tab to enter the values in text area</td>
<td>-</td>
</tr>

<tr>
<td></td>
<td>Rating</td>
<td>Swipe to change the Rating values</td>
<td>-</td>
<td>Tap to increase or decrease the rating values</td>
<td>-</td>
</tr>

<tr>
<td></td>
<td>Checked Listbox</td>
<td>Scrolling</td>
<td>-</td>
<td>Tab to select the item</td>
<td>-</td>
</tr>

<tr>
<td></td>
<td>Dropdown Button</td>
<td>-</td>
<td>-</td>
<td>Dropdown open</td>
<td>-</td>
</tr>

<tr>
<td></td>
<td>Split Button</td>
<td>Click</td>
<td>-</td>
<td>Select</td>
<td>-</td>
</tr>

<tr>
<td></td>
<td>Multicolumn Drop-Down</td>
<td>Scrolling</td>
<td>-</td>
<td>Click and Select</td>
<td>Right Click</td>
</tr>

<tr>
<td></td>
<td>Calendar</td>
<td>Swipe to change the month view</td>
<td>-</td>
<td>Tap to select the date</td>
<td>-</td>
</tr>

<tr>
<td></td>
<td>Syntax Editor</td>
<td>-</td>
<td>-</td>
<td>tap to set the cursor index.<br/>
double tab to select the current word of cursor placed index </td>
<td>Hold to open Context menu</td>
</tr>

<tr>
<td>NAVIGATION</td>
<td>Tree View</td>
<td>Swipe</td>
<td>-</td>
<td>Click</td>
<td>Context Menu, Drag drop</td>
</tr>

<tr>
<td></td>
<td>Menu</td>
<td>-</td>
<td>-</td>
<td>Click</td>
<td>-</td>
</tr>

<tr>
<td></td>
<td>Toolbar</td>
<td>-</td>
<td>-</td>
<td>Click</td>
<td>ToolTip</td>
</tr>

<tr>
<td></td>
<td>Hierarchical Navigator</td>
<td>-</td>
<td>-</td>
<td>Tab to navigate the next item</td>
<td>-</td>
</tr>

<tr>
<td></td>
<td>Groupbar</td>
<td>-</td>
<td>-</td>
<td>Tap to select the groupbar item.<br/>
Expand or collapse the item.</td>
<td>Hold to open Context menu</td>
</tr>

<tr>
<td></td>
<td>Tabs</td>
<td>Change the Tab index positions</td>
<td>-</td>
<td>Tap to select the item</td>
<td>Hold to open the context menus</td>
</tr>

<tr>
<td></td>
<td>Tab Navigation</td>
<td>Scroll</td>
<td>-</td>
<td>Tap to navigate the next or previous view</td>
<td>-</td>
</tr>

<tr>
<td></td>
<td>Taskbar</td>
<td>-</td>
<td>-</td>
<td>Tap to expand or collapse the task bar item</td>
<td>-</td>
</tr>

<tr>
<td></td>
<td>Radial Menu</td>
<td>Swipe to rotate the radial menu items</td>
<td>-</td>
<td>Tap to expand or collapse the radial menu item</td>
<td>Indicates the selected item</td>
</tr>

<tr>
<td></td>
<td>Tree Navigator</td>
<td>-</td>
<td>-</td>
<td>Tab to navigate the item</td>
<td>-</td>
</tr>

<tr>
<td></td>
<td>Navigation Drawer</td>
<td>To open the primary or secondary drawers</td>
<td>-</td>
<td>-</td>
<td>-</td>
</tr>

<tr>
<td>NOTIFICATION</td>
<td>Busy Indicator</td>
<td>-</td>
<td>-</td>
<td>-</td>
<td>-</td>
</tr>

<tr>
<td></td>
<td>Notify Icon</td>
<td>-</td>
<td>-</td>
<td>Tap to close the notify icon popup</td>
<td>-</td>
</tr>

<tr>
<td></td>
<td>Hub Tile</td>
<td>-</td>
<td>-</td>
<td>Tap to perform the scale animation based on tile pressed direction</td>
<td>-</td>
</tr>

<tr>
<td>
FILE FORMAT LIBRARY</td>
<td>Excel</td>
<td>NA</td>
<td>NA</td>
<td>NA</td>
<td>NA</td>
</tr>

<tr>
<td></td>
<td>PDF</td>
<td>NA</td>
<td>NA</td>
<td>NA</td>
<td>NA</td>
</tr>

<tr>
<td></td>
<td>Word</td>
<td>NA(Non UI Component)</td>
<td>NA(Non UI Component)</td>
<td>NA(Non UI Component)</td>
<td>NA(Non UI Component)</td>
</tr>

<tr>
<td></td>
<td>PDF Viewer</td>
<td>Scroll</td>
<td>Zoom</td>
<td>Button click</td>
<td>-</td>
</tr>

<tr>
<td></td>
<td>PowerPoint</td>
<td>NA</td>
<td>NA</td>
<td>NA</td>
<td>NA</td>
</tr>

<tr>
<td>REPORTING</td>
<td>Report Viewer</td>
<td>Scrolling</td>
<td>-</td>
<td>Click and Select</td>
<td>-</td>
</tr>

<tr>
<td></td>
<td>Report Writer</td>
<td>NA (Non UI component)</td>
<td>NA (Non UI component)</td>
<td>NA (Non UI component)</td>
<td>NA (Non UI component)</td>
</tr>

<tr>
<td></td>
<td>Report Designer</td>
<td>Scrolling, Resizing</td>
<td>-</td>
<td>Click and Select</td>
<td>Right click</td>
</tr>

<tr>
<td>BUSINESS INTELLIGENCE</td>
<td>Olap Grid</td>
<td>Drag and drop, expand and collapse and resizing</td>
<td>-</td>
<td>Click, hyperlink and selection</td>
<td>Right click and tooltip</td>
</tr>

<tr>
<td></td>
<td>Olap Chart</td>
<td>Drag and drop, expand and collapse and resizing</td>
<td>Zooming and panning</td>
<td>-</td>
<td>Right click, tooltip and context menu</td>
</tr>

<tr>
<td></td>
<td>Olap Client</td>
<td>Drag and drop, expand and collapse and resizing</td>
<td>Zooming and panning</td>
<td>Click, hyperlink and selection</td>
<td>Right click, tooltip and context menu</td>
</tr>

<tr>
<td></td>
<td>Olap Gauge</td>
<td>-</td>
<td>-</td>
<td>-</td>
<td>Tooltip</td>
</tr>

<tr>
<td></td>
<td>Pivot Grid</td>
<td>Drag and drop, expand and collapse and resizing</td>
<td>-</td>
<td>Click, hyperlink and selection</td>
<td>Right click, context menu and tooltip</td>
</tr>

<tr>
<td>MISCELLANEOUS</td>
<td>SpellChecker</td>
<td>-</td>
<td>-</td>
<td>Tab to perform the spell check operations in spell check dialog window</td>
<td>Hold to open the suggestion context menu</td>
</tr>

<tr>
<td></td>
<td>Wizard</td>
<td>-</td>
<td>-</td>
<td>Click</td>
<td>-</td>
</tr>

<tr>
<td></td>
<td>Calculate</td>
<td>NA (Non UI component)</td>
<td>NA (Non UI component)</td>
<td>NA (Non UI component)</td>
<td>NA (Non UI component)</td>
</tr>

<tr>
<td></td>
<td>Diagram(classic)</td>
<td>Diagram: Pan/Scroll, MultipleSelect, Drop, Zoom, Connect.<br/>
Stencil: Drag & Drop.<br/>
Node and Annotation: Drag, Resize, Rotate, Connect<br/>
Connector: Segment editing, Connect<br/>
Port: Drag, Connect</td>
<td>Zoom</td>
<td>Select</td>
<td>Context Menu</td>
</tr>

<tr>
<td></td>
<td>GridTreeControl</td>
<td>Scrolling, Drag and drop and Resizing</td>
<td>-</td>
<td>Click and Selection</td>
<td>Right click</td>
</tr>

<tr>
<td></td>
<td>Spreadsheet(classic)</td>
<td>-</td>
<td>-</td>
<td>-</td>
<td>-</td>
</tr>

<tr>
<td></td>
<td>GridDataControl</td>
<td>Scrolling, Drag and drop and Resizing</td>
<td>-</td>
<td>Click and Selection</td>
<td>Right click</td>
</tr>

<tr>
<td></td>
<td>Chart(classic)</td>
<td>Panning, Scrolling, Dragging</td>
<td>Zooming</td>
<td>ToolTip, Series selection, Segment selection</td>
<td>-</td>
</tr>

<tr>
<td></td>
<td>TabControlExt</td>
<td>Swipe to move the tabitem</td>
<td>-</td>
<td>Tab to change the SelectedItem</td>
<td>Hold to open TabItemExt ContextMenu</td>
</tr>

<tr>
<td></td>
<td>SfMaskEdit</td>
<td>Select</td>
<td>-</td>
<td>Tap to place the cursor</td>
<td>Hold to open the context menu</td>
</tr>

<tr>
<td></td>
<td>ColorEdit</td>
<td>Select the color</td>
<td>-</td>
<td>Tap to select the color, Tap on ColorCode Editor box to place the cursor</td>
<td>Hold on ColorCode Editor to open the ContextMenu</td>
</tr>

<tr>
<td></td>
<td>SfCircularGauge</td>
<td>-</td>
<td>-</td>
<td>-</td>
<td>-</td>
</tr>

<tr>
<td></td>
<td>PinnableListBox</td>
<td>-</td>
<td>-</td>
<td>Click and selection</td>
<td>Right click</td>
</tr>
</table>