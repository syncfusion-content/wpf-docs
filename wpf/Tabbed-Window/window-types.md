---
layout: post
title: Window Type Modes in WPF Tabbed Window | Syncfusion
description: Choose between Tabbed and Normal window type modes for different UI layouts and use cases.
platform: WPF
control: TabbedWindow
documentation: ug
---

# WPF Tabbed Window - Window Type Modes

## Overview

The Tabbed Window supports two distinct modes that control how tabs are integrated into the window layout. Choose the mode that best fits your application's requirements.

## Tabbed Mode

In Tabbed mode, tabs are integrated into the window's chrome area (the title bar area), similar to modern web browsers. This creates a unified interface where tabs and the window controls appear together.

### When to Use Tabbed Mode

- Building browser-style applications
- Creating document editors (similar to Visual Studio)
- Tabs are the primary navigation method
- Want integrated chrome appearance with tabs

### Example

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

### Layout Characteristics

- Tabs appear in the window chrome area
- Window title and tabs share the top area
- Compact layout
- Professional browser-like appearance

## Normal Mode

In Normal mode, the SfTabControl is displayed as regular content within the window. The tabs occupy the content area rather than being integrated into the window chrome, providing a traditional tab navigation interface.

### When to Use Normal Mode

- Tabs are secondary navigation
- Need additional UI elements above tabs (toolbar, menu)
- Creating traditional MDI applications
- Want flexible layout control

### Example

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
