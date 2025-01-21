---
layout: post
title: Customizing context menu in WPF Pdf Viewer | Syncfusion;
description: Learn about Customizing context menu support in Syncfusion<sup>&reg;</sup>; WPF Pdf Viewer control, its elements and more.
platform: wpf
control: PDF Viewer
documentation: ug
---

# Customization support for context menu in WPF PdfViewer

PDF Viewer now supports customization of the default context menu items. This gives users more options to adjust the viewer to fit their application's requirements. Previously, the context menus for Annotation, Text Selection, Redaction, and Signature Field did not allow modifications. With this enhancement, users can add, remove, and hide the default menu items with the help of events.

### Events 

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

## How to customize the context menu items before opening.
The `ContextMenuOpening` Event allows users to customize and manage context menus dynamically,based on the source type where the context menu is triggered. This event provides the flexibility to modify, add, or suppress menu items based on the specific operation.

{% tabs %}
{% highlight c# %}

//Wire the `ContextMenuOpening` event.
pdfViewer.ContextMenuOpening += PdfViewer_ContextMenuOpening;

{% endhighlight %}
{% endtabs %}

Using the `ContextMenuOpeningEventArgs`, you can add,remove or hide context menu items.
Please refer to the following example for more details.
### Add the context menu item.
You can enhance the existing default context menu by adding new menu items to it or inserting them at specific positions based on the source type that triggers the menu. This allows for dynamic customization to suit various use cases, such as adding custom options for annotations, redactions, text selection, or signature fields.
{% tabs %}
{% highlight c# %}
  private void PdfViewer_ContextMenuOpening(object sender, ContextMenuOpeningEventArgs e)
  {
      if (e.Source == "Annotation")
      {
	    e.MenuItems.Insert(0,(new ContextMenuItem { Content = "Lock Annotation" }));
        e.MenuItems.Add(new ContextMenuItem { Content = "New Menu Item" });
      }
      if (e.Source == "Redaction")
      {
        e.MenuItems.Add(new ContextMenuItem { Content = "New Menu Item" });
      }
      if (e.Source == "Text Selection")
      {
        e.MenuItems.Add(new ContextMenuItem { Content = "New Menu Item" });
      }
      if(e.Source == "Signature Field")
      {
        e.MenuItems.Add(new ContextMenuItem { Content = "New Menu Item" });
      }
  }

{% endhighlight %}
{% endtabs %}
![Adding new menu item](Customized-ConetextMenu-Images\Customized-Context-Menu-1.png)

### Remove the context menu item.
You can remove a menu item from the context menu based on the source type by identifying and matching the item's content. This helps you customize the menu to display only the necessary options.
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

![Remove menu item](Customized-ConetextMenu-Images\Customized-Context-Menu-2.png)
### Hide the context menu item.
You can hide the context menu by setting the `Handled` property to `true` in the `ContextMenuOpening` event.This prevents the menu from being displayed,giving you control over whether the context menu should appear for source types.This helps you manage and customize the behavior of the context menu based on your application's requirements.
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
## How to customized the clicked event for context menu item.
You can customized the context menu clicked event operations in the PDF Viewer control by setting the value of `Handled` to `true` in the `ContextMenuItemClickedEventArgs` parameter within the `ContextMenuItemClickedEvent` event.This allows you to control the behavior of the context menu and prevent any actions from being executed. 
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

You can also retrieve the details of the clicked context menu item, including its content and the source type,using the `ContextMenuItemClickedEventArgs` in the `ContextMenuItemClickedEvent` event.
Please refer to the following example for more details.
{% tabs %}
{% highlight c# %}

private void PdfViewer_ContextMenuItemClickedEvent(object sender, ContextMenuItemClickedEventArgs e)
{
   MessageBox.Show($"Source of ContextMenu: {e.Source}\nClicked Menu Item: {e.MenuItem.Content}");
}

{% endhighlight %}
{% endtabs %}
