---
layout: post
title: Overview
description: overview
platform: wpf
control: UpDown Control
documentation: ug
---

# Overview

The UpDown control displays numeric values. You can select any value on scrolling the values, by using the Increment and Decrement buttons of the UpDown control.

The features of the UpDown control include:

* Null value.
* Maximum and Minimum value.
* Maximum and Minimum validation.
* Culture.
* Number formatting.
* Animation speed.
* Text alignment.
* Keyboard and Mouse support.



### Breaking Changes in the UpDown control from Version 8.3 to Version 8.4

The event handler and event argument for the ValueChanging event is changed in version 8.4. The changes are provided in the following tabulation:

_Changes in the UpDown control from Version 8.3 to Version 8.4_

<table>
<tr>
<th>
{{ '**Event Name**' | markdownify }}</th><th>
{{ '**Old Type**' | markdownify }}</th><th>
{{ '**New Type**' | markdownify }}</th></tr>
<tr>
<td rowspan = "2">
ValueChanging</td><td>
PropertyChangedCallback</td><td>
ValueChangingEventHandler</td></tr>
<tr>
<td>
DependencyPropertyChangedEventArgs</td><td>
ValueChangingEventArgs</td></tr>
</table>


The following properties are no longer used and do not make any change in the UpDown control:

* CursorBackground
* CursorBorderBrush
* CursorWidth
* CursorBorderThickness
* CursorTemplate
* CursorVisible
* CursorPosition
* SelectionBrush
* AnimationShift



![](Overview_images/Overview_img1.png)



_Structure of the UpDown control_

### Structure

The following are the elements of the UpDown control:

* Text area - It is the area where the numeric values are displayed. You can edit the value of the UpDown control when the AllowEdit property is set to true.
* Increment button - It is a repeat button that can be clicked to increment the current value of the UpDown control.
* Decrement button - It is a repeat button that can be clicked to decrement the current value of the UpDown control.



### Sample Link: To access a sample:

Navigate to Start -> All Programs -> Syncfusion -> Essential Studio -> Dashboard.

Click the WPF drop-down list and then select Run Locally Installed Samples. In the sample browser, expand the Editor Controls TreeView item, and then select Up-DownText Box Demo.

