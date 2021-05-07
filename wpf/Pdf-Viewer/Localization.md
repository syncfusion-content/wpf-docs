---
layout: post
title: Localization in WPF Pdf Viewer control | Syncfusion
description: Learn about Localization support in Syncfusion WPF Pdf Viewer control, its elements and more details.
platform: wpf
control: PDF Viewer
documentation: ug
---

# Localization in WPF Pdf Viewer

Localization is the process of configuring the application to a specific language. `PdfViewerControl` provides support to localize all the static text used for tooltip and context menu contents. Localization can be done by adding resource file (Resx) in the application.
The following table shows the default values for the common text used in the `PdfViewerControl` which is in `en-US` culture:

<table>
<tr>
<th>
Name</th><th>
Value</th></tr>
<tr>
<td>
AddLayer</td><td>
Click to add a layer</td></tr>
<tr>
<td>
Appearance</td><td>
Appearance</td></tr>
<tr>
<td>
Author</td><td>
Author</td></tr>
<tr>
<td>
BackgroundColor</td><td>
Background Color :</td></tr>
<tr>
<td>
BookmarkTitle</td><td>
Bookmarks</td></tr>
<tr>
<td>
BorderColor</td><td>
Border Color :</td></tr>
<tr>
<td>
BorderThickness</td><td>
Border Thickness :</td></tr>
<tr>
<td>
Cancel</td><td>
Cancel</td></tr>
<tr>
<td>
CloseBookmark</td><td>
Click to close the bookmark pane</td></tr>
<tr>
<td>
CloseFontPopUp</td><td>
Click to close the text properties</td></tr>
<tr>
<td>
CloseLayer</td><td>
Click to close the layer pane</td></tr>
<tr>
<td>
CloseSearchBar</td><td>
Close Search Bar</td></tr>
<tr>
<td>
CloseThumbnail</td><td>
Click to close the thumbnail pane</td></tr>
<tr>
<td>
Color</td><td>
Color :</td></tr>
<tr>
<td>
ColorPicker</td><td>
Color Picker</td></tr>
<tr>
<td>
Copy</td><td>
Copy</td></tr>
<tr>
<td>
CurrentPageNumber</td><td>
Current page index</td></tr>
<tr>
<td>
DecreaseMagnification</td><td>
Click to decrease the magnification of the entire page.</td></tr>
<tr>
<td>
Delete</td><td>
Delete</td></tr>
<tr>
<td>
DeleteLayer</td><td>
Click to delete a layer</td></tr>
<tr>
<td>
DocumentProtected</td><td>
This document is protected. Please enter a Document Open Password.</td></tr>
<tr>
<td>
DrawCircle</td><td>
Circle</td></tr>
<tr>
<td>
DrawingTools</td><td>
Drawing Tools</td></tr>
<tr>
<td>
DrawInk</td><td>
Draw free form</td></tr>
<tr>
<td>
DrawLine</td><td>
Line</td></tr>
<tr>
<td>
DrawRectangle</td><td>
Rectangle</td></tr>
<tr>
<td>
EnlargePageThumbnails</td><td>
Enlarge page thumbnails</td></tr>
<tr>
<td>
EnterPassword</td><td>
Enter Password:</td></tr>
<tr>
<td>
EssentialPdfViewer</td><td>
Essential Pdf Viewer</td></tr>
<tr>
<td>
FillColor</td><td>
FillColor :</td></tr>
<tr>
<td>
FitPage</td><td>
Click to show one page at a time.</td></tr>
<tr>
<td>
FitWidth</td><td>
Click to fill the window with each page and scroll through pages continuously.</td></tr>
<tr>
<td>
FreeTextBox</td><td>
Add text box</td></tr>
<tr>
<td>
FreeTextProperties</td><td>
Free Text Properties</td></tr>
<tr>
<td>
General</td><td>
General</td></tr>
<tr>
<td>
GoToFirstPage</td><td>
Click to go to first page in the document.</td></tr>
<tr>
<td>
GoToLastPage</td><td>
Click to go to last page in the document.</td></tr>
<tr>
<td>
GoToNextPage</td><td>
Click to go to next page in the document.</td></tr>
<tr>
<td>
GoToPreviousPage</td><td>
Click to go to previous page in the document.</td></tr>
<tr>
<td>
HighlightProperties</td><td>
Highlight Properties</td></tr>
<tr>
<td>
HighlightText</td><td>
Highlight text</td></tr>
<tr>
<td>
IncreaseMagnification</td><td>
Click to increase the magnification of the entire page.</td></tr>
<tr>
<td>
InkProperties</td><td>
Ink Properties</td></tr>
<tr>
<td>
LayerTitle</td><td>
Layers</td></tr>
<tr>
<td>
LineProperties</td><td>
Line Properties</td></tr>
<tr>
<td>
MakeDefault</td><td>
Make Properties Default</td></tr>
<tr>
<td>
MatchCase</td><td>
Match Case</td></tr>
<tr>
<td>
Modified</td><td>
Modified</td></tr>
<tr>
<td>
Next</td><td>
Next</td></tr>
<tr>
<td>
NoMatchesFound</td><td>
Reader has finished searching the document. No matches were found</td></tr>
<tr>
<td>
Of</td><td>
of</td></tr>
<tr>
<td>
Ok</td><td>
Ok</td></tr>
<tr>
<td>
Opacity</td><td>
Opacity (%) :</td></tr>
<tr>
<td>
OpenDocument</td><td>
Click to open a PDF Document</td></tr>
<tr>
<td>
OpenPopupNote</td><td>
Open Pop-up Note</td></tr>
<tr>
<td>
OvalProperties</td><td>
Oval Properties</td></tr>
<tr>
<td>
PageCount</td><td>
Total page count</td></tr>
<tr>
<td>
PasswordCancelButton</td><td>
Cancel</td></tr>
<tr>
<td>
PasswordOkButton</td><td>
OK</td></tr>
<tr>
<td>
Previous</td><td>
Previous</td></tr>
<tr>
<td>
PrintDocument</td><td>
Click to Print this PDF file or pages from it.</td></tr>
<tr>
<td>
Properties</td><td>
Properties</td></tr>
<tr>
<td>
RectangleProperties</td><td>
Rectangle Properties</td></tr>
<tr>
<td>
ReducePageThumbnails</td><td>
Reduce page thumbnails</td></tr>
<tr>
<td>
Rename</td><td>
Rename</td></tr>
<tr>
<td>
SaveDocument</td><td>
Click to save the document in the local disk</td></tr>
<tr>
<td>
SearchIndicator</td><td>
Searching</td></tr>
<tr>
<td>
SearchText</td><td>
Click to search text</td></tr>
<tr>
<td>
StrikeoutProperties</td><td>
StrikeOut Properties</td></tr>
<tr>
<td>
StrikeoutText</td><td>
Strikethrough text</td></tr>
<tr>
<td>
Subject</td><td>
Subject</td></tr>
<tr>
<td>
TextProperties</td><td>
Text Properties</td></tr>
<tr>
<td>
Thickness</td><td>
Thickness :</td></tr>
<tr>
<td>
ThumbnailTitle</td><td>
Page Thumbnails</td></tr>
<tr>
<td>
UnderlineProperties</td><td>
Underline Properties</td></tr>
<tr>
<td>
UnderlineText</td><td>
Underline text</td></tr>
<tr>
<td>
ViewBookmarks</td><td>
Click to view the bookmarks</td></tr>
<tr>
<td>
ViewLayers</td><td>
Click to view the layers</td></tr>
<tr>
<td>
ViewThumbnails</td><td>
Click to view the thumbnails</td></tr>
<tr>
<td>
ZoomLevel</td><td>
Current zoom level</td></tr>
</table>

