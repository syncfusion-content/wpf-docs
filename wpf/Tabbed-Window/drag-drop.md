---
layout: post
title: Drag and Drop in WPF Tabbed Window | Syncfusion
description: Enable drag-and-drop functionality in WPF Tabbed Window to reorder tabs and organize documents.
platform: WPF
control: TabbedWindow
documentation: ug
---

# WPF Tabbed Window - Drag and Drop Support

## Overview

The Tabbed Window supports drag-and-drop functionality that allows users to reorder tabs by dragging and dropping them within the tab control. This provides an intuitive way for users to organize their tabs based on their preferences.

## Enable Drag and Drop

Set the `AllowDragDrop` property to `true` on the `SfTabControl` to enable tab reordering:

```xaml
<syncfusion:SfTabControl AllowDragDrop="True">
    <syncfusion:SfTabItem Header="Tab 1" CloseButtonVisibility="Visible">
        <TextBlock Text="Content 1" />
    </syncfusion:SfTabItem>
    <syncfusion:SfTabItem Header="Tab 2" CloseButtonVisibility="Visible">
        <TextBlock Text="Content 2" />
    </syncfusion:SfTabItem>
    <syncfusion:SfTabItem Header="Tab 3" CloseButtonVisibility="Visible">
        <TextBlock Text="Content 3" />
    </syncfusion:SfTabItem>
</syncfusion:SfTabControl>
```

In C#:

```csharp
SfTabControl tabControl = new SfTabControl();
tabControl.AllowDragDrop = true;

// Add tab items
tabControl.Items.Add(new SfTabItem { Header = "Tab 1", Content = new TextBlock { Text = "Content 1" } });
tabControl.Items.Add(new SfTabItem { Header = "Tab 2", Content = new TextBlock { Text = "Content 2" } });
tabControl.Items.Add(new SfTabItem { Header = "Tab 3", Content = new TextBlock { Text = "Content 3" } });
```

## How It Works

When `AllowDragDrop` is enabled:
1. Users can click and hold on a tab header
2. Drag the tab to a new position
3. Release to drop the tab at the new location
4. The tab order updates immediately

## Disable Drag and Drop

To prevent tab reordering, set `AllowDragDrop` to `false`:

```xaml
<syncfusion:SfTabControl AllowDragDrop="False">
    <!-- Tab items with fixed order -->
</syncfusion:SfTabControl>
```

