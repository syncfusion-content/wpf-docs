---
layout: post
title: Touch support for Syncfusion WPF controls
description: Touch Support Overview
platform: WPF
control: General
documentation: ug
---

# Touch Support

## Gesture

Gestures determine whether a finger or stylus has moved over a control. Syncfusion WPF controls support the following touch gestures: Tap, Swipe, Pinch, and Hold.<br/><br/>
This table shows the gesture mappings for each control.

<table>
<tr>
<th>
Category<br/><br/></th><th>
Control<br/><br/></th><th>
Swipe<br/><br/></th><th>
Pinch<br/><br/></th><th>
Tap<br/><br/></th><th>
Hold<br/><br/></th></tr>
<tr>
<td>
GRIDS<br/><br/></td><td>
Cell Grid<br/><br/></td><td>
-<br/><br/></td><td>
-<br/><br/></td><td>
-<br/><br/></td><td>
-<br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
Data Grid<br/><br/></td><td>
Selection, Scrolling and Drag Drop<br/><br/></td><td>
-<br/><br/></td><td>
Click and Select<br/><br/></td><td>
Right-Click<br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
Tree Grid<br/><br/></td><td>
Selection, Scrolling and Drag Drop<br/><br/></td><td>
-<br/><br/></td><td>
Click and Select<br/><br/></td><td>
Right-Click<br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
Property Grid<br/><br/></td><td>
-<br/><br/></td><td>
-<br/><br/></td><td>
Click<br/><br/></td><td>
-<br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
Spreadsheet<br/><br/></td><td>
Scrolling and Resizing<br/><br/></td><td>
Zoom in & Zoom out<br/><br/></td><td>
Click and Selection<br/><br/></td><td>
Right Click<br/><br/></td></tr>
<tr>
<td>
DATA VISUALIZATION<br/><br/></td><td>
Charts<br/><br/></td><td>
Panning, Scrolling, Annotation resizing, dragging<br/><br/></td><td>
Zooming<br/><br/></td><td>
ToolTip, Series selection, Segment selection, Annotation text editing, Annotation selection<br/><br/></td><td>
-<br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
Sunburst Chart<br/><br/></td><td>
-<br/><br/></td><td>
-<br/><br/></td><td>
Click and Select<br/><br/></td><td>
-<br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
Smith Chart<br/><br/></td><td>
-<br/><br/></td><td>
-<br/><br/></td><td>
Click<br/><br/></td><td>
-<br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
Kanban<br/><br/></td><td>
Panning/Scrolling, Dragging<br/><br/></td><td>
-<br/><br/></td><td>
Column collapse/expand<br/><br/></td><td>
Hold to select the card for dragging<br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
Diagramming<br/><br/></td><td>
Diagram: Pan/Scroll, MultipleSelect, Drop, Zoom, Connect

Stencil: Drag & Drop

Node and Annotation: Drag, Resize, Rotate, Connect

Connector: Segment editing, Connect

Port: Drag, Connect<br/><br/></td><td>
Zoom<br/><br/></td><td>
Select<br/><br/></td><td>
Context Menu<br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
Maps<br/><br/></td><td>
-<br/><br/></td><td>
Pan<br/><br/></td><td>
Click and Select<br/><br/></td><td>
-<br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
Treemap<br/><br/></td><td>
-<br/><br/></td><td>
-<br/><br/></td><td>
Click<br/><br/></td><td>
-<br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
Scheduler<br/><br/></td><td>
View swiping (By enabling EnableTouch property to true)<br/><br/></td><td>
-<br/><br/></td><td>
Tap support for Cell selection , appointment selection , display context menu .

