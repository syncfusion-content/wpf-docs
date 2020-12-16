---
layout: post
title: Members of the WPF Syncfusion Syntax Editor control | Syncfusion
description: Learn about Members of Syncfusion WPF Syntax Editor control, which is a code editor similiar to  Visual studio editor.
platform: wpf
control: Syntax Editor
documentation: ug
---

# WPF EditControl Members

EditControl class contains variety of properties, methods and events to enable the developers utilize this control easily. It is enhanced with maximum possible level of customization and facilities that are provided for the developers to use these controls effectively. This topic discusses about the properties, methods and events available in the EditControl class.

**Properties**

The following table illustrates the properties in EditControl and its usages.

<table>
<tr>
<td>
Name of the property<br/><br/></td><td>
Type<br/><br/></td><td>
Description<br/><br/></td></tr>
<tr>
<td>
AcceptsTab<br/><br/></td><td>
Boolean<br/><br/></td><td>
Gets or sets a boolean property to allow or restrict the usage of TAB key in EditControl.<br/><br/></td></tr>
<tr>
<td>
AssemblyReferences<br/><br/></td><td>
IEnumerable(Uri)<br/><br/></td><td>
Gets or sets a collection of type Uri, this property enables you to specify the path of assemblies from EditControl and it should fetch Intellisense items automatically.<br/><br/></td></tr>
<tr>
<td>
CurrentLanguage<br/><br/></td><td>
LanguageBase<br/><br/></td><td>
Gets a LanguageBase instance based on the DocumentLanguage property. <br/><br/></td></tr>
<tr>
<td>
CursorIndex<br/><br/></td><td>
Int<br/><br/></td><td>
Gets current index of text where the cursor is located in EditControl pane.<br/><br/></td></tr>
<tr>
<td>
CustomLanguage<br/><br/></td><td>
LanguageBase<br/><br/></td><td>
Gets or sets an instance of LanguageBase type indicating the custom language.<br/><br/></td></tr>
<tr>
<td>
DocumentLanguage<br/><br/></td><td>
Languages<br/><br/></td><td>
Gets or sets Language for the text in EditControl. Syntax highlighting and outlining of text in EditControl are performed based on the language set using this property.<br/><br/></td></tr>
<tr>
<td>
DocumentSource<br/><br/></td><td>
String<br/><br/></td><td>
Gets or sets Source for EditControl. The filename specified will be loaded in the EditControl.<br/><br/></td></tr>
<tr>
<td>
EnableIntellisense<br/><br/></td><td>
Boolean<br/><br/></td><td>
Gets or sets a value indicating whether Intellisense is enabled in this instance of EditControl.<br/><br/></td></tr>
<tr>
<td>
EnableOutlining<br/><br/></td><td>
Boolean<br/><br/></td><td>
Gets or sets a value indicating whether Outlining of text in EditControl should be applied.<br/><br/></td></tr>
<tr>
<td>
FindOptions<br/><br/></td><td>
FindOptions<br/><br/></td><td>
Gets or sets an instance of FindOptions indicating the options selected in the FindReplace Window.<br/><br/></td></tr>
<tr>
<td>
FindResultsTabHeight<br/><br/></td><td>
Double<br/><br/></td><td>
Gets or sets a value indicating desired height of the find results tab.<br/><br/></td></tr>
<tr>
<td>
FindResultsTabVisibility<br/><br/></td><td>
TabVisibility<br/><br/></td><td>
Gets or sets a value indicating the Visibility mode of the find results tab. TabVisibility is enum type containing values such as Auto, Visible and Collapsed. <br/><br/></td></tr>
<tr>
<td>
HorizontalScrollBarVisibility<br/><br/></td><td>
ScrollBarVisibility<br/><br/></td><td>
Gets or sets a value indicating Visibility of Horizontal ScrollBar. By default, it is set to Auto, wherein the ScrollBar will be visible when required.<br/><br/></td></tr>
<tr>
<td>
IntellisenseBoxStyle<br/><br/></td><td>
Style<br/><br/></td><td>
Gets or sets a Style to be applied to IntelliSense listbox.<br/><br/></td></tr>
<tr>
<td>
IntellisenseCustomItemsSource<br/><br/></td><td>
IEnumerable<br/><br/></td><td>
Gets or sets a collection of business object inherited from IntellisenseItem to be displayed in the IntellisenseBox.<br/><br/></td></tr>
<tr>
<td>
IntellisenseItemTemplate<br/><br/></td><td>
DataTemplate<br/><br/></td><td>
Gets or sets a DataTemplate to be applied to an IntellisenseBox.<br/><br/></td></tr>
<tr>
<td>
IntellisenseMode<br/><br/></td><td>
IntellisenseMode<br/><br/></td><td>
Gets or sets a value indicating the Intellisense mode. It supports two modes viz, Auto and Custom. <br/><br/> In Auto mode, intellisense items are auto generated based on the language lexems, assembly references included.<br/> In Custom mode, users have to set the IntellisenseCustomItemsSource property to specify the items to be displayed in the intellisense.<br/></td></tr>
<tr>
<td>
<br/>IntellisensePopupHeight<br/><br/></td><td>
Double<br/><br/></td><td>
Gets or sets a value indicating desired height of the IntellisensePopup.  <br/><br/></td></tr>
<tr>
<td>
IntellisensePopupWidth<br/><br/></td><td>
Double<br/><br/></td><td>
Gets or sets a value indicating desired width of IntellisensePopup.<br/><br/></td></tr>
<tr>
<td>
IsFindResultsTabClosed<br/><br/></td><td>
Boolean<br/><br/></td><td>
Gets or sets a value indicating whether the Find Results Tab is closed or not. This property has a value `true` if the Find results tab in the EditControl is closed; otherwise, `false`.<br/><br/></td></tr>
<tr>
<td>
IsReadOnly<br/><br/></td><td>
Boolean<br/><br/></td><td>
Gets or sets a value indicating whether Read only mode is enabled or not.<br/><br/></td></tr>
<tr>
<td>
IsRedoEnabled<br/><br/></td><td>
Boolean<br/><br/></td><td>
Gets or sets a value indicating whether this instance supports Redo operation or not.<br/><br/></td></tr>
<tr>
<td>
IsUndoEnabled<br/><br/></td><td>
Boolean<br/><br/></td><td>
Gets or sets a value indicating whether this instance supports Undo operation or not.<br/><br/></td></tr>
<tr>
<td>
LineHeight<br/><br/></td><td>
Double<br/><br/></td><td>
Gets and sets the height of each line in EditControl.<br/><br/></td></tr>
<tr>
<td>
LineNumber<br/><br/></td><td>
Int<br/><br/></td><td>
Gets the line number where the cursor is currently located.<br/><br/></td></tr>
<tr>
<td>
Lines<br/><br/></td><td>
LinesCollection<br/><br/></td><td>
Gets the Collection of Lines in EditControl.  <br/><br/></td></tr>
<tr>
<td>
SearchResults<br/><br/></td><td>
SearchResults<br/><br/></td><td>
Gets or sets a value indicating the Search results.<br/><br/></td></tr>
<tr>
<td>
SelectedText<br/><br/></td><td>
String<br/><br/></td><td>
Gets a value indicating the Selected text of EditControl. <br/><br/></td></tr>
<tr>
<td>
ShowDefaultContextMenu<br/><br/></td><td>
Boolean<br/><br/></td><td>
Gets or sets a value indicating whether built-in context menu should be displayed.<br/><br/></td></tr>
<tr>
<td>
ShowFindAndReplace<br/><br/></td><td>
Boolean<br/><br/></td><td>
Gets or sets a value indicating whether Find and Replace functionality to enabled or not.<br/><br/></td></tr>
<tr>
<td>
ShowLineNumber<br/><br/></td><td>
Boolean<br/><br/></td><td>
Gets or sets a value indicating whether Line Number to be displayed or not. Set this to `true` to display the Line number. Default value is `true`.<br/><br/></td></tr>
<tr>
<td>
TabSpaces<br/><br/></td><td>
Int<br/><br/></td><td>
Gets or sets a value indicating the number of Spaces to include when the tab key is pressed.<br/><br/></td></tr>
<tr>
<td>
Text<br/><br/></td><td>
String<br/><br/></td><td>
Gets or sets a value indicating text in EditControl.<br/><br/></td></tr>
<tr>
<td>
VerticalScrollBarVisibility<br/><br/></td><td>
ScrollBarVisibility<br/><br/></td><td>
Gets or sets a value indicating Visibility of Vertical ScrollBar. By default, it is set to Auto, wherein the ScrollBar will be visible when required.<br/><br/></td></tr>
</table>





