---
layout: post
title: Merge Tabs Between Windows in WPF Tabbed Window | Syncfusion
description: Learn how to detach tabs into floating windows and validate tab movement between tabbed windows by using tear-off support and the PreviewTabMerge event.
platform: wpf
control: TabbedWindow
documentation: ug
---

# Merge Tabs Between Windows in WPF Tabbed Window

This section explains how to move tabs between tabbed windows and provides an overview of the supported tear-off and merge validation features.

## Tear-Off Windows

The tabbed window interface supports tear-off functionality that allows tabs to be detached from an `SfTabControl` and displayed in independent floating windows. These floating windows can later be merged back into another tabbed window.

### Enable Tear-Off

You can use the `AllowDragDrop` property to enable tear-off support in `SfTabControl`. When drag-and-drop is enabled, a tab can be dragged outside the tab control boundary to create a floating window. The detached tab is moved into the new window automatically, and it can be reattached later by dragging it back into the tab area of another tabbed window. If a floating window becomes empty after a tab is moved out, it is closed automatically.

The floating window created through tear-off behaves like a regular tabbed window. It can be moved, resized, and minimized, and it supports the same tab features as the original window.

{% tabs %}

{% highlight XAML %}

<syncfusion:SfChromeslessWindow Title="Main Window" WindowType="Tabbed">
    <syncfusion:SfTabControl AllowDragDrop="True">
        <syncfusion:SfTabItem Header="Document 1" CloseButtonVisibility="Visible">
            <TextBlock Text="Drag this tab outside to tear it off" />
        </syncfusion:SfTabItem>
        <syncfusion:SfTabItem Header="Document 2" CloseButtonVisibility="Visible">
            <TextBlock Text="Each tab can be independently floated" />
        </syncfusion:SfTabItem>
    </syncfusion:SfTabControl>
</syncfusion:SfChromeslessWindow>

{% endhighlight %}

{% endtabs %}

![WPF TabbedWindow Tear-Off](merge-tabs_images/tear-off-tabbedwindow.gif)

## Control Tab Movement with PreviewTabMerge

You can use the `PreviewTabMerge` event to validate or cancel a tab merge operation before a tab is moved between tabbed windows. This event also allows you to modify the item that will be inserted into the target `SfTabControl`.

{% tabs %}

{% highlight XAML %}

<syncfusion:SfTabControl 
    AllowDragDrop="True"
    PreviewTabMerge="OnPreviewTabMerge">
    <!-- Tab items -->
</syncfusion:SfTabControl>

{% endhighlight %}

{% highlight C# %}

private void OnPreviewTabMerge(object sender, TabMergePreviewEventArgs e)
{
    // Get information about the merge operation
    var draggedItem = e.DraggedItem;
    var sourceControl = e.SourceControl;
    var targetControl = e.TargetControl;

    // Validate the merge
    if (draggedItem is Document doc && doc.IsLocked)
    {
        // Cancel the merge
        e.Allow = false;
        MessageBox.Show("Cannot move locked documents");
        return;
    }

    // Optional: Transform the item before merge
    if (draggedItem is Document docItem)
    {
        e.ResultingItem = new Document
        {
            Title = docItem.Title,
            Content = docItem.Content,
            CreatedAt = DateTime.Now
        };
    }

    // Allow the merge
    e.Allow = true;
}

{% endhighlight %}

{% endtabs %}

![WPF TabbedWindow Merging](merge-tabs_images/tabbedwindow-merging.gif)

## PreviewTabMergeEventArgs Properties

| Property | Type | Description |
|----------|------|-------------|
| `DraggedItem` | object | The item being dragged. |
| `SourceControl` | SfTabControl | The tab control where the drag operation started. |
| `TargetControl` | SfTabControl | The tab control that receives the dragged item. |
| `Allow` | bool | Specifies whether the merge operation is allowed. Set this to `false` to cancel the merge. |
| `ResultingItem` | object | The item to be inserted into the target control. By default, this is the same as `DraggedItem`. |