Double tap support to appointment editor. <br/><br/></td><td>
-<br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
Linear Gauge<br/><br/></td><td>
-<br/><br/></td><td>
-<br/><br/></td><td>
-<br/><br/></td><td>
-<br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
Digital Gauge<br/><br/></td><td>
-<br/><br/></td><td>
-<br/><br/></td><td>
-<br/><br/></td><td>
-<br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
Radial Gauge<br/><br/></td><td>
-<br/><br/></td><td>
-<br/><br/></td><td>
-<br/><br/></td><td>
-<br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
Bullet Graph<br/><br/></td><td>
-<br/><br/></td><td>
-<br/><br/></td><td>
Click<br/><br/></td><td>
-<br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
Gantt<br/><br/></td><td>
Selection and drag and drop<br/><br/></td><td>
-<br/><br/></td><td>
Click and Select<br/><br/></td><td>
Select<br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
Range Navigator<br/><br/></td><td>
Scroll<br/><br/></td><td>
-<br/><br/></td><td>
Range selection<br/><br/></td><td>
-<br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
Sparkline<br/><br/></td><td>
-<br/><br/></td><td>
-<br/><br/></td><td>
Click<br/><br/></td><td>
-<br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
Surface Chart<br/><br/></td><td>
-<br/><br/></td><td>
-<br/><br/></td><td>
Click<br/><br/></td><td>
-<br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
Barcode<br/><br/></td><td>
NA<br/><br/></td><td>
NA<br/><br/></td><td>
NA<br/><br/></td><td>
NA<br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
Heat Map<br/><br/></td><td>
Pan/Scroll<br/><br/></td><td>
-<br/><br/></td><td>
-<br/><br/></td><td>
-<br/><br/></td></tr>
<tr>
<td>
DATA SCIENCE<br/><br/></td><td>
Predictive Analytics<br/><br/></td><td>
NA<br/><br/></td><td>
NA<br/><br/></td><td>
NA<br/><br/></td><td>
NA<br/><br/></td></tr>
<tr>
<td>
LAYOUT<br/><br/></td><td>
Ribbon<br/><br/></td><td>
Swipe<br/><br/></td><td>
-<br/><br/></td><td>
Click<br/><br/></td><td>
Context Menu<br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
Docking Manager<br/><br/></td><td>
Swipe to rearrange Tab order in Tabbed and Document state windows. <br/><br/></td><td>
-<br/><br/></td><td>
Tap to select the active window of DockingManager

Double tab to float the active window <br/><br/></td><td>
Hold any docking window header Context menu opened <br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
Document Container<br/><br/></td><td>
Swipe to rearrange TDI mode Items <br/><br/></td><td>
-<br/><br/></td><td>
Tap to select the active document window<br/><br/></td><td>
Hold any document window header Context menu opened <br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
Tile View<br/><br/></td><td>
Swipe to reorder the tile items <br/><br/></td><td>
-<br/><br/></td><td>
Tap to select the item <br/><br/></td><td>
-<br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
Carousel<br/><br/></td><td>
To view the next or previous items<br/><br/></td><td>
-<br/><br/></td><td>
Click and select the item <br/><br/></td><td>
-<br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
Tab Splitter<br/><br/></td><td>
Swipe to move the splitter<br/><br/></td><td>
-<br/><br/></td><td>
Tap to select the item<br/><br/></td><td>
Hold on TabBarSplitterItem to open the context menu  <br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
Chromeless Window<br/><br/></td><td>
Move<br/><br/></td><td>
-<br/><br/></td><td>
Select<br/><br/></td><td>
-<br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
Card View<br/><br/></td><td>
-<br/><br/></td><td>
-<br/><br/></td><td>
Click and Select<br/><br/></td><td>
-<br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
Accordion<br/><br/></td><td>
-<br/><br/></td><td>
-<br/><br/></td><td>
Tap to select the accordion item and expand or collapse item<br/><br/></td><td>
-<br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
Grid Splitter<br/><br/></td><td>
Swipe to move the splitter horizontally or vertically <br/><br/></td><td>
-<br/><br/></td><td>
-<br/><br/></td><td>
-<br/><br/></td></tr>
<tr>
<td>
EDITORS<br/><br/></td><td>
Autocomplete<br/><br/></td><td>
Scroll<br/><br/></td><td>
-<br/><br/></td><td>
Select<br/><br/></td><td>
-<br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
Textbox<br/><br/></td><td>
Move<br/><br/></td><td>
-<br/><br/></td><td>
double tab to select the word <br/><br/></td><td>
Hold to open the default context menu<br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
Currency Textbox<br/><br/></td><td>
Move<br/><br/></td><td>
-<br/><br/></td><td>
double tab to select the word <br/><br/></td><td>
Hold to open the default context menu<br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
Double Textbox<br/><br/></td><td>
Move<br/><br/></td><td>
-<br/><br/></td><td>
double tab to select the word <br/><br/></td><td>
Hold to open the default context menu<br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
Integer Textbox<br/><br/></td><td>
Move<br/><br/></td><td>
-<br/><br/></td><td>
double tab to select the word <br/><br/></td><td>
Hold to open the default context menu<br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
Date Picker<br/><br/></td><td>
Swipe to change the dates<br/><br/></td><td>
-<br/><br/></td><td>
click to select the date<br/><br/></td><td>
-<br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
Time Picker<br/><br/></td><td>
Swipe to change the dates<br/><br/></td><td>
-<br/><br/></td><td>
click to select the date<br/><br/></td><td>
-<br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
Date Time Editor<br/><br/></td><td>
Swipe<br/><br/></td><td>
-<br/><br/></td><td>
Select<br/><br/></td><td>
-<br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
Button Adv<br/><br/></td><td>
-<br/><br/></td><td>
-<br/><br/></td><td>
Click<br/><br/></td><td>
-<br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
Masked Textbox<br/><br/></td><td>
-<br/><br/></td><td>
-<br/><br/></td><td>
Click and Select<br/><br/></td><td>
Context Menu<br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
Percent Textbox<br/><br/></td><td>
-<br/><br/></td><td>
-<br/><br/></td><td>
double tab to select the word <br/><br/></td><td>
Hold to open the default context menu<br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
RichTextBox<br/><br/></td><td>
Swipe left/right to scroll the pages horizontally