## Adding Resource file

* Create a folder names `Resources` in your application.
* Add default English (“en-US”) [Resx](https://github.com/syncfusion/wpf-controls-localization-resx-files/blob/master/Syncfusion.PdfViewer.WPF/Syncfusion.PdfViewer.WPF.resx) (resource) file of `PdfViewerControl` in `Resources` folder named as Syncfusion.PdfViewer.WPF.resx.
* Create a Resx (resource) files and named as Syncfusion.PdfViewer.WPF.[Culture name].resx. For example, Syncfusion.PdfViewer.WPF.fr.resx for French culture. 
* Add the resource key such as `OpenDocument` and its corresponding localized value in Syncfusion.PdfViewer.WPF.fr.resx file. Refer the below screenshot for the same.
* Execute the application in the French culture to see the changes.

![Resource file](Localization_images/Localization_image2.png)

The following screenshot shows the `PdfViewerControl` in French language

![Localization](Localization_images/Localization_image1.png)

## Localize Resource File with Different Assembly or Namespace

In general, [PdfViewerControl](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html) try to read the resource file from executing assembly and its default namespace by using [Assembly.GetExecuteAssembly](https://msdn.microsoft.com/en-us/library/system.reflection.assembly.getexecutingassembly.aspx) method. When the resource file is located at different assembly or namespace, then it can be set to the [PdfViewerControl](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html) by using `LocalizationManager.SetResources` method.

{% tabs %}
{% highlight c# %}
public MainWindow()
{
    Thread.CurrentThread.CurrentUICulture = new System.Globalization.CultureInfo("fr-FR");
	
	// Set the Custom assembly and namespace for the localization.
	LocalizationManager.SetResources(typeof(Custom_Class).Assembly, "ClassLibrary");
    InitializeComponent();
}    
{% endhighlight %}
{% endtabs %}
