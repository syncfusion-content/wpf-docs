---
layout: post
title: Touch support for Syncfusion WPF controls
description: Touch Support Overview
platform: WPF
control: General
documentation: ug
---

# Touch Support

Syncfusion WPF controls provide touch support. This feature allows you to interact with your applications on touch-enabled devices such as touch-screen monitors. It provides extensibility, and all our specific controls support to `Gestures`.

## Gesture

Gestures determine whether a finger or stylus has to move over a control. Syncfusion WPF controls support the following touch gestures:

* Swipe
* Pinch
* Tap
* Hold

### Swipe

Move one or more fingers across the screen in horizontal or vertical direction. This gesture quickly effects the screen after released the finger from screen. It is also used for selection process.

### Pinch

Touch the screen with two or more fingers, then move them to zoom in or zoom out the screen. Pinch is used commonly to change the size of picture, object, or content on the screen. For example, if you use Google maps, use pinch to zoom in or zoom out the Google maps.

### Tap

Tap describes a click or touch on the object. If you tap an object on the screen once, you can see that the object is selected or clicked. This process is applicable to the left mouse button too. If you tap an object (picture, maps. etc.) twice, the object will be zoomed in or zoomed out.

### Hold

Touch and hold the screen for a few seconds. If you long press the screen or page, the context menu of the current page will be opened. This gesture functions as same as the right-clicking a mouse.

## Controls Behavior

This table shows the gesture mappings for each control.

<table>
<tr>
<td>
{{'**Category**'| markdownify }}<br/><br/>
</td>
<td>
{{'**Control**'| markdownify }}<br/><br/>
</td>
<td>
{{'**Swipe**'| markdownify }}<br/><br/>
</td>
<td>
{{'**Pinch**'| markdownify }}<br/><br/>
</td>
<td>
{{'**Tap**'| markdownify }}<br/><br/>
</td>
<td>
{{'**Hold**'| markdownify }}<br/><br/>
</td>
</tr>
<tr>
<td>
GRIDS<br/><br/>
</td>
<td>
DataGrid<br/><br/>
</td>
<td>
Scrolling, Drag and drop and Resizing<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
Click and Selection<br/><br/>
</td>
<td>
Right Click<br/><br/>
</td>
</tr>
<tr>
<td>
<br/><br/>
</td>
<td>
TreeGrid<br/><br/>
</td>
<td>
Scrolling, Drag and drop and Resizing<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
Click and Selection<br/><br/>
</td>
<td>
Right Click<br/><br/>
</td>
</tr>
<tr>
<td>
<br/><br/>
</td>
<td>
Grid Control<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
-<br/><br/>
</td>
</tr>
<tr>
<td>
<br/><br/>
</td>
<td>
Property Grid<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
Click <br/><br/>
</td>
<td>
-<br/><br/>
</td>
</tr>
<tr>
<td>
DATA VISUALIZATION<br/><br/>
</td>
<td>
Charts<br/><br/>
</td>
<td>
Panning, Scrolling, Annotation resizing, dragging<br/><br/>
</td>
<td>
Zooming<br/><br/>
</td>
<td>
ToolTip, Series selection, Segment selection, Annotation text editing, Annotation selection<br/><br/>
</td>
<td>
-<br/><br/>
</td>
</tr>
<tr>
<td>
<br/><br/>
</td>
<td>
Diagram<br/><br/>
</td>
<td>
{{'**Diagram:**'| markdownify }}Pan/Scroll, MultipleSelect, Drop, Zoom, Connect<br/><br/>{{'**Stencil:**'| markdownify }}Drag & Drop<br/><br/>{{'**Node and Annotation:** '| markdownify }}Drag, Resize, Rotate, Connect<br/><br/>{{'**Connector:**'| markdownify }}Segment editing, Connect<br/><br/>{{'**Port:**'| markdownify }}Drag, Connect<br/><br/></td>
<td>
Zoom<br/><br/>
</td>
<td>
Select<br/><br/>
</td>
<td>
Context Menu<br/><br/>
</td>
</tr>
<tr>
<td>
<br/><br/>
</td>
<td>
Barcode<br/><br/>
</td>
<td>
NA<br/><br/>
</td>
<td>
NA<br/><br/>
</td>
<td>
NA<br/><br/>
</td>
<td>
NA<br/><br/>
</td>
</tr>
<tr>
<td>
<br/><br/>
</td>
<td>
Bullet Graph<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
Click<br/><br/>
</td>
<td>
-<br/><br/>
</td>
</tr>
<tr>
<td>
<br/><br/>
</td>
<td>
Circular Gauge<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
-<br/><br/>
</td>
</tr>
<tr>
<td>
<br/><br/>
</td>
<td>
Linear Gauge<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
-<br/><br/>
</td>
</tr>
<tr>
<td>
<br/><br/>
</td>
<td>
Digital Gauge<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
-<br/><br/>
</td>
</tr>
<tr>
<td>
<br/><br/>
</td>
<td>
Radial Gauge<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
-<br/><br/>
</td>
</tr>
<tr>
<td>
<br/><br/>
</td>
<td>
Gantt<br/><br/>
</td>
<td>
Selection and drag and drop <br/><br/>
</td>
<td>
 -<br/><br/>