Swipe up/down to scroll the pages vertically<br/><br/></td><td>
Zoom in/out<br/><br/></td><td>
Click and select<br/><br/></td><td>
-<br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
Timespan Editor<br/><br/></td><td>
-<br/><br/></td><td>
-<br/><br/></td><td>
-<br/><br/></td><td>
-<br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
Numeric Updown<br/><br/></td><td>
Selection<br/><br/></td><td>
-<br/><br/></td><td>
Tap up down button to change the values.<br/><br/></td><td>
Hold to open the default context menu<br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
Domain Updown<br/><br/></td><td>
-<br/><br/></td><td>
-<br/><br/></td><td>
Tap up down button to change the values.<br/><br/></td><td>
-<br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
Combobox<br/><br/></td><td>
Swipe<br/><br/></td><td>
-<br/><br/></td><td>
Click and Select<br/><br/></td><td>
-<br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
Range Slider<br/><br/></td><td>
Swipe horizontally or vertically to change minimum and maximum range values <br/><br/></td><td>
-<br/><br/></td><td>
Tap to increase or decrease the values based on step value. <br/><br/></td><td>
-<br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
Radial Slider<br/><br/></td><td>
Swipe to change change the slider positions <br/><br/></td><td>
-<br/><br/></td><td>
Tap to update the selected value<br/><br/></td><td>
-<br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
Color Picker<br/><br/></td><td>
-<br/><br/></td><td>
-<br/><br/></td><td>
Click<br/><br/></td><td>
-<br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
Color Palette<br/><br/></td><td>
Swipe<br/><br/></td><td>
-<br/><br/></td><td>
Select<br/><br/></td><td>
-<br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
Color Picker Palette<br/><br/></td><td>
Swipe<br/><br/></td><td>
-<br/><br/></td><td>
Click<br/><br/></td><td>
-<br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
Calculator<br/><br/></td><td>
-<br/><br/></td><td>
-<br/><br/></td><td>
Tab to enter the values in text area<br/><br/></td><td>
-<br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
Rating<br/><br/></td><td>
Swipe to change the Rating values.<br/><br/></td><td>
-<br/><br/></td><td>
Tap to increase or decrease the rating values.<br/><br/></td><td>
-<br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
Checked Listbox<br/><br/></td><td>
Scrolling<br/><br/></td><td>
-<br/><br/></td><td>
Tab to select the item<br/><br/></td><td>
-<br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
Dropdown Button<br/><br/></td><td>
-<br/><br/></td><td>
-<br/><br/></td><td>
Dropdown open<br/><br/></td><td>
-<br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
Split Button<br/><br/></td><td>
Click<br/><br/></td><td>
-<br/><br/></td><td>
Select<br/><br/></td><td>
-<br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
Multicolumn Drop-Down
<br/><br/></td><td>
Scrolling<br/><br/></td><td>
-<br/><br/></td><td>
Click and Select<br/><br/></td><td>
Right Click<br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
Calendar<br/><br/></td><td>
Swipe to change the month view<br/><br/></td><td>
-<br/><br/></td><td>
Tap to select the date<br/><br/></td><td>
-<br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
Syntax Editor<br/><br/></td><td>
-<br/><br/></td><td>
-<br/><br/></td><td>
tap to set the cursor index

