---
layout: post
title: Tab Management in WPF Tabbed Window | Syncfusion
description: Manage tabs dynamically with close buttons, new tab creation, and tab selection.
platform: WPF
control: TabbedWindow
documentation: ug
---

# WPF Tabbed Window - Tab Management

## Overview

The Tabbed Window provides comprehensive tab management capabilities including dynamic tab creation, tab closing, and tab selection. These features enable flexible and responsive tab-based interfaces.

## Close Button Support

Display close buttons on individual tabs using the `CloseButtonVisibility` property on `SfTabItem`:

```xaml
<syncfusion:SfTabControl>
    <syncfusion:SfTabItem 
        Header="Document 1" 
        CloseButtonVisibility="Visible">
        <TextBlock Text="Click the X button to close this tab" />
    </syncfusion:SfTabItem>
    <syncfusion:SfTabItem 
        Header="Document 2" 
        CloseButtonVisibility="Visible">
        <TextBlock Text="Each tab has its own close button" />
    </syncfusion:SfTabItem>
</syncfusion:SfTabControl>
```

In C#:

```csharp
var tabItem = new SfTabItem 
{ 
    Header = "Document", 
    CloseButtonVisibility = Visibility.Visible,
    Content = new TextBlock { Text = "Tab Content" }
};
tabControl.Items.Add(tabItem);
```

When a user clicks the close button, the tab is automatically removed and the control selects the next available tab.

## New Tab Button

Enable the new tab button to allow users to dynamically add tabs:

```xaml
<syncfusion:SfTabControl 
    EnableNewTabButton="True"
    NewTabRequested="OnNewTabRequested">
    <syncfusion:SfTabItem Header="Tab 1">
        <TextBlock Text="Content 1" />
    </syncfusion:SfTabItem>
</syncfusion:SfTabControl>
```

Handle the `NewTabRequested` event to create new tabs:

```csharp
private void OnNewTabRequested(object sender, NewTabRequestedEventArgs e)
{
    // Create a new tab item when user clicks the + button
    var newTabContent = new TextBlock 
    { 
        Text = $"New Document {DateTime.Now:g}" 
    };
    
    var newTabItem = new SfTabItem 
    { 
        Header = $"Document {tabControl.Items.Count + 1}",
        Content = newTabContent,
        CloseButtonVisibility = Visibility.Visible
    };
    
    e.Item = newTabItem;
}
```

Customize the new tab button appearance:

```xaml
<syncfusion:SfTabControl 
    EnableNewTabButton="True"
    NewTabButtonStyle="{StaticResource CustomNewTabButtonStyle}">
    <!-- Tab items -->
</syncfusion:SfTabControl>
```

## Tab Selection

### Programmatic Selection

Set the active tab using the `SelectedItem` property:

```csharp
// Change selected tab programmatically
tabControl.SelectedItem = tabControl.Items[1];
```

### Listen to Selection Changes

Handle the `SelectionChanged` event:

```csharp
tabControl.SelectionChanged += (s, e) => 
{
    var selectedTab = tabControl.SelectedItem as SfTabItem;
    MessageBox.Show($"Selected: {selectedTab?.Header}");
};
```

### Keyboard Navigation

Users can navigate between tabs using keyboard shortcuts:
- **Ctrl+Tab** - Move to next tab
- **Ctrl+Shift+Tab** - Move to previous tab