</td>
<td>
Click and select <br/><br/>
</td>
<td>
Select<br/><br/>
</td>
</tr>
<tr>
<td>
<br/><br/>
</td>
<td>
HeatMap<br/><br/>
</td>
<td>
Pan/Scroll<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
-<br/><br/>
</td>
</tr>
<tr>
<td>
<br/><br/>
</td>
<td>
Kanban Board<br/><br/>
</td>
<td>
Panning/Scrolling, Dragging<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
Column collapse/expand<br/><br/>
</td>
<td>
Hold to select the card for dragging<br/><br/>
</td>
</tr>
<tr>
<td>
<br/><br/>
</td>
<td>
Map<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
Pan<br/><br/>
</td>
<td>
Click and Select<br/><br/>
</td>
<td>
-<br/><br/>
</td>
</tr>
<tr>
<td>
<br/><br/>
</td>
<td>
Range Navigator<br/><br/>
</td>
<td>
Scroll<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
Range selection<br/><br/>
</td>
<td>
-<br/><br/>
</td>
</tr>
<tr>
<td>
<br/><br/>
</td>
<td>
Smith Chart<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
Click<br/><br/>
</td>
<td>
-<br/><br/>
</td>
</tr>
<tr>
<td>
<br/><br/>
</td>
<td>
Sparkline<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
Click<br/><br/>
</td>
<td>
-<br/><br/>
</td>
</tr>
<tr>
<td>
<br/><br/>
</td>
<td>
Sunburst Chart<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
Click and Select<br/><br/>
</td>
<td>
-<br/><br/>
</td>
</tr>
<tr>
<td>
<br/><br/>
</td>
<td>
Surface Chart<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
Click<br/><br/>
</td>
<td>
-<br/><br/>
</td>
</tr>
<tr>
<td>
<br/><br/>
</td>
<td>
TreeMap<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
Click<br/><br/>
</td>
<td>
-<br/><br/>
</td>
</tr>
<tr>
<td>
FILE VIEWERS AND EDITORS<br/><br/>
</td>
<td>
PDF Viewer<br/><br/>
</td>
<td>
Scroll<br/><br/>
</td>
<td>
Zoom<br/><br/>
</td>
<td>
Button click<br/><br/>
</td>
<td>
-<br/><br/>
</td>
</tr>
<tr>
<td>
<br/><br/>
</td>
<td>
RichTextBox<br/><br/>
</td>
<td>
Swipe left/right to scroll the pages horizontally. Swipe up/down to scroll the pages vertically<br/><br/>
</td>
<td>
Zoom in/out<br/><br/>
</td>
<td>
Click and select<br/><br/>
</td>
<td>
-<br/><br/>
</td>
</tr>
<tr>
<td>
<br/><br/>
</td>
<td>
Spreadsheet<br/><br/>
</td>
<td>
Scrolling and Resizing<br/><br/>
</td>
<td>
Zoom in & Zoom out<br/><br/>
</td>
<td>
Click and Selection<br/><br/>
</td>
<td>
Right Click<br/><br/>
</td>
</tr>
<tr>
<td>
<br/><br/>
</td>
<td>
Syntax Editor<br/><br/>
</td>
<td>
  -<br/><br/>