double tab to select the current word of cursor placed index <br/><br/></td><td>
Hold to open Context menu<br/><br/></td></tr>
<tr>
<td>
NAVIGATION<br/><br/></td><td>
Tree View<br/><br/></td><td>
Swipe<br/><br/></td><td>
-<br/><br/></td><td>
Click<br/><br/></td><td>
Context Menu, Drag drop<br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
Menu<br/><br/></td><td>
-<br/><br/></td><td>
-<br/><br/></td><td>
Click<br/><br/></td><td>
-<br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
Toolbar<br/><br/></td><td>
-<br/><br/></td><td>
-<br/><br/></td><td>
Click<br/><br/></td><td>
ToolTip<br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
Hierarchical Navigator<br/><br/></td><td>
-<br/><br/></td><td>
-<br/><br/></td><td>
Tab to navigate the next item<br/><br/></td><td>
-<br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
Groupbar<br/><br/></td><td>
-<br/><br/></td><td>
-<br/><br/></td><td>
Tap to select the groupbar item. 

Expand or collapse the item<br/><br/></td><td>
Hold to open Context menu<br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
Tabs<br/><br/></td><td>
Change the Tab index positions<br/><br/></td><td>
-<br/><br/></td><td>
Tap to select the item<br/><br/></td><td>
Hold to open the context menus.<br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
Tab Navigation<br/><br/></td><td>
Scroll<br/><br/></td><td>
-<br/><br/></td><td>
Tap to navigate the next or previous view<br/><br/></td><td>
-<br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
Taskbar<br/><br/></td><td>
-<br/><br/></td><td>
-<br/><br/></td><td>
Tap to expand or collapse the task bar item<br/><br/></td><td>
-<br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
Radial Menu<br/><br/></td><td>
Swipe to rotate the radial menu items<br/><br/></td><td>
-<br/><br/></td><td>
Tap to expand or collapse the radial menu item<br/><br/></td><td>
Indicates the selected item.<br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
Tree Navigator<br/><br/></td><td>
-<br/><br/></td><td>
-<br/><br/></td><td>
Tab to navigate the item<br/><br/></td><td>
<br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
Navigation Drawer<br/><br/></td><td>
To open the primary or secondary drawers.<br/><br/></td><td>
-<br/><br/></td><td>
-<br/><br/></td><td>
-<br/><br/></td></tr>
<tr>
<td>
NOTIFICATION<br/><br/></td><td>
Busy Indicator<br/><br/></td><td>
-<br/><br/></td><td>
-<br/><br/></td><td>
-<br/><br/></td><td>
-<br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
Notify Icon<br/><br/></td><td>
-<br/><br/></td><td>
-<br/><br/></td><td>
Tap to close the notify icon popup<br/><br/></td><td>
-<br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
Hub Tile<br/><br/></td><td>
-<br/><br/></td><td>
-<br/><br/></td><td>
Tap to perform the scale animation based on tile pressed direction. <br/><br/></td><td>
-<br/><br/></td></tr>
<tr>
<td>
FILE FORMAT LIBRARY<br/><br/></td><td>
Excel<br/><br/></td><td>
NA<br/><br/></td><td>
NA<br/><br/></td><td>
NA<br/><br/></td><td>
NA<br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
PDF<br/><br/></td><td>
NA<br/><br/></td><td>
NA<br/><br/></td><td>
NA<br/><br/></td><td>
NA<br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
Word<br/><br/></td><td>
NA(Non UI Component)<br/><br/></td><td>
NA(Non UI Component)<br/><br/></td><td>
NA(Non UI Component)<br/><br/></td><td>
NA(Non UI Component)<br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
PDF Viewer<br/><br/></td><td>
Scroll<br/><br/></td><td>
Zoom<br/><br/></td><td>
Button click<br/><br/></td><td>
-<br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
PowerPoint<br/><br/></td><td>
NA<br/><br/></td><td>
NA<br/><br/></td><td>
NA<br/><br/></td><td>
NA<br/><br/></td></tr>
<tr>
<td>
REPORTING<br/><br/></td><td>
Report Viewer<br/><br/></td><td>
Scrolling<br/><br/></td><td>
-<br/><br/></td><td>
Click and Select<br/><br/></td><td>
-<br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
Report Writer<br/><br/></td><td>
NA (Non UI component)<br/><br/></td><td>
NA (Non UI component)<br/><br/></td><td>
NA (Non UI component)<br/><br/></td><td>
NA (Non UI component)<br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
Report Designer<br/><br/></td><td>
Scrolling, Resizing <br/><br/></td><td>
-<br/><br/></td><td>
Click and Select<br/><br/></td><td>
Right click<br/><br/></td></tr>
<tr>
<td>
BUSINESS INTELLIGENCE<br/><br/></td><td>
Olap Grid<br/><br/></td><td>
Drag and drop, expand and collapse and resizing<br/><br/></td><td>
-<br/><br/></td><td>
Click, hyperlink and selection<br/><br/></td><td>
Right click and tooltip<br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
Olap Chart<br/><br/></td><td>
Drag and drop, expand and collapse and resizing<br/><br/></td><td>
Zooming and panning<br/><br/></td><td>
-<br/><br/></td><td>
Right click, tooltip and context menu<br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
Olap Client<br/><br/></td><td>
Drag and drop, expand and collapse and resizing<br/><br/></td><td>
Zooming and panning<br/><br/></td><td>
Click, hyperlink and selection<br/><br/></td><td>
Right click, tooltip and context menu<br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
Olap Gauge<br/><br/></td><td>
-<br/><br/></td><td>
-<br/><br/></td><td>
-<br/><br/></td><td>
Tooltip<br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
Pivot Grid<br/><br/></td><td>
Drag and drop, expand and collapse and resizing<br/><br/></td><td>
-<br/><br/></td><td>
Click, hyperlink and selection<br/><br/></td><td>
Right click, context menu and tooltip<br/><br/></td></tr>
<tr>
<td>
MISCELLANEOUS<br/><br/></td><td>
SpellChecker<br/><br/></td><td>
-<br/><br/></td><td>
-<br/><br/></td><td>
Tab to perform the spell check operations in spell check dialog window<br/><br/></td><td>
Hold to open the suggestion context menu<br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
Wizard<br/><br/></td><td>
-<br/><br/></td><td>
-<br/><br/></td><td>
Click<br/><br/></td><td>
-<br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
Calculate<br/><br/></td><td>
NA (Non UI component)<br/><br/></td><td>
NA (Non UI component)<br/><br/></td><td>
NA (Non UI component)<br/><br/></td><td>
NA (Non UI component)<br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
Diagram(classic)<br/><br/></td><td>
Diagram: Pan/Scroll, MultipleSelect, Drop, Zoom, Connect

