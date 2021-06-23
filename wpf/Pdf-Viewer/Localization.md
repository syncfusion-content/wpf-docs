---
layout: post
title: Localization in WPF Pdf Viewer control | Syncfusion
description: Learn about Localization support in Syncfusion Essential Studio WPF Pdf Viewer control, its elements and more.
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
<td>AddLayer</td>
<td>Click to add a layer.</td>
</tr>
<tr>
<td>AddSignatureLabel</td>
<td>Add signature</td>
</tr>
<tr>
<td>AddStampMessage</td>
<td>Click to add stamp</td>
</tr>
<tr>
<td>AddStickyNote</td>
<td>Add sticky note</td>
</tr>
<tr>
<td>Appearance</td>
<td>Appearance</td>
</tr>
<tr>
<td>ApplyLabel</td>
<td>Apply</td>
</tr>
<tr>
<td>ApplyRedactionLabel</td>
<td>Apply</td>
</tr>
<tr>
<td>ApplyRedactionMessage</td>
<td>Click to permanently remove marked content.</td>
</tr>
<tr>
<td>Arrow</td>
<td>Arrow</td>
</tr>
<tr>
<td>Author</td>
<td>Author</td>
</tr>
<tr>
<td>BackgroundColor</td>
<td>Background Color</td>
</tr>
<tr>
<td>BookmarkNotExists</td>
<td>This bookmark destination doesn't exist</td>
</tr>
<tr>
<td>BookmarkTitle</td>
<td>Bookmarks</td>
</tr>
<tr>
<td>BorderColor</td>
<td>Border Color</td>
</tr>
<tr>
<td>BorderStyle</td>
<td>Border Style</td>
</tr>
<tr>
<td>BorderThickness</td>
<td>Border Thickness</td>
</tr>
<tr>
<td>BrowseButtonHeaderText</td>
<td>Add Stamp</td>
</tr>
<tr>
<td>Butt</td>
<td>Butt</td>
</tr>
<tr>
<td>Cancel</td>
<td>Cancel</td>
</tr>
<tr>
<td>ClearLabel</td>
<td>Clear</td>
</tr>
<tr>
<td>CloseBookmark</td>
<td>Click to close the bookmark pane</td>
</tr>
<tr>
<td>Closed</td>
<td>Closed</td>
</tr>
<tr>
<td>CloseFontPopUp</td>
<td>Click to close the text properties</td>
</tr>
<tr>
<td>CloseFormOptionsMessage</td>
<td>Close form options</td>
</tr>
<tr>
<td>CloseLayer</td>
<td>Click to close the layer pane</td>
</tr>
<tr>
<td>ClosePageOrganizerMessage</td>
<td>Click to close organize pages pane.</td>
</tr>
<tr>
<td>CloseRedactionMessage</td>
<td>Close redact</td>
</tr>
<tr>
<td>CloseSearchBar</td>
<td>Close Search Bar</td>
</tr>
<tr>
<td>CloseThumbnail</td>
<td>Click to close the thumbnail pane</td>
</tr>
<tr>
<td>Cloud</td>
<td>Cloud</td>
</tr>
<tr>
<td>Color</td>
<td>Color</td>
</tr>
<tr>
<td>ColorPicker</td>
<td>Color picker</td>
</tr>
<tr>
<td>Comment</td>
<td>Comment</td>
</tr>
<tr>
<td>ConfirmationBeforeClose</td>
<td>Do you want to save changes before closing?</td>
</tr>
<tr>
<td>Copy</td>
<td>Copy</td>
</tr>
<tr>
<td>CounterclockwiseMessage</td>
<td>Rotate counterclockwise</td>
</tr>
<tr>
<td>CreateSignatureLabel</td>
<td>Create signature</td>
</tr>
<tr>
<td>CurrentPageNumber</td>
<td>Current page index</td>
</tr>
<tr>
<td>CustomStampHeaderText</td>
<td>Custom Stamps</td>
</tr>
<tr>
<td>CustomTextLabel</td>
<td>Custom text</td>
</tr>
<tr>
<td>DecreaseMagnification</td>
<td>Click to decrease the magnification of the entire page.</td>
</tr>
<tr>
<td>Delete</td>
<td>Delete</td>
</tr>
<tr>
<td>DeleteLayer</td>
<td>Click to delete a layer</td>
</tr>
<tr>
<td>DeletePagesConfirmation</td>
<td>Are you sure you want to delete the pages from the document?</td>
</tr>
<tr>
<td>DeletePagesLimitation</td>
<td>You cannot delete all pages. At least one page should remain</td>
</tr>
<tr>
<td>DeletePagesMesage</td>
<td>Delete pages</td>
</tr>
<tr>
<td>Diamond</td>
<td>Diamond</td>
</tr>
<tr>
<td>DocumentProtected</td>
<td>This document is protected. Please enter a document Open Password.</td>
</tr>
<tr>
<td>DrawCircle</td>
<td>Circle</td>
</tr>
<tr>
<td>DrawingTools</td>
<td>Drawing Tools</td>
</tr>
<tr>
<td>DrawInk</td>
<td>Draw free form</td>
</tr>
<tr>
<td>DrawLine</td>
<td>Line</td>
</tr>
<tr>
<td>DrawPolygon</td>
<td>Polygon</td>
</tr>
<tr>
<td>DrawPolyline</td>
<td>Polyline</td>
</tr>
<tr>
<td>DrawRectangle</td>
<td>Rectangle</td>
</tr>
<tr>
<td>EnableMultiplePageSelection</td>
<td>Enable multiple page selection</td>
</tr>
<tr>
<td>End</td>
<td>End</td>
</tr>
<tr>
<td>EnlargePageThumbnails</td>
<td>Enlarge page thumbnails</td>
</tr>
<tr>
<td>EnterPassword</td>
<td>Enter password</td>
</tr>
<tr>
<td>Error</td>
<td>Error</td>
</tr>
<tr>
<td>EssentialPdfViewer</td>
<td>Essential Pdf Viewer</td>
</tr>
<tr>
<td>ExportDataMessage</td>
<td>Export data from a Form file</td>
</tr>
<tr>
<td>FileAlreadyOpenedInformation</td>
<td>This file is already opened. Please close it before saving</td>
</tr>
<tr>
<td>FilesViewMessage</td>
<td>Click to open, save and print a PDF Document</td>
</tr>
<tr>
<td>FileText</td>
<td>File</td>
</tr>
<tr>
<td>FillColor</td>
<td>Fill color</td>
</tr>
<tr>
<td>FillOpacityLabel</td>
<td>Fill opacity</td>
</tr>
<tr>
<td>FitPage</td>
<td>Click to show one page at a time.</td>
</tr>
<tr>
<td>FitWidth</td>
<td>Click to fill the window with each page and scroll through pages continuously.</td>
</tr>
<tr>
<td>FontColorLabel</td>
<td>Font color</td>
</tr>
<tr>
<td>FontLabel</td>
<td>Font</td>
</tr>
<tr>
<td>FontSizeLabel</td>
<td>Font size</td>
</tr>
<tr>
<td>FormDataLabel</td>
<td>Form Data</td>
</tr>
<tr>
<td>FormDataMessage</td>
<td>Form Data</td>
</tr>
<tr>
<td>FormExportLabel</td>
<td>Export</td>
</tr>
<tr>
<td>FormImportLabel</td>
<td>Import</td>
</tr>
<tr>
<td>FreeText</td>
<td>Free Text</td>
</tr>
<tr>
<td>FreeTextBox</td>
<td>Add text box</td>
</tr>
<tr>
<td>FreeTextProperties</td>
<td>Free text properties</td>
</tr>
<tr>
<td>General</td>
<td>General</td>
</tr>
<tr>
<td>GoToFirstPage</td>
<td>Click to go to first page in the document.</td>
</tr>
<tr>
<td>GoToLastPage</td>
<td>Click to go to last page in the document.</td>
</tr>
<tr>
<td>GoToNextPage</td>
<td>Click to go to next page in the document.</td>
</tr>
<tr>
<td>GoToPreviousPage</td>
<td>Click to go to previous page in the document.</td>
</tr>
<tr>
<td>HandwrittenSignatureMessage</td>
<td>Sign document by drawing a signature.</td>
</tr>
<tr>
<td>HandwrittenSignaturePropertiesLabel</td>
<td>Handwritten signature properties</td>
</tr>
<tr>
<td>Help</td>
<td>Help</td>
</tr>
<tr>
<td>Highlight</td>
<td>Highlight</td>
</tr>
<tr>
<td>HighlightProperties</td>
<td>Highlight properties</td>
</tr>
<tr>
<td>HighlightText</td>
<td>Highlight text</td>
</tr>
<tr>
<td>Icon</td>
<td>Icon</td>
</tr>
<tr>
<td>ImportDataMessage</td>
<td>Import data into a Form file</td>
</tr>
<tr>
<td>IncorrectNumericEntry</td>
<td>Invalid numeric value</td>
</tr>
<tr>
<td>IncorrectPassword</td>
<td>Incorrect password</td>
</tr>
<tr>
<td>IncreaseMagnification</td>
<td>Click to increase the magnification of the entire page.</td>
</tr>
<tr>
<td>Information</td>
<td>Information</td>
</tr>
<tr>
<td>Ink</td>
<td>Ink</td>
</tr>
<tr>
<td>InkEraser</td>
<td>Click to erase a part of the ink annotation (freehand drawings)</td>
</tr>
<tr>
<td>InkProperties</td>
<td>Ink properties</td>
</tr>
<tr>
<td>InsertText</td>
<td>Insert Text</td>
</tr>
<tr>
<td>InvalidPasswordError</td>
<td>Password is invalid</td>
</tr>
<tr>
<td>Key</td>
<td>Key</td>
</tr>
<tr>
<td>LayerTitle</td>
<td>Layers</td>
</tr>
<tr>
<td>LineProperties</td>
<td>Line properties</td>
</tr>
<tr>
<td>LoadingPage</td>
<td>Loading Pages</td>
</tr>
<tr>
<td>MakeDefault</td>
<td>Make properties default</td>
</tr>
<tr>
<td>MarkForRedactionLabel</td>
<td>Mark for Redaction</td>
</tr>
<tr>
<td>MarkForRedactionMessage</td>
<td>Click to mark content for permanent removal.</td>
</tr>
<tr>
<td>MarqueeZoom</td>
<td>Zoom to selected area</td>
</tr>
<tr>
<td>MatchCase</td>
<td>Match Case</td>
</tr>
<tr>
<td>Message</td>
<td>Message</td>
</tr>
<tr>
<td>Modified</td>
<td>Modified</td>
</tr>
<tr>
<td>MoreActions</td>
<td>Click to view more actions</td>
</tr>
<tr>
<td>NewParagraph</td>
<td>New Paragraph</td>
</tr>
<tr>
<td>Next</td>
<td>Next</td>
</tr>
<tr>
<td>NoMatchesFound</td>
<td>Reader has finished searching the document. No matches were found</td>
</tr>
<tr>
<td>NoMoreMatchesFound</td>
<td>Reader has finished searching the document. No more matches were found</td>
</tr>
<tr>
<td>None</td>
<td>None</td>
</tr>
<tr>
<td>Note</td>
<td>Note</td>
</tr>
<tr>
<td>Of</td>
<td>of</td>
</tr>
<tr>
<td>Ok</td>
<td>OK</td>
</tr>
<tr>
<td>Opacity</td>
<td>Opacity</td>
</tr>
<tr>
<td>Open</td>
<td>Open</td>
</tr>
<tr>
<td>OpenDocument</td>
<td>Click to open a PDF Document</td>
</tr>
<tr>
<td>OpenHeaderText</td>
<td>Open</td>
</tr>
<tr>
<td>OpenPopupNote</td>
<td>Open Pop-up Note</td>
</tr>
<tr>
<td>OutlineColorLabel</td>
<td>Outline color</td>
</tr>
<tr>
<td>Oval</td>
<td>Oval</td>
</tr>
<tr>
<td>OvalProperties</td>
<td>Oval properties</td>
</tr>
<tr>
<td>OverlayTextTitleLabel</td>
<td>Overlay text</td>
</tr>
<tr>
<td>PageCount</td>
<td>Total page count</td>
</tr>
<tr>
<td>PageNotExists</td>
<td>There is no page numbered '{0}' in this document</td>
</tr>
<tr>
<td>PageOrganizerTitle</td>
<td>Organize Pages</td>
</tr>
<tr>
<td>Panning</td>
<td>Click to pan around the document</td>
</tr>
<tr>
<td>Paragraph</td>
<td>Paragraph</td>
</tr>
<tr>
<td>PasswordCancelButton</td>
<td>Cancel</td>
</tr>
<tr>
<td>PasswordOkButton</td>
<td>OK</td>
</tr>
<tr>
<td>PolygonalLine</td>
<td>Polygonal Line</td>
</tr>
<tr>
<td>PolygonLineProperties</td>
<td>Polygon line properties</td>
</tr>
<tr>
<td>PolygonProperties</td>
<td>Polygon properties</td>
</tr>
<tr>
<td>Previous</td>
<td>Previous</td>
</tr>
<tr>
<td>PrintDocument</td>
<td>Click to Print this PDF file or pages from it.</td>
</tr>
<tr>
<td>PrintHeaderText</td>
<td>Print</td>
</tr>
<tr>
<td>Properties</td>
<td>Properties</td>
</tr>
<tr>
<td>RectangleProperties</td>
<td>Rectangle properties</td>
</tr>
<tr>
<td>RedactedAreaFillLabel</td>
<td>Redacted area fill color</td>
</tr>
<tr>
<td>RedactionConfirmation</td>
<td>Are you sure you want to continue?</td>
</tr>
<tr>
<td>RedactionLabel</td>
<td>Redaction</td>
</tr>
<tr>
<td>RedactionMarkAppearancelabel</td>
<td>Redaction mark appearance</td>
</tr>
<tr>
<td width="238">RedactionMessage</td>
<td width="930">Click to perform redaction.</td>
</tr>
<tr>
<td>RedactionPropertiesLabel</td>
<td>Redaction tool properties</td>
</tr>
<tr>
<td>RedactionPropertiesMessage</td>
<td>Click to view redaction tool properties.</td>
</tr>
<tr>
<td>RedactionWarning</td>
<td>You are about to permanently remove all content that has been marked for redaction. Once the document is saved, this operation cannot be undone</td>
</tr>
<tr>
<td>ReducePageThumbnails</td>
<td>Reduce page thumbnails</td>
</tr>
<tr>
<td>Rename</td>
<td>Rename</td>
</tr>
<tr>
<td>RequestCorrectPassword</td>
<td>Please open the document again and enter the correct password</td>
</tr>
<tr>
<td>ReversedClose</td>
<td>Closed (Reverse)</td>
</tr>
<tr>
<td>ReversedOpen</td>
<td>Open (Reverse)</td>
</tr>
<tr>
<td>RotateClockwiseMessage</td>
<td>Rotate clockwise</td>
</tr>
<tr>
<td>Round</td>
<td>Round</td>
</tr>
<tr>
<td>SaveAsDocument</td>
<td>Click to save the document in the local disk</td>
</tr>
<tr>
<td>SaveAsHeaderText</td>
<td>Save As</td>
</tr>
<tr>
<td>SaveDocument</td>
<td>Click to save the document in the local disk</td>
</tr>
<tr>
<td>SaveHeaderText</td>
<td>Save</td>
</tr>
<tr>
<td>SearchIndicator</td>
<td>Searching</td>
</tr>
<tr>
<td>SearchText</td>
<td>Click to search text</td>
</tr>
<tr>
<td>SelectionTool</td>
<td>Selection tool for text</td>
</tr>
<tr>
<td>Slash</td>
<td>Slash</td>
</tr>
<tr>
<td>Square</td>
<td>Square</td>
</tr>
<tr>
<td>Stamp</td>
<td>Stamp</td>
</tr>
<tr>
<td>StampPropertiesLabel</td>
<td>Stamp properties</td>
</tr>
<tr>
<td>StandardLabel</td>
<td>Standard Business</td>
</tr>
<tr>
<td>Start</td>
<td>Start</td>
</tr>
<tr>
<td>StickyNote</td>
<td>Sticky Note</td>
</tr>
<tr>
<td>StickyNoteProperties</td>
<td>Sticky note properties</td>
</tr>
<tr>
<td>StrikeoutProperties</td>
<td>Strikethrough properties</td>
</tr>
<tr>
<td>StrikeoutText</td>
<td>Strikethrough text</td>
</tr>
<tr>
<td>Strikethrough</td>
<td>Strikethrough</td>
</tr>
<tr>
<td>Subject</td>
<td>Subject</td>
</tr>
<tr>
<td>TextProperties</td>
<td>Text properties</td>
</tr>
<tr>
<td>Thickness</td>
<td>Thickness</td>
</tr>
<tr>
<td>ThumbnailTitle</td>
<td>Page Thumbnails</td>
</tr>
<tr>
<td>Underline</td>
<td>Underline</td>
</tr>
<tr>
<td>UnderlineProperties</td>
<td>Underline properties</td>
</tr>
<tr>
<td>UnderlineText</td>
<td>Underline text</td>
</tr>
<tr>
<td>UseOverlayTextLabel</td>
<td>Use overlay text</td>
</tr>
<tr>
<td>ValueExceedsLimit</td>
<td>The value must be between {0} and {1}</td>
</tr>
<tr>
<td>ViewBookmarks</td>
<td>Click to view the bookmarks</td>
</tr>
<tr>
<td>ViewLayers</td>
<td>Click to view the layers</td>
</tr>
<tr>
<td>ViewPageOrganizerMessage</td>
<td>Rotate, rearrange, or delete pages</td>
</tr>
<tr>
<td>ViewThumbnails</td>
<td>Click to view the thumbnails</td>
</tr>
<tr>
<td>Warning</td>
<td>Warning</td>
</tr>
<tr>
<td>ZoomLevel</td>
<td>Current zoom level</td>
</tr>
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