</td>
<td>
  -<br/><br/>
</td>
<td>
Tap to set the cursor index. Double tab to select the current word of cursor placed index <br/><br/>
</td>
<td>
Hold to open Context menu  <br/><br/>
</td>
</tr>
<tr>
<td>
INPUT CONTROLS<br/><br/>
</td>
<td>
Currency TextBox<br/><br/>
</td>
<td>
- <br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
double tab to select the word <br/><br/>
</td>
<td>
Hold to open the default context menu<br/><br/>
</td>
</tr>
<tr>
<td>
<br/><br/>
</td>
<td>
Double TextBox<br/><br/>
</td>
<td>
- <br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
double tab to select the word <br/><br/>
</td>
<td>
Hold to open the default context menu<br/><br/>
</td>
</tr>
<tr>
<td>
<br/><br/>
</td>
<td>
Integer TextBox<br/><br/>
</td>
<td>
 - <br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
double tab to select the word <br/><br/>
</td>
<td>
Hold to open the default context menu<br/><br/>
</td>
</tr>
<tr>
<td>
<br/><br/>
</td>
<td>
Masked Edit<br/><br/>
</td>
<td>
Select<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
Tap to place the cursor<br/><br/>
</td>
<td>
Hold to open the context menu<br/><br/>
</td>
</tr>
<tr>
<td>
<br/><br/>
</td>
<td>
Percent TextBox<br/><br/>
</td>
<td>
 - <br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
double tab to select the word <br/><br/>
</td>
<td>
Hold to open the default context menu<br/><br/>
</td>
</tr>
<tr>
<td>
<br/><br/>
</td>
<td>
TextBox<br/><br/>
</td>
<td>
Move<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
double tab to select the word <br/><br/>
</td>
<td>
Hold to open the default context menu<br/><br/>
</td>
</tr>
<tr>
<td>
<br/><br/>
</td>
<td>
Check ListBox<br/><br/>
</td>
<td>
Scrolling<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
Tab to select the item<br/><br/>
</td>
<td>
-<br/><br/>
</td>
</tr>
<tr>
<td>
<br/><br/>
</td>
<td>
Numeric Updown<br/><br/>
</td>
<td>
Selection<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
Tap up down button to change the values. <br/><br/>
</td>
<td>
Hold to open the default context menu<br/><br/>
</td>
</tr>
<tr>
<td>
<br/><br/>
</td>
<td>
Domain Updown<br/><br/>
</td>
<td>
 - <br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
Tap up down button to change the values. <br/><br/>
</td>
<td>
-<br/><br/>
</td>
</tr>
<tr>
<td>
<br/><br/>
</td>
<td>
ButtonAdv<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
Click<br/><br/>
</td>
<td>
   -<br/><br/>
</td>
</tr>
<tr>
<td>
<br/><br/>
</td>
<td>
Dropdown Button<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
Dropdown open<br/><br/>
</td>
<td>
   -<br/><br/>
</td>
</tr>
<tr>
<td>
<br/><br/>
</td>
<td>
Split Button<br/><br/>
</td>
<td>
Click<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
Select<br/><br/>
</td>
<td>
-<br/><br/>
</td>
</tr>
<tr>
<td>
<br/><br/>
</td>
<td>
Color Picker<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
Click<br/><br/>
</td>
<td>
-<br/><br/>
</td>
</tr>
<tr>
<td>
<br/><br/>
</td>
<td>
Color Palette<br/><br/>
</td>
<td>
Swipe<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
Select<br/><br/>
</td>
<td>
-<br/><br/>
</td>
</tr>
<tr>
<td>
<br/><br/>
</td>
<td>
Color Picker Palette<br/><br/>
</td>
<td>
Swipe<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
Click<br/><br/>
</td>
<td>
  -<br/><br/>
