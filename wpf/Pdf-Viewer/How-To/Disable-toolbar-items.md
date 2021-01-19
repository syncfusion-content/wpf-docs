---
layout: post
title: Disable toolbar items| PDF Viewer | Wpf | Syncfusion
description: This section explains how to disable a toolbar item and contains the table showing the complete list of toolbar items and their types.
platform: wpf
control: PDF Viewer
documentation: ug
---

# Disable toolbar items

To remove the default toolbar completely, use [PdfDocumentView](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfDocumentView.html) control instead of [PdfViewerControl](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html) as described in the [View PDF files without using the toolbar](https://help.syncfusion.com/wpf/pdf-viewer/viewing-pdf-files#view-pdf-files-without-using-the-toolbar) section. 

However, an individual toolbar item can also be removed from the default toolbar of PDF Viewer using the toolbar template. The following code snippet illustrates disabling the <b>text search tool</b> from the default toolbar.

{% tabs %}
{% highlight c# %}

        private void MainWindow_Loaded(object sender, RoutedEventArgs e)
        {
            //Get the instance of the toolbar using its template name
            DocumentToolbar toolbar = pdfViewer.Template.FindName("PART_Toolbar", pdfViewer) as DocumentToolbar;

            //Get the instance of the open file button using its template name
            Button textSearchButton = (Button)toolbar.Template.FindName("PART_ButtonTextSearch", toolbar);

            //Set the visibility of the button to collapsed 
            textSearchButton.Visibility = System.Windows.Visibility.Collapsed;
        }

{% endhighlight %}
{% endtabs %}

Similarly, other toolbar items can be disabled. The following table lists the template names of the rest of the toolbar items along with their respective types in the order they appear in the toolbar.

<table>
<tr>
<th>Toolbar item</th>
<th>Template name</th>
<th>Type</th>
</tr>
<tr>
<td>File tool</td>
<td>PART_FileToggleButton</td>
<td>System.Windows.Controls.Primitives.ToggleButton</td>
</tr>
<tr>
<td>Navigation tools separator</td>
<td>Part_NavigationToolsSeparator</td>
<td>System.Windows.Shapes.Rectangle</td>
</tr>
<tr>
<td>First page tool</td>
<td>PART_ButtonGoToFirstPage</td>
<td>System.Windows.Controls.Button</td>
</tr>
<tr>
<td>Previous page tool</td>
<td>PART_ButtonGoToPreviousPage</td>
<td>System.Windows.Controls.Button</td>
</tr>
<tr>
<td>Current page number tool</td>
<td>PART_TextCurrentPageIndex</td>
<td>System.Windows.Controls.TextBox</td>
</tr>
<tr>
<td>Page count tool</td>
<td>PART_LabelTotalPageCount</td>
<td>System.Windows.Controls.TextBlock</td>
</tr>
<tr>
<td>Next page tool</td>
<td>PART_ButtonGoToNextPage</td>
<td>System.Windows.Controls.Button</td>
</tr>
<tr>
<td>Last page tool</td>
<td>PART_ButtonGoToLastPage</td>
<td>System.Windows.Controls.Button</td>
</tr>
<tr>
<td>Zoom tools separator</td>
<td>Part_ZoomToolsSeparator_0</td>
<td>System.Windows.Shapes.Rectangle</td>
</tr>
<tr>
<td>Current zoom level tool</td>
<td>PART_ComboBoxCurrentZoomLevel</td>
<td>System.Windows.Controls.ComboBox</td>
</tr>
<tr>
<td>Zoom in tool</td>
<td>PART_ButtonZoomIn</td>
<td>System.Windows.Controls.Button</td>
</tr>
<tr>
<td>Zoom out tool</td>
<td>PART_ButtonZoomOut</td>
<td>System.Windows.Controls.Button</td>
</tr>
<tr>
<td>Zoom tools separator</td>
<td>PART_ZoomToolsSeparator_1</td>
<td>System.Windows.Shapes.Rectangle</td>
</tr>
<tr>
<td>Fit width tool</td>
<td>PART_ButtonFitWidth</td>
<td>System.Windows.Controls.Button</td>
</tr>
<tr>
<td>Fit page tool</td>
<td>PART_ButtonFitPage</td>
<td>System.Windows.Controls.Button</td>
</tr>
<tr>
<td>Annotation tools separator</td>
<td>PART_AnnotationToolsSeparator</td>
<td>System.Windows.Shapes.Rectangle</td>
</tr>
<tr>
<td>Ink tool</td>
<td>PART_Ink</td>
<td>System.Windows.Controls.Primitives.ToggleButton</td>
</tr>
<tr>
<td>Highlight tool</td>
<td>PART_Highlight</td>
<td>System.Windows.Controls.Primitives.ToggleButton</td>
</tr>
<tr>
<td>Underline tool</td>
<td>PART_Underline</td>
<td>System.Windows.Controls.Primitives.ToggleButton</td>
</tr>
<tr>
<td>Strikethrough tool</td>
<td>PART_Strikethrough</td>
<td>System.Windows.Controls.Primitives.ToggleButton</td>
</tr>
<tr>
<td>Shapes tool</td>
<td>PART_Shapes</td>
<td>System.Windows.Controls.Primitives.ToggleButton</td>
</tr>
<tr>
<td>Fill tool</td>
<td>PART_Fill</td>
<td>System.Windows.Controls.Primitives.ToggleButton</td>
</tr>
<tr>
<td>Add textbox tool</td>
<td>PART_FreeText</td>
<td>System.Windows.Controls.Primitives.ToggleButton</td>
</tr>
<tr>
<td>Text properties tool</td>
<td>PART_ButtonTextBoxFont</td>
<td>System.Windows.Controls.Button</td>
</tr>
<tr>
<td>Separator between the annotation and cursor tools</td>
<td>PART_AnnotationsSeparator</td>
<td>System.Windows.Shapes.Rectangle</td>
</tr>
<tr>
<td>Stamp tool</td>
<td>PART_Stamp</td>
<td>System.Windows.Controls.Primitives.ToggleButton</td>
</tr>
<tr>
<td>Handwritten signature tool</td>
<td>PART_ButtonSignature</td>
<td>System.Windows.Controls.Button</td>
</tr>
<tr>
<td>Select tool</td>
<td>PART_SelectTool</td>
<td>System.Windows.Controls.Primitives.ToggleButton</td>
</tr>
<tr>
<td>Hand tool</td>
<td>PART_HandTool</td>
<td>System.Windows.Controls.Primitives.ToggleButton</td>
</tr>
<tr>
<td>Marquee zoom tool</td>
<td>PART_MarqueeZoom</td>
<td>System.Windows.Controls.Primitives.ToggleButton</td>
</tr>
<tr>
<td>Separator between the cursor tools and text search button</td>
<td>Part_CursorTools</td>
<td>System.Windows.Shapes.Rectangle</td>
</tr>
<tr>
<td>Text search tool</td>
<td>PART_ButtonTextSearch</td>
<td>System.Windows.Controls.Button</td>
</tr>
</table>

N> From v18.4.0.x onwards, the file menu items such as the Open, Save, Save As, and Print are not directly present in the toolbar and they are present in the context menu of File tools toggle button.

The following code snippet illustrates disabling the Open tool from the menu.

{% tabs %}
{% highlight c# %}

private void MainWindow_Loaded(object sender, RoutedEventArgs e)
{
	//Get the instance of the toolbar using its template name
	DocumentToolbar toolbar = pdfViewer.Template.FindName("PART_Toolbar", pdfViewer) as DocumentToolbar;

	//Get the instance of the file menu button using its template name
	ToggleButton FileButton = (ToggleButton)toolbar.Template.FindName("PART_FileToggleButton", toolbar);

	//Get the instance of the file menu button context menu and the item collection
	ContextMenu FileContextMenu = FileButton.ContextMenu;
	foreach (MenuItem FileMenuItem in FileContextMenu.Items)
	{
		//Get the instance of the open menu item using its template name and disable its visibility
		if (FileMenuItem.Name == "PART_OpenMenuItem")
			FileMenuItem.Visibility = System.Windows.Visibility.Collapsed;
	}
}

{% endhighlight %}
{% endtabs %}

Similarly, other file menu items can be disabled. The following table lists the template names along with their respective types in the order they appear in the context menu.

<table>
<tr>
<th>Toolbar item</th>
<th>Template name</th>
<th>Type</th>
</tr>
<tr>
<td>Open tool</td>
<td>PART_OpenMenuItem</td>
<td>System.Windows.Controls.MenuItem</td>
</tr>
<tr>
<td>Save tool</td>
<td>PART_SaveMenuItem</td>
<td>System.Windows.Controls.MenuItem</td>
</tr>
<tr>
<td>SaveAs tool</td>
<td>PART_SaveAsMenuItem</td>
<td>System.Windows.Controls.MenuItem</td>
</tr>
<tr>
<td>Print tool</td>
<td>PART_PrintMenuItem</td>
<td>System.Windows.Controls.MenuItem</td>
</tr>
</table>