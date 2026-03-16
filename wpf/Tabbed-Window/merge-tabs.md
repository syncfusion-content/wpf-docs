---
layout: post
title: Merge Tabs Between Windows in WPF Tabbed Window | Syncfusion
description: Move tabs between multiple tabbed windows and control merge operations with validation.
platform: WPF
control: TabbedWindow
documentation: ug
---

# WPF Tabbed Window - Merge Tabs Between Windows

## Overview

The Tabbed Window supports merging tabs between multiple windows through drag-and-drop operations. This enables users to reorganize content across multiple windows and create flexible workspace configurations.

## Tear-Off Windows

The Tabbed Window supports tear-off functionality that allows users to detach tabs and create independent floating windows. These floating windows operate as separate TabbedWindow instances and can be reattached to the main window later.

### Creating Floating Windows

To tear off a tab and create a floating window:

1. Drag a tab outside the boundary of the tab control
2. A new floating window is automatically created
3. The tab is now contained in the new floating window
4. The floating window can be a new tabbed window

### Enable Tear-Off

Ensure `AllowDragDrop` is enabled, which is the prerequisite for tear-off functionality:

```xaml
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
```

### Reattaching Floating Tabs

To reattach a tab from a floating window back to the main window:

1. Drag the tab from the floating window
2. Drop it inside the main window's tab area
3. The tab is automatically integrated back into the main window
4. The floating window is closed if it becomes empty

### Floating Window Behavior

Each floating window created by tearing off a tab:
- Is a fully functional TabbedWindow instance
- Inherits SfChromelessWindow properties
- Can be resized, moved, and minimized
- Supports the same tab features as the main window (drag-drop, new tabs, close buttons)
- Can have additional tabs dragged into it

## Control Tab Movement with PreviewTabMerge

The `PreviewTabMerge` event fires before a tab is moved between windows, allowing you to validate or cancel the merge operation:

```xaml
<syncfusion:SfTabControl 
    AllowDragDrop="True"
    PreviewTabMerge="OnPreviewTabMerge">
    <!-- Tab items -->
</syncfusion:SfTabControl>
```

Handle the event in code-behind:

```csharp
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
```

## PreviewTabMergeEventArgs Properties

| Property | Type | Description |
|----------|------|-------------|
| `DraggedItem` | object | The item being dragged |
| `SourceControl` | SfTabControl | The control where drag originated |
| `TargetControl` | SfTabControl | The control receiving the item |
| `Allow` | bool | Set to false to cancel merge (default: true) |
| `ResultingItem` | object | The item to be inserted (default: DraggedItem) |