</td>
</tr>
<tr>
<td>
<br/><br/>
</td>
<td>
Color Edit<br/><br/>
</td>
<td>
Select the color<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
Tap to select the color. Tap on ColorCode Editor box to place the cursor<br/><br/>
</td>
<td>
Hold on ColorCode Editor to open the ContextMenu<br/><br/>
</td>
</tr>
<tr>
<td>
<br/><br/>
</td>
<td>
Radial Slider<br/><br/>
</td>
<td>
Swipe to change change the slider positions <br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
Tap to update the selected value<br/><br/>
</td>
<td>
-<br/><br/>
</td>
</tr>
<tr>
<td>
<br/><br/>
</td>
<td>
Rating<br/><br/>
</td>
<td>
Swipe to change the Rating values.<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
Tap to increase or decrease the rating values.<br/><br/>
</td>
<td>
-<br/><br/>
</td>
</tr>
<tr>
<td>
<br/><br/>
</td>
<td>
Calculator<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
Tab to enter the values in text area<br/><br/>
</td>
<td>
-<br/><br/>
</td>
</tr>
<tr>
<td>
<br/><br/>
</td>
<td>
Range Slider<br/><br/>
</td>
<td>
Swipe horizontally or vertically to change minimum and maximum range values <br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
Tap to increase or decrease the values based on step value.<br/><br/> 
</td>
<td>
-<br/><br/>
</td>
</tr>
<tr>
<td>
LISTS AND DROPDOWN<br/><br/>
</td>
<td>
ComboBox<br/><br/>
</td>
<td>
Swipe<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
Click and Select<br/><br/>
</td>
<td>
-<br/><br/>
</td>
</tr>
<tr>
<td>
<br/><br/>
</td>
<td>
Auto Complete<br/><br/>
</td>
<td>
Scroll<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
Select<br/><br/>
</td>
<td>
-<br/><br/>
</td>
</tr>
<tr>
<td>
<br/><br/>
</td>
<td>
MultiColumn Dropdown<br/><br/>
</td>
<td>
Scrolling<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
Click and Selection<br/><br/>
</td>
<td>
Right Click<br/><br/>
</td>
</tr>
<tr>
<td>
LAYOUT<br/><br/>
</td>
<td>
Docking<br/><br/>
</td>
<td>
Swipe to rearrange Tab order in Tabbed and Document state windows.<br/><br/> 
</td>
<td>
   -<br/><br/>
