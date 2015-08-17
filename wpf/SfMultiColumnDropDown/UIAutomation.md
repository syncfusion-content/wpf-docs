---
layout: post
title: UIAutomation
description: uiautomation
platform: wpf
control: SfMultiColumnDropDownControl
documentation: ug
---

## UIAutomation

SfMultiColumnDropDownControl supports the following UIAutomations,

### Coded UI

SfMutliColumnDropDownControl supports CodedUITest automation that enables you to create an automation test with SfMultiColumnDropDownControl elements and record the sequence of actions.

There are three level of support in CodedUITest for SfMultiColumnDropDownControl.

_List of levels_

<table>
<tr>
<th>
Levels</th><th>
Description</th></tr>
<tr>
<th>
Level – 1</th><th>
Record and Detecting the UI Elements when you do the actions in the control.</th></tr>
<tr>
<th>
Level – 2</th><th>
Provide custom properties for UI elements when you drag the Cross hair to any UI element.</th></tr>
<tr>
<th>
Level – 3</th><th>
Coded UI Test Builder generates code from recorded session and custom class is implemented to access custom properties, so the generated code is simplified.</th></tr>
</table>
The following screenshot illustrates the SfMultiColumnDropDownControl properties, when you drag the crosshair to the SfMultiColumnDropDown control.

![](Features_images/Features_img12.png)



Following are the properties for SfMultiColumnDropDownControl.

_Property Table_

<table>
<tr>
<td>
UI Element</td><td>
Properties</td></tr>
<tr>
<td>
SfMultiColumnDropDownControl</td><td>
* AllowAutoComplete* AllowNullInput* AllowImmediatePopup* AllowIncrementalFiltering* AllowCaseSensitiveFiltering* AllowSpinOnMouseWheel* DisplayMember* IsDropDownOpen* SelectedIndex* ValueMember</td></tr>
</table>

### Quick Test Professional


SfMultiColumnDropDownControl supports for QTP test. You can record the actions performed in the control, by mentioning the corresponding method name with Syncfusion namespace. To know more about QTP test refer to the [link](http://help.syncfusion.com/ug/wpf/Documents/quicktestprofessionalqtp.htm).

The following screenshot illustrates the QTP Test for SfMultiColumnDropDownControl.

![](Features_images/Features_img13.png)



Following are methods for SfMultiColumnDropDownControl.

_Methods Table_

<table>
<tr>
<th>
Method</th><th>
Description</th><th>
Parameters </th><th>
Return Type </th></tr>
<tr>
<th>
void SetSelectedIndex(int index);</th><th>
To set the SelectedIndex from the Popup</th><th>
 Int index</th><th>
void</th></tr>
<tr>
<th>
void ShowPopup();</th><th>
To open the Popup</th><th>
NA</th><th>
void</th></tr>
<tr>
<th>
void HidePopup();</th><th>
To close the Popup</th><th>
NA</th><th>
void</th></tr>
</table>


