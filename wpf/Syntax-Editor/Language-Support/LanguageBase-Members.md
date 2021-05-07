---
layout: post
title: LanguageBase Members in WPF Syntax Editor control | Syncfusion
description: Learn about LanguageBase Members support in Syncfusion WPF Syntax Editor control and more.
platform: wpf
control: Syntax Editor
documentation: ug
---

## LanguageBase Members

LanguageBase class in Syncfusion.Windows.Edit namespace plays a vital role in the implementation of language support in EditControl. In order to include a support for a new or custom language, a class inherited from LanguageBase or its sub classes need to be implemented. LanguageBase contains a number of properties and methods to enable the custom language developers configure their languages easily. This topic discusses about the properties and methods available in the LanguageBase class.

Properties

The following table lists the properties available in LanguageBase class and its usage.

<table>
<tr>
<td>
Property name<br/><br/></td><td>
Type<br/><br/></td><td>
Description<br/><br/></td></tr>
<tr>
<td>
ApplyColoring<br/><br/></td><td>
Boolean<br/><br/></td><td>
Gets or sets a value indicating if the language supports syntax highlighting.<br/><br/></td></tr>
<tr>
<td>
BlockEnd<br/><br/></td><td>
String<br/><br/></td><td>
Gets or sets a value indicating the end text that denotes end of a block in code.<br/><br/></td></tr>
<tr>
<td>
BlockStart<br/><br/></td><td>
String<br/><br/></td><td>
Gets or sets a value indicating the start text that denotes Start of a block in code.<br/><br/></td></tr>
<tr>
<td>
CaseSensitive<br/><br/></td><td>
Boolean<br/><br/></td><td>
Gets or sets a value indicating whether the Language has Case Sensitive or not.<br/><br/></td></tr>
<tr>
<td>
CommitsIntellisenseItemOnSpaceBar<br/><br/></td><td>
Boolean<br/><br/></td><td>
Gets or sets a value indicating whether the selected Intellisense items to be appended when space bar is pressed.<br/><br/></td></tr>
<tr>
<td>
EllipsisText<br/><br/></td><td>
String<br/><br/></td><td>
Gets or sets a value indicating the text to be displayed when a block is collapsed. By default it is set to "...".<br/><br/></td></tr>
<tr>
<td>
FileExtension<br/><br/></td><td>
String<br/><br/></td><td>
Gets or sets File Extension supported by the language.<br/><br/></td></tr>
<tr>
<td>
Formats<br/><br/></td><td>
IEnumerable<br/><br/></td><td>
Gets or sets a collection of type of IFormat indicating the language configurations. It has been modified to IEnumerable type to allow the users to binding a custom collection as language formats.<br/><br/></td></tr>
<tr>
<td>
IntellisenseCommitCharacters<br/><br/></td><td>
String<br/><br/></td><td>
Gets or sets a value indicating when the selected Intellisense items to be appended. The string given will be converted to individual characters internally and verified to append the selected item to text.<br/><br/></td></tr>
<tr>
<td>
IntellisenseDrillDownChar<br/><br/></td><td>
Char<br/><br/></td><td>
Gets or sets a value indicating a char on which the <br/><br/>sub-items of the intellisense items to displayed.<br/><br/></td></tr>
<tr>
<td>
IsSplitTextToWords<br/><br/></td><td>
Boolean<br/><br/></td><td>
Gets or sets a value indicating if the text in lines has to be spitted into tokens.<br/><br/></td></tr>
<tr>
<td>
Lexem<br/><br/></td><td>
IEnumerable<br/><br/></td><td>
Gets or sets a collection of type of ILexem indicating the language configurations. It has been modified to IEnumerable type to allow the users to bind a custom collection as language lexems.<br/><br/></td></tr>
<tr>
<td>
Name<br/><br/></td><td>
String<br/><br/></td><td>
Gets or sets Name of the Language.<br/><br/></td></tr>
<tr>
<td>
ParentControl<br/><br/></td><td>
EditControl<br/><br/></td><td>
Gets a value indicating the Parent EditControl’s reference.<br/><br/></td></tr>
<tr>
<td>
SplitLinesRegex<br/><br/></td><td>
String<br/><br/></td><td>
Gets or sets a value indicating the Regex to be applied for splitting the text in lines.<br/><br/></td></tr>
<tr>
<td>
SplitWordsRegex<br/><br/></td><td>
String<br/><br/></td><td>
Gets or sets a value indicating the Regex to be applied for splitting the lines into individual tokens.<br/><br/></td></tr>
<tr>
<td>
SupportsIntellisense<br/><br/></td><td>
Boolean<br/><br/></td><td>
Gets or sets a value indicating whether the language supports IntelliSense or not.<br/><br/></td></tr>
<tr>
<td>
SupportsOutlining<br/><br/></td><td>
Boolean<br/><br/></td><td>
Gets or sets a value indicating whether the language supports Outlining.<br/><br/></td></tr>
<tr>
<td>
TextForeground<br/><br/></td><td>
Brush<br/><br/></td><td>
Gets or sets Foreground brush to be applied when no Lexems are applicable for the text.<br/><br/></td></tr>
</table>