</td>
<td>
Tap to select the active window of DockingManager. Double tab to float the active window <br/><br/>
</td>
<td>
Hold any docking window header Context menu opened <br/><br/>
</td>
</tr>
<tr>
<td>
<br/><br/>
</td>
<td>
Card View<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
click and select<br/><br/>
</td>
<td>
-<br/><br/>
</td>
</tr>
<tr>
<td>
<br/><br/>
</td>
<td>
Carousel<br/><br/>
</td>
<td>
To view the next or previous items<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
click and select the item <br/><br/>
</td>
<td>
-<br/><br/>
</td>
</tr>
<tr>
<td>
<br/><br/>
</td>
<td>
Chromeless Window<br/><br/>
</td>
<td>
Move<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
Select<br/><br/>
</td>
<td>
-<br/><br/>
</td>
</tr>
<tr>
<td>
<br/><br/>
</td>
<td>
Document Container<br/><br/>
</td>
<td>
Swipe to rearrange TDI mode Items <br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
Tap to select the active document window<br/><br/>
</td>
<td>
Hold any document window header Context menu opened <br/><br/>
</td>
</tr>
<tr>
<td>
<br/><br/>
</td>
<td>
GridSplitter<br/><br/>
</td>
<td>
Swipe to move the splitter horizontally or vertically <br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
-<br/><br/>
</td>
</tr>
<tr>
<td>
<br/><br/>
</td>
<td>
TileView<br/><br/>
</td>
<td>
Swipe to reorder the tile items <br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
Tap to select the item <br/><br/>
</td>
<td>
-<br/><br/>
</td>
</tr>
<tr>
<td>
<br/><br/>
</td>
<td>
Tab Splitter<br/><br/>
</td>
<td>
Swipe to move the splitter <br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
Tap to select the item<br/><br/>
</td>
<td>
Hold on TabBarSplitterItem to open the context menu<br/><br/>
</td>
</tr>
<tr>
<td>
NAVIGATION<br/><br/>
</td>
<td>
Ribbon<br/><br/>
</td>
<td>
Swipe<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
Click<br/><br/>
</td>
<td>
Context Menu<br/><br/>
</td>
</tr>
<tr>
<td>
<br/><br/>
</td>
<td>
TabControlExt<br/><br/>
</td>
<td>
Swipe to move the tabitem<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
Tab to change the SelectedItem<br/><br/>
</td>
<td>
Hold to open TabItemExt ContextMenu<br/><br/>
</td>
</tr>
<tr>
<td>
<br/><br/>
</td>
<td>
Tab Navigation<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
Tap to navigate the next or previous view <br/><br/>
</td>
<td>
-<br/><br/>
</td>
</tr>
<tr>
<td>
<br/><br/>
</td>
<td>
TreeView<br/><br/>
</td>
<td>
Swipe<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
Click <br/><br/>
</td>
<td>
Context menu, Drag drop<br/><br/>
</td>
</tr>
<tr>
<td>
<br/><br/>
</td>
<td>
Accordion<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
Tap to select the accordion item and expand or collapse item<br/><br/>
</td>
<td>
-<br/><br/>
</td>
</tr>
<tr>
<td>
<br/><br/>
</td>
<td>
Group Bar<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
Tap to select the groupbar item. Expand or collapse the item<br/><br/>
</td>
<td>
Hold to open Context menu<br/><br/>
</td>
</tr>
<tr>
<td>
<br/><br/>
</td>
<td>
Hierarchical Navigator<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
Tab to navigate the next item<br/><br/>
</td>
<td>
-<br/><br/>
</td>
</tr>
<tr>
<td>
<br/><br/>
</td>
<td>
Menu<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
Click<br/><br/>
</td>
<td>
-<br/><br/>
</td>
</tr>
<tr>
<td>
<br/><br/>
</td>
<td>
Navigation Drawer<br/><br/>
</td>
<td>
To open the primary or secondary drawers.<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
-<br/><br/>
</td>
</tr>
<tr>
<td>
<br/><br/>
</td>
<td>
Radial Menu<br/><br/>
</td>
<td>
Swipe to rotate the radial menu items<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
Tap to expand or collapse the radial menu item<br/><br/>
</td>
<td>
Indicates the selected item.<br/><br/>
</td>
</tr>
<tr>
<td>
<br/><br/>
</td>
<td>
TaskBar<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
Tap to expand or collapse the task bar item<br/><br/>
</td>
<td>
  -<br/><br/>
</td>
</tr>
<tr>
<td>
<br/><br/>
</td>
<td>
ToolBar<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
Click<br/><br/>
</td>
<td>
Tooltip<br/><br/>
</td>
</tr>
<tr>
<td>
<br/><br/>
</td>
<td>
Tree Navigator<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
Tab to navigate the item<br/><br/>
</td>
<td>
  -<br/><br/>
</td>
</tr>
<tr>
<td>
<br/><br/>
</td>
<td>
Wizard Control<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
click<br/><br/>
</td>
<td>
-<br/><br/>
</td>
</tr>
<tr>
<td>
CALENDARS<br/><br/>
</td>
<td>
Calendar<br/><br/>
</td>
<td>
Swipe to change the month view<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
Tap to select the date<br/><br/>
</td>
<td>
-<br/><br/>
</td>
</tr>
<tr>
<td>
<br/><br/>
</td>
<td>
DateTimeEdit<br/><br/>
</td>
<td>
Swipe<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
Select<br/><br/>
</td>
<td>
  -<br/><br/>