**Methods**

The following table lists the methods available in EditControl class and its purpose.

<table>
<tr>
<td>
Methods<br/><br/></td><td>
Type<br/><br/></td><td>
Description<br/><br/></td></tr>
<tr>
<td>
ExpandLine(int index)  <br/><br/></td><td>
Void<br/><br/></td><td>
a line, index in the argument refers the index of the line to be expanded (0 based value). <br/><br/></td></tr>
<tr>
<td>
ExpandLineUpTopLevel(int index)<br/><br/></td><td>
Void<br/><br/></td><td>
Expands  a line and its parent line upto the top most level. Index in the argument refers to the index of the line to be expanded (0 based value).<br/><br/></td></tr>
<tr>
<td>
GetTextRange(int start, int end)<br/><br/></td><td>
String<br/><br/></td><td>
Returns the text between Start and End lines. Start and End denotes the index of the Start and End lines <br/><br/>(0 based values).<br/><br/></td></tr>
<tr>
<td>
LoadFile()<br/><br/></td><td>
Boolean<br/><br/></td><td>
LoadFile method is used to open a file in the EditControl. It shows up a OpenFileDialog in order to select the file to be opened using EditControl and returns a boolean value stating whether file opened  is successful.<br/><br/></td></tr>
<tr>
<td>
LoadFile(string filename)<br/><br/></td><td>
Boolean<br/><br/></td><td>
This method does not display OpenFileDialog and loads the file specified as the parameter of the method. It returns a boolean value stating the file open is successful.<br/><br/></td></tr>
<tr>
<td>
SaveFile()<br/><br/></td><td>
Boolean<br/><br/></td><td>
Save method is used to save the text in the EditControl under a file name with different supported file types.<br/><br/></td></tr>
</table>





 
**Events**