Stencil: Drag & Drop

Node and Annotation: Drag, Resize, Rotate, Connect

Connector: Segment editing, Connect

Port: Drag, Connect<br/><br/></td><td>
Zoom<br/><br/></td><td>
Select<br/><br/></td><td>
Context Menu<br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
GridTreeControl<br/><br/></td><td>
Scrolling, Drag and drop and Resizing<br/><br/></td><td>
-<br/><br/></td><td>
Click and Selection<br/><br/></td><td>
Right click<br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
Spreadsheet(classic)<br/><br/></td><td>
-<br/><br/></td><td>
-<br/><br/></td><td>
-<br/><br/></td><td>
-<br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
GridDataControl<br/><br/></td><td>
Scrolling, Drag and drop and Resizing<br/><br/></td><td>
-<br/><br/></td><td>
Click and Selection<br/><br/></td><td>
Right click<br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
Chart(classic)<br/><br/></td><td>
Panning, Scrolling, Dragging<br/><br/></td><td>
Zooming<br/><br/></td><td>
ToolTip, Series selection, Segment selection<br/><br/></td><td>
-<br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
TabControlExt<br/><br/></td><td>
Swipe to move the tabitem<br/><br/></td><td>
-<br/><br/></td><td>
Tab to change the SelectedItem<br/><br/></td><td>
Hold to open TabItemExt ContextMenu<br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
SfMaskEdit<br/><br/></td><td>
Select<br/><br/></td><td>
-<br/><br/></td><td>
Tap to place the cursor<br/><br/></td><td>
Hold to open the context menu<br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
ColorEdit<br/><br/></td><td>
Select the color<br/><br/></td><td>
-<br/><br/></td><td>
Tap to select the color,

Tap on ColorCode Editor box to place the cursor<br/><br/></td><td>
Hold on ColorCode Editor to open the ContextMenu<br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
SfCircularGauge<br/><br/></td><td>
-<br/><br/></td><td>
-<br/><br/></td><td>
-<br/><br/></td><td>
-<br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
PinnableListBox<br/><br/></td><td>
-<br/><br/></td><td>
-<br/><br/></td><td>
Click and selection.<br/><br/></td><td>
Right click<br/><br/></td></tr>
</table>