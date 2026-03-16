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

## Window Type Modes

The Tabbed Window supports two distinct modes that control how tabs are integrated into the window layout. Choose the mode that best fits your application's requirements.

### Tabbed Mode

In Tabbed mode, tabs are integrated into the window's chrome area (the title bar area), similar to modern web browsers. This creates a unified interface where tabs and the window controls appear together.

#### When to Use Tabbed Mode

- Building browser-style applications
- Creating document editors (similar to Visual Studio)
- Tabs are the primary navigation method
- Want integrated chrome appearance with tabs

#### Example

```xaml
<syncfusion:TabbedWindow 
    xmlns:syncfusion="http://schemas.syncfusion.com/wpf"
    x:Class="TabbedWindowApp.MainWindow"
    Title="Document Editor"
    WindowType="Tabbed"
    Height="600" 
    Width="900">
    <syncfusion:SfTabControl AllowDragDrop="True" EnableNewTabButton="True">
        <syncfusion:SfTabItem Header="Document 1" CloseButtonVisibility="Visible">
            <TextBlock Text="Tabs are integrated into window chrome" Padding="20" />
        </syncfusion:SfTabItem>
        <syncfusion:SfTabItem Header="Document 2" CloseButtonVisibility="Visible">
            <TextBlock Text="Similar to browser interface" Padding="20" />
        </syncfusion:SfTabItem>
    </syncfusion:SfTabControl>
</syncfusion:TabbedWindow>
```

#### Layout Characteristics

- Tabs appear in the window chrome area
- Window title and tabs share the top area
- Compact layout
- Professional browser-like appearance

### Normal Mode

In Normal mode, the SfTabControl is displayed as regular content within the window. The tabs occupy the content area rather than being integrated into the window chrome, providing a traditional tab navigation interface.

#### When to Use Normal Mode

- Tabs are secondary navigation
- Need additional UI elements above tabs (toolbar, menu)
- Creating traditional MDI applications
- Want flexible layout control

#### Example

```xaml
<syncfusion:TabbedWindow 
    xmlns:syncfusion="http://schemas.syncfusion.com/wpf"
    x:Class="TabbedWindowApp.MainWindow"
    Title="View Manager"
    WindowType="Normal"
    Height="600" 
    Width="900">
    <Grid>
        <StackPanel Orientation="Vertical">
            <ToolBar Height="40" Background="LightGray">
                <Button Content="File" />
                <Button Content="Edit" />
                <Button Content="View" />
            </ToolBar>
            <syncfusion:SfTabControl AllowDragDrop="True">
                <syncfusion:SfTabItem Header="View 1">
                    <TextBlock Text="Tab control is regular content" Padding="20" />
                </syncfusion:SfTabItem>
                <syncfusion:SfTabItem Header="View 2">
                    <TextBlock Text="Not integrated into chrome" Padding="20" />
                </syncfusion:SfTabItem>
            </syncfusion:SfTabControl>
        </StackPanel>
    </Grid>
</syncfusion:TabbedWindow>
```