Methods

The following table lists the methods available in LanguageBase class and its purpose.

<table>
<tr>
<td>
Method<br/><br/></td><td>
Return Type<br/><br/></td><td>
Description<br/><br/></td></tr>
<tr>
<td>
ApplyColor(string text, int line);<br/><br/></td><td>
IFormat<br/><br/></td><td>
Helper method to apply coloring to the text based on the Lexems in the Language configurations. It is a protected method and can be overridden in the sub classes. The method is used to manipulate the Format to be applied to a particular token in a line.<br/><br/></td></tr>
<tr>
<td>
ApplyExpandCollapse(ApplyExpandCollapseArgs args)  <br/><br/></td><td>
Void<br/><br/></td><td>
Helper method to perform Expand Collapse for line items. When custom expand collapse logics is implemented, the methods can be overridden.This method runs in a background thread to overcome performance hits.Usage of any properties and methods outside the scope of the thread may result in an exception.<br/><br/></td></tr>
<tr>
<td>
ApplyExpandItems()<br/><br/></td><td>
Void<br/><br/></td><td>
Helper method to Apply Expansions for the content in the EditControl. This method can be called if the Expand Collapse has to be refreshed for entire text in EditControl.<br/><br/></td></tr>
<tr>
<td>
HideIntellisensePopup()<br/><br/></td><td>
Void<br/><br/></td><td>
Helper method to Hide Intellisense Pop-up.<br/><br/></td></tr>
<tr>
<td>
InitializeExpandCollapse()<br/><br/></td><td>
Void<br/><br/></td><td>
This method is called before the ApplyExpandCollapse and can be used to perform any Initialization operations.<br/><br/></td></tr>
<tr>
<td>
PositionIntellisensePopup(int line, int index)<br/><br/></td><td>
Void<br/><br/></td><td>
Helper method to adjust the Position of the Intellisense box. Line value in parameter <br/><br/>represents the line number (starts of 0)<br/><br/>and index in the parameter <br/><br/>represents the cursor index<br/><br/></td></tr>
<tr>
<td>
RefreshExpandItems(int line)<br/><br/></td><td>
Void<br/><br/></td><td>
Helper method to Refresh lines expansions from a specified line number. Line value in parameter refers to the index (starts from 0)<br/><br/></td></tr>
<tr>
<td>
ShowIntellisenseBox(EditIntellisenseArgs args)<br/><br/></td><td>
Void<br/><br/></td><td>
Helper method to Show the Intellisense pop-up.<br/><br/></td></tr>
<tr>
<td>
SplitTextToLines()<br/><br/></td><td>
Void<br/><br/></td><td>
A helper method to Split the text in the EditControl into individual lines.<br/><br/></td></tr>
</table>
