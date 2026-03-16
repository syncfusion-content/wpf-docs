---
layout: post
title: Getting Started with WPF Tabbed Window | Syncfusion
description: Learn how to create and use WPF Tabbed Window by combining SfChromelessWindow with SfTabControl for document management applications.
platform: WPF
control: TabbedWindow
documentation: ug
---

# Getting Started with WPF Tabbed Window

## Creating Your First Tabbed Window

### Step 1: Add References

Ensure you have the required Syncfusion assemblies referenced in your project:
- Syncfusion.SfChromelessWindow.WPF
- Syncfusion.Shared.WPF

### Step 2: Create XAML

Create a window that inherits from `TabbedWindow`:

```xaml
<syncfusion:TabbedWindow 
    xmlns:syncfusion="http://schemas.syncfusion.com/wpf"
    x:Class="TabbedWindowApp.MainWindow"
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    Title="Tabbed Window Example" 
    Height="600" 
    Width="900"
    WindowType="Tabbed">
    <syncfusion:SfTabControl AllowDragDrop="True" EnableNewTabButton="True">
        <syncfusion:SfTabItem Header="Tab 1" CloseButtonVisibility="Visible">
            <TextBlock Text="Welcome to Tabbed Window" Padding="20" FontSize="16" />
        </syncfusion:SfTabItem>
        <syncfusion:SfTabItem Header="Tab 2" CloseButtonVisibility="Visible">
            <TextBlock Text="Drag tabs to reorder" Padding="20" FontSize="16" />
        </syncfusion:SfTabItem>
        <syncfusion:SfTabItem Header="Tab 3" CloseButtonVisibility="Visible">
            <TextBlock Text="Tear off tabs to float them" Padding="20" FontSize="16" />
        </syncfusion:SfTabItem>
    </syncfusion:SfTabControl>
</syncfusion:TabbedWindow>
```

### Step 3: Create Code-Behind

Create the C# code-behind file:

```csharp
using Syncfusion.Windows.Controls;
using System.Windows;

namespace TabbedWindowApp
{
    public partial class MainWindow : TabbedWindow
    {
        public MainWindow()
        {
            InitializeComponent();
        }
    }
}
```

## Key Properties

| Property | Description |
|----------|-------------|
| `AllowDragDrop` | Enable/disable drag-drop reordering of tabs |
| `EnableNewTabButton` | Show/hide the new tab (+) button |
| `SelectedItem` | Get/set the currently active tab |
| `ItemsSource` | Bind tabs to a collection for data-driven scenarios |
| `WindowType` | Choose between "Tabbed" or "Normal" mode |

## Basic Examples

### Tabbed Mode (Browser-Style)

```xaml
<syncfusion:TabbedWindow WindowType="Tabbed">
    <!-- Tabs are integrated into window chrome -->
</syncfusion:TabbedWindow>
```

### Normal Mode (Content-Based)

```xaml
<syncfusion:TabbedWindow WindowType="Normal">
    <!-- Tabs are regular content area -->
</syncfusion:TabbedWindow>
```

### With Close Buttons

```xaml
<syncfusion:SfTabControl>
    <syncfusion:SfTabItem Header="Document 1" CloseButtonVisibility="Visible">
        <TextBlock Text="Content" />
    </syncfusion:SfTabItem>
</syncfusion:SfTabControl>
```

### With New Tab Handler

```xaml
<syncfusion:SfTabControl 
    EnableNewTabButton="True"
    NewTabRequested="OnNewTabRequested">
    <!-- Tab items -->
</syncfusion:SfTabControl>
```

```csharp
private void OnNewTabRequested(object sender, NewTabRequestedEventArgs e)
{
    var newItem = new SfTabItem { Header = "New Tab" };
    e.Item = newItem;
}
```