</td>
</tr>
<tr>
<td>
<br/><br/>
</td>
<td>
DatePicker<br/><br/>
</td>
<td>
Swipe to change the dates<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
click to select the date<br/><br/>
</td>
<td>
-<br/><br/>
</td>
</tr>
<tr>
<td>
<br/><br/>
</td>
<td>
TimePicker<br/><br/>
</td>
<td>
Swipe to change the time<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
click to select the Time<br/><br/>
</td>
<td>
-<br/><br/>
</td>
</tr>
<tr>
<td>
<br/><br/>
</td>
<td>
Scheduler<br/><br/>
</td>
<td>
View swiping (By enabling EnableTouch property to true)<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
Tap support for Cell selection, appointment selection , display context menu . Double tap support to appointment editor. <br/><br/>
</td>
<td>
-<br/><br/>
</td>
</tr>
<tr>
<td>
<br/><br/>
</td>
<td>
TimeSpanEdit<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
-<br/><br/>
</td>
</tr>
<tr>
<td>
REPORTING<br/><br/>
</td>
<td>
Report Designer<br/><br/>
</td>
<td>
Scrolling, Resizing <br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
Click and Select<br/><br/>
</td>
<td>
Right-Click<br/><br/>
</td>
</tr>
<tr>
<td>
<br/><br/>
</td>
<td>
Report Writer<br/><br/>
</td>
<td>
NA<br/><br/>
</td>
<td>
NA<br/><br/>
</td>
<td>
NA<br/><br/>
</td>
<td>
NA<br/><br/>
</td>
</tr>
<tr>
<td>
<br/><br/>
</td>
<td>
Report Viewer<br/><br/>
</td>
<td>
Scrolling<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
Click and select<br/><br/>
</td>
<td>
-<br/><br/>
</td>
</tr>
<tr>
<td>
FILE FORMAT<br/><br/>
</td>
<td>
Excel<br/><br/>
</td>
<td>
NA<br/><br/>
</td>
<td>
NA<br/><br/>
</td>
<td>
NA<br/><br/>
</td>
<td>
NA<br/><br/>
</td>
</tr>
<tr>
<td>
<br/><br/>
</td>
<td>
PDF<br/><br/>
</td>
<td>
NA<br/><br/>
</td>
<td>
NA<br/><br/>
</td>
<td>
NA<br/><br/>
</td>
<td>
NA<br/><br/>
</td>
</tr>
<tr>
<td>
<br/><br/>
</td>
<td>
Word<br/><br/>
</td>
<td>
NA (Non UI Component)<br/><br/>
</td>
<td>
NA (Non UI Component)<br/><br/>
</td>
<td>
NA (Non UI Component)<br/><br/>
</td>
<td>
NA (Non UI Component)<br/><br/>
</td>
</tr>
<tr>
<td>
<br/><br/>
</td>
<td>
PowerPoint<br/><br/>
</td>
<td>
NA<br/><br/>
</td>
<td>
NA<br/><br/>
</td>
<td>
NA<br/><br/>
</td>
<td>
NA<br/><br/>
</td>
</tr>
<tr>
<td>
BUSINESS INTELLIGENCE<br/><br/>
</td>
<td>
Olap Chart<br/><br/>
</td>
<td>
Drag and drop, expand and collapse and resizing<br/><br/>
</td>
<td>
Zooming and panning<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
Right click, tooltip and context menu<br/><br/>
</td>
</tr>
<tr>
<td>
<br/><br/>
</td>
<td>
Olap Client<br/><br/>
</td>
<td>
Drag and drop, expand and collapse and resizing<br/><br/>
</td>
<td>
Zooming and panning<br/><br/>
</td>
<td>
Click, hyperlink and selection<br/><br/>
</td>
<td>
Right click, tooltip and context menu<br/><br/>
</td>
</tr>
<tr>
<td>
<br/><br/>
</td>
<td>
Olap Gauge<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
Tooltip<br/><br/>
</td>
</tr>
<tr>
<td>
<br/><br/>
</td>
<td>
Olap Grid<br/><br/>
</td>
<td>
Drag and drop, expand and collapse and resizing<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
Click, hyperlink and selection<br/><br/>
</td>
<td>
Right click and tooltip<br/><br/>
</td>
</tr>
<tr>
<td>
<br/><br/>
</td>
<td>
Pivot Grid<br/><br/>
</td>
<td>
Drag and drop, expand and collapse and resizing<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
Click, hyperlink and selection<br/><br/>
</td>
<td>
Right click, context menu and tooltip<br/><br/>
</td>
</tr>
<tr>
<td>
NOTIFICATION<br/><br/>
</td>
<td>
Hub Tile<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
Tap to perform the scale animation based on tile pressed direction. <br/><br/>
</td>
<td>
-<br/><br/>
</td>
</tr>
<tr>
<td>
<br/><br/>
</td>
<td>
Notify Icon<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
Tap to close the notify icon popup <br/><br/>
</td>
<td>
-<br/><br/>
</td>
</tr>
<tr>
<td>
<br/><br/>
</td>
<td>
Busy Indicator<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
-<br/><br/>
</td>
</tr>
<tr>
<td>
DATA SCIENCE<br/><br/>
</td>
<td>
Predictive Analytics<br/><br/>
</td>
<td>
NA<br/><br/>
</td>
<td>
NA<br/><br/>
</td>
<td>
NA<br/><br/>
</td>
<td>
NA<br/><br/>
</td>
</tr>
<tr>
<td>
MISCELLANEOUS<br/><br/>
</td>
<td>
Calculate<br/><br/>
</td>
<td>
NA (Non UI Component)<br/><br/>
</td>
<td>
NA (Non UI Component)<br/><br/>
</td>
<td>
NA (Non UI Component)<br/><br/>
</td>
<td>
NA (Non UI Component)<br/><br/>
</td>
</tr>
<tr>
<td>
<br/><br/>
</td>
<td>
Spell Checker<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
Tab to perform the spell check operations in spell check dialog window<br/><br/>
</td>
<td>
Hold to open the suggestion context menu<br/><br/>
</td>
</tr>
<tr>
<td>
CLASSIC CONTROLS<br/><br/>
</td>
<td>
Busy indicator<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
-<br/><br/>
</td>
</tr>
<tr>
<td>
<br/><br/>
</td>
<td>
RichTextBox<br/><br/>
</td>
<td>
Swipe left/right to scroll the pages horizontally Swipe up/down to scroll the pages vertically<br/><br/>
</td>
<td>
Zoom in/out<br/><br/>
</td>
<td>
Click and select<br/><br/>
</td>
<td>
-<br/><br/>
</td>
</tr>
<tr>
<td>
<br/><br/>
</td>
<td>
Diagram<br/><br/>
</td>
<td>
{{'**Diagram:**'| markdownify }}Pan/Scroll, MultipleSelect, Drop, Zoom, Connect<br/><br/>{{'**Stencil:**'| markdownify }}Drag & Drop<br/><br/>{{'**Node and Annotation:** '| markdownify }}Drag, Resize, Rotate, Connect<br/><br/>{{'**Connector:**'| markdownify }}Segment editing, Connect<br/><br/>{{'**Port:**'| markdownify }}Drag, Connect<br/><br/></td>
<td>
Zoom<br/><br/>
</td>
<td>
Select<br/><br/>
</td>
<td>
Context Menu<br/><br/>
</td>
</tr>
<tr>
<td>
<br/><br/>
</td>
<td>
MaskedTextBox<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
Click, Select<br/><br/>
</td>
<td>
Context Menu <br/><br/>
</td>
</tr>
<tr>
<td>
<br/><br/>
</td>
<td>
GridTreeControl<br/><br/>
</td>
<td>
Scrolling, Drag and drop and Resizing<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
Click and Selection<br/><br/>
</td>
<td>
Right click<br/><br/>
</td>
</tr>
<tr>
<td>
<br/><br/>
</td>
<td>
Spreadsheet<br/><br/>
</td>
<td>
  -<br/><br/>
</td>
<td>
  -<br/><br/>
</td>
<td>
  -<br/><br/>
</td>
<td>
  -<br/><br/>
</td>
</tr>
<tr>
<td>
<br/><br/>
</td>
<td>
GridDataControl<br/><br/>
</td>
<td>
Scrolling, Drag and drop and Resizing<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
Click and Selection<br/><br/>
</td>
<td>
Right click<br/><br/>
</td>
</tr>
<tr>
<td>
<br/><br/>
</td>
<td>
Chart<br/><br/>
</td>
<td>
Panning, Scrolling, Dragging<br/><br/>
</td>
<td>
Zooming<br/><br/>
</td>
<td>
ToolTip, Series selection, Segment selection<br/><br/>
</td>
<td>
-<br/><br/>
</td>
</tr>
<tr>
<td>
<br/><br/>
</td>
<td>
Pinnable ListBox<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
-<br/><br/>
</td>
<td>
Click and selection.<br/><br/>
</td>
<td>
Right click<br/><br/>
</td>
</tr>
</table>
