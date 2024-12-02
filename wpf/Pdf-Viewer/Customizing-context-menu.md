---
layout: post
title: Customizing context menu in WPF Pdf Viewer | Syncfusion
description: Learn about Customizing context menu support in Syncfusion WPF Pdf Viewer control, its elements and more.
platform: wpf
control: PDF Viewer
documentation: ug
---

# Customization support for context menu in WPF PdfViewer

PDF Viewer now supports customization of the default context menu items. This gives users more options to adjust the viewer to fit their application's requirements. Previously, the context menus for Annotation, Text Selection, Redaction, and Signature Field did not allow modifications. With this enhancement, users can add, remove, and hide the default menu items.This also supports a few events that are listed in the following table.

### Events Table

<table>
<tr>
<th>
Event </th><th>
Description </th><th>
Arguments </th></tr>
<tr>
<td>
ContextMenuOpening Event</td><td>
This Triggered before the context menu is displayed,this event allows users to dynamically modify menu items.</td><td>
ContextMenuOpeningEventArgs</td></tr>
<tr>
<td>
ContextMenuItemClicked Event</td><td>
This event is triggered when a menu item is clicked,this event enables users to handle menu actions programmatically.</td><td>
ContextMenuItemClickedEventArgs</td></tr>
</table>

## How to customize the contextMenu items before opening.
The `ContextMenuOpening` Event allows users to customize and manage context menus dynamically based on the source type where the context menu is triggered. This event provides the flexibility to modify, add, or suppress menu items based on the specific operation.

{% tabs %}
{% highlight c# %}

//Wire the `ContextMenuOpening` event.
pdfViewer.ContextMenuOpening += PdfViewer_ContextMenuOpening;

{% endhighlight %}
{% endtabs %}

Using the `ContextMenuOpeningEventArgs`, you can add,remove or hide context menu items.
Please refer to the following example for more details.
### Add the context menu item.

{% tabs %}
{% highlight c# %}
  private void PdfViewer_ContextMenuOpening(object sender, ContextMenuOpeningEventArgs e)
  {
      if (e.Source == "Annotation")
      {
          e.MenuItems.Add(new ContextMenuItem { Content = "Custom Annotation Item" });
      }
      if (e.Source == "Redaction")
      {
          e.MenuItems.Add(new ContextMenuItem { Content = "Custom Redaction Item" });
      }
      if (e.Source == "Text Selection")
      {
          e.MenuItems.Add(new ContextMenuItem { Content = "Custom TextSelection Item" });
      }
      if(e.Source == "Signature Field")
      {
          e.MenuItems.Add(new ContextMenuItem { Content = "Custom SignatureField Item" });
      }
  }

{% endhighlight %}
{% endtabs %}

### Remove the context menu item.

{% tabs %}
{% highlight c# %}
  private void PdfViewer_ContextMenuOpening(object sender, ContextMenuOpeningEventArgs e)
  {
      if (e.Source == "Annotation")
      {
        var itemToRemove = e.MenuItems.FirstOrDefault(item => item.Content == "Delete");
		if (itemToRemove != null)
		{
		   e.MenuItems.Remove(itemToRemove);
		}
      }
      if (e.Source == "Redaction")
      {
        var itemToRemove = e.MenuItems.FirstOrDefault(item => item.Content == "Delete");
		if (itemToRemove != null)
		{
		   e.MenuItems.Remove(itemToRemove);
		}
      }
      if (e.Source == "Text Selection")
      {
        var itemToRemove = e.MenuItems.FirstOrDefault(item => item.Content == "Copy");
		if (itemToRemove != null)
		{
		   e.MenuItems.Remove(itemToRemove);
		}
      }
      if(e.Source == "Signature Field")
      {
        var itemToRemove = e.MenuItems.FirstOrDefault(item => item.Content == "Delete");
		if (itemToRemove != null)
		{
		   e.MenuItems.Remove(itemToRemove);
		}
      }
  }

{% endhighlight %}
{% endtabs %}

### Hide the context menu item.

{% tabs %}
{% highlight c# %}
  private void PdfViewer_ContextMenuOpening(object sender, ContextMenuOpeningEventArgs e)
  {
      if (e.Source == "Annotation")
      {
        e.Handled = true;
      }
      if (e.Source == "Redaction")
      {
         e.Handled = true;
      }
      if (e.Source == "Text Selection")
      {
         e.Handled = true;
      }
      if(e.Source == "Signature Field")
      {
         e.Handled = true;
      }
  }

{% endhighlight %}
{% endtabs %}
## How to the disable contextMenu operations using clicked event.

You can disable the contextMenu operations in PDF viewer control by setting the value of `Handled` in the `ContextMenuItemClickedEventArgs` parameter as true in the `ContextMenuItemClickedEvent` event which is available in the PdfViewerControl and PdfDocumentView class. 
Please refer to the following example for more details.

{% tabs %}
{% highlight c# %}

//Wire the `ContextMenuItemClickedEvent` event.
pdfViewer.ContextMenuItemClickedEvent += PdfViewer_ContextMenuItemClickedEvent;

private void PdfViewer_ContextMenuItemClickedEvent(object sender, ContextMenuItemClickedEventArgs e)
{
  e.Handled = true;
}

{% endhighlight %}
{% endtabs %}

## How to retrieve the clicked menu item content and its source type.

You can acquire the details of the context menu item, which is clicked in the PDF file using the`ContextMenuItemClickedEventArgs`in the`ContextMenuItemClickedEvent`event. 
Please refer to the following example for more details.

{% tabs %}
{% highlight c# %}

//Wire the `ContextMenuItemClickedEvent` event.
pdfViewer.ContextMenuItemClickedEvent += PdfViewer_ContextMenuItemClickedEvent;

private void PdfViewer_ContextMenuItemClickedEvent(object sender, ContextMenuItemClickedEventArgs e)
{
  foreach (var item in e.MenuItems)
  {
    MessageBox.Show($"Source of ContextMenu: {e.Source}\nClicked Menu Item: {item.Content}");
  }
}

{% endhighlight %}
{% endtabs %}
