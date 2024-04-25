---
layout: post
title: Disable toolbar items| PDF Viewer | Wpf | Syncfusion
description: This section explains how to disable a toolbar item and contains the table showing the complete list of toolbar items and their types.
platform: wpf
control: PDF Viewer
documentation: ug
---

# Disable toolbar items

To remove the default toolbar completely, use the [PdfDocumentView](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfDocumentView.html) control instead of [PdfViewerControl](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html) as described in the [section](https://help.syncfusion.com/wpf/pdf-viewer/viewing-pdf-files#view-pdf-files-without-using-the-toolbar). 

However, an individual toolbar item can also be removed from the default toolbar of the PDF Viewer using the toolbar template and attaching an event handler to the Loaded event of the PdfViewerControl.

N> Disable the toolbar items using the **PdfViewerControl's Loaded event** so that we can effectively disable the toolbar items. This step is necessary because if the PdfViewer is not fully initialized in your code snippet, accessing the PdfViewer toolbar will result in a null reference exception.

The following code sample explains disabling the text search tool from the default toolbar.

{% tabs %}
{% highlight c# %}

PdfViewerControl pdfViewer;

public MainWindow()
{
    InitializeComponent();
    // Create a new instance of PdfViewerControl.
    pdfViewer = new PdfViewerControl();
    // Add the PdfViewerControl to the HomeGrid.
    HomeGrid.Children.Add(pdfViewer);
    // Load the specified PDF file.
    pdfViewer.Load("Document.pdf");
    // Attach an event handler to the Loaded event of the PdfViewerControl.
    pdfViewer.Loaded += pdfViewer_Loaded;
}

private void pdfViewer_Loaded(object sender, RoutedEventArgs e)
{
    // Find the DocumentToolbar element within the PdfViewerControl template.
    DocumentToolbar toolbar = pdfViewer.Template.FindName("PART_Toolbar", pdfViewer) as DocumentToolbar;

    // Hide the Text Search button within the toolbar.
    Button textSearchButton = toolbar.Template.FindName("PART_ButtonTextSearch", toolbar) as Button;
    textSearchButton.Visibility = System.Windows.Visibility.Collapsed;
}

{% endhighlight %}
{% endtabs %}

N> Apply the changes of hiding toolbar items, only after when the application window is loaded.
N> The sample project for disabling toolbar item is available in the [GitHub](https://github.com/SyncfusionExamples/WPF-PDFViewer-Examples/tree/master/Toolbar/HideToolbarItems).

Similarly, other toolbar items also can be disabled. The following table lists the template names of the rest of the toolbar items along with their respective types in the order they appear in the toolbar.

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
<td>Page separator tool</td>
<td>PART_PageSeparator</td>
<td>System.Windows.Controls.TextBlock</td>
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
<td>Annotation tools separator</td>
<td>PART_AnnotationToolsSeparator</td>
<td>System.Windows.Shapes.Rectangle</td>
</tr>
<tr>
<td>Sticky note tool</td>
<td>PART_StickyNote</td>
<td>System.Windows.Controls.Primitives.ToggleButton</td>
</tr>
<tr>
<td>Ink tool</td>
<td>PART_Ink</td>
<td>System.Windows.Controls.Primitives.ToggleButton</td>
</tr>
<tr>
<td>Ink eraser tool</td>
<td>PART_InkEraser</td>
<td>System.Windows.Controls.Primitives.ToggleButton</td>
</tr>
<tr>
<td>Text markup tool</td>
<td>PART_TextMarkup</td>
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

N> From the v18.4.0.x onwards, the file menu items such as Open, Save, Save As, and Print are not directly present in the toolbar and they are present in the context menu of the File tools toggle button.
N> From the v21.1.0.x onwards, the PDFViewer toolbar design is changed for a better user interface and visual.

Due to the changes in the toolbar design, there were some changes for a few tool templates. They are listed as follows.

## Before v21.1.0.x (Old Toolbar)

<table>
<tr>
<th>Toolbar item</th>
<th>Template name</th>
<th>Type</th>
</tr>
<tr>
<th>Zoom tools separator</th>
<th>Part_ZoomToolsSeparator_0</th>
<th>System.Windows.Shapes.Rectangle</th>
</tr>
<tr>
<th>Fit width tool</th>
<th>PART_ButtonFitWidth</th>
<th>System.Windows.Controls.Button</th>
</tr>
<tr>
<th>Fit page tool</th>
<th>PART_ButtonFitPage</th>
<th>System.Windows.Controls.Button</th>
</tr>
<tr>
<th>Zoom tools separator</th>
<th>PART_ZoomToolsSeparator_1</th>
<th>System.Windows.Shapes.Rectangle</th>
</tr>
<tr>
<th>Separator between annotation and cursor tools</th>
<th>PART_AnnotationsSeparator</th>
<th>System.Windows.Shapes.Rectangle</th>
</tr>
<tr>
<th>Marquee zoom tool</th>
<th>PART_MarqueeZoom</th>
<th>System.Windows.Controls.Primitives.ToggleButton</th>
</tr>
</table>

## After v21.1.0.x (Current Toolbar)

<table>
<tr>
<th>Toolbar item</th>
<th>Template name</th>
<th>Type</th>
</tr>
<tr>
<th>Zoom tools separator</th>
<th>PART_ZoomToolsSeparator</th>
<th>System.Windows.Shapes.Rectangle</th>
</tr>
<tr>
<th>Cursor tools separator</th>
<th>PART_CursorToolsSeparator</th>
<th>System.Windows.Shapes.Rectangle</th>
</tr>
<tr>
<th>Fit width tool</th>
<th>PART_FitWidth</th>
<th>System.Windows.Controls.ComboBoxItem</th>
</tr>
<tr>
<th>Fit page tool</th>
<th>PART_FitPage</th>
<th>System.Windows.Controls.ComboBoxItem</th>
</tr>
<tr>
<th>Marquee zoom tool</th>
<th>PART_MarqueeZoom</th>
<th>System.Windows.Controls.ComboBoxItem</th>
</tr>
<tr>
<th>Separates zoom mode and zoom percentage</th>
<th>PART_ComboBoxZoomModeSeperator</th>
<th>System.Windows.Controls.Separator</th>
</tr>
<tr>
<th>Separates zoom mode and marquee zoom</th>
<th>PART_ComboBoxMarqueeZoomSeperator</th>
<th>System.Windows.Controls.Separator</th>
</tr>
</table>

The following code sample explains disabling the combo box item, and separators present inside the combo box.

{% tabs %}
{% highlight c# %}

private void HideComboBoxTools(object sender, RoutedEventArgs e)
{
	// Get the instance of the toolbar using its template name.
    DocumentToolbar toolbar = pdfViewer.Template.FindName("PART_Toolbar", pdfViewer) as DocumentToolbar;
    // Get the Instance of the zoom level combo box using its template name.
    ComboBox comboBox = (ComboBox)toolbar.Template.FindName("PART_ComboBoxCurrentZoomLevel", toolbar); 
    // Iterates the combo box items present inside the combo box and disables them.
    for (int i = 0; i < comboBox.Items.Count; i++)
    {
        if (comboBox.Items[i] is ComboBoxItem)
        {
            ComboBoxItem item = comboBox.Items[i] as ComboBoxItem;
			if (item.Name == "PART_FitPage")
            {
                item.Visibility = System.Windows.Visibility.Collapsed;
            }
            if (item.Name == "PART_FitWidth")
            {
                item.Visibility = System.Windows.Visibility.Collapsed;
            }
            if (item.Name == "PART_MarqueeZoom")
            {
                item.Visibility = System.Windows.Visibility.Collapsed;
            }
        }
        if (comboBox.Items[i] is Separator)
        {
            Separator separator = comboBox.Items[i] as Separator;
            if (separator.Name == "PART_ComboBoxZoomModeSeperator")
            {
                separator.Visibility = System.Windows.Visibility.Collapsed;
            }
            if (separator.Name == "PART_ComboBoxMarqueeZoomSeperator")
            {
                separator.Visibility = System.Windows.Visibility.Collapsed;
            }
        }
    }
}

{% endhighlight %}
{% endtabs %}

## Disable the file menu item

The PDF Viewer allows users to disable the individual menu items present under the file menu of the toolbar. The following example code explains how to disable the open menu item from the file menu.

{% tabs %}
{% highlight c# %}

private void HideOpenTool(object sender, RoutedEventArgs e)
{
	//Get the instance of the toolbar using its template name.
	DocumentToolbar toolbar = pdfViewer.Template.FindName("PART_Toolbar", pdfViewer) as DocumentToolbar;
	//Get the instance of the file menu button using its template name.
	ToggleButton FileButton = (ToggleButton)toolbar.Template.FindName("PART_FileToggleButton", toolbar);
	//Get the instance of the file menu button context menu and the item collection.
	ContextMenu FileContextMenu = FileButton.ContextMenu;
	foreach (MenuItem FileMenuItem in FileContextMenu.Items)
	{
		//Get the instance of the open menu item using its template name and disable its visibility.
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

N> The present UI design is subject to change, based on the inclusion of new features, enhancements, and user convenience.