The following table lists the events available in EditControl class and its purpose.


<table>
<tr>
<td>
Event<br/><br/></td><td>
Type<br/><br/></td><td>
Description<br/><br/></td></tr>
<tr>
<td>
DocumentSourceChanged<br/><br/></td><td>
PropertyChangedCallback<br/><br/></td><td>
A property changed event gets raised when the DocumentSource property value is changed.<br/><br/></td></tr>
<tr>
<td>
IntellisenseBoxOpening<br/><br/></td><td>
IntellisenseBoxEventHandler<br/><br/></td><td>
Gets raised before the Intellisense popup is displayed. This event can be used to cancel the Intellisense popup display or change ItemsSource of the Intellisense ListBox and so on.<br/><br/></td></tr>
<tr>
<td>
IntellisenseBoxClosed<br/><br/></td><td>
EventHandler<br/><br/></td><td>
This event will be raised after the Intellisense popup is closed. This event can be used to perform any operation related to Intellisense after the popup is closed.<br/><br/></td></tr>
<tr>
<td>
IntellisenseDrillDown<br/><br/></td><td>
IntellisenseBoxEventHandler<br/><br/></td><td>
Drill down in Intellisense occurs when the user types  drill down char specified in the CurrentLanguage instance. When the drill down occurs, the Intellisense looks for any sub items are available for the selected Intellisense item and displays the popup if any. This event gets raised before the Intellisense popup is displayed after a drill down char is typed by the user. This event can be used to perform any operations related to Intellisense during drill down. <br/><br/></td></tr>
<tr>
<td>
SelectedTextChanged<br/><br/></td><td>
PropertyChangedCallback<br/><br/></td><td>
A PropertyChangedCallback gets raised when the text in the EditControl is selected.<br/><br/></td></tr>
<tr>
<td>
TextChanged<br/><br/></td><td>
PropertyChangedCallback<br/><br/></td><td>
A PropertyChangedCallback get raised when the text in the EditControl gets changed.<br/><br/></td></tr>
<tr>
<td>
CaretPositionChanged<br/><br/></td><td>
EventHandler<br/><br/></td><td>
This event will be raised when the caret position of the text in the EditControl is changed. The <code>CaretPositionChanged</code> event receives the <code>CaretPositionEventArgs</code> as argument which has the following properties.
<ul>
<li> <a href="https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Edit.EditControl.html#Syncfusion_Windows_Edit_EditControl_LineNumber">Line Number :</a> Gets the current line number value of the EditControl.</li>
<li> <a href="https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Edit.EditControl.html#Syncfusion_Windows_Edit_EditControl_CursorIndex">Cursor Index :</a> Gets the current cursor index of the EditControl.</li>
</ul>
<br/><br/></td></tr>
</table>
