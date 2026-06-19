---
layout: post
title: Zoom Control in WPF Magnifier | Syncfusion®
description: Learn how to control zoom levels programmatically using ZoomIn, ZoomOut methods and ZoomFactor property in the WPF Magnifier control.
platform: wpf
control: Magnifier
documentation: ug
---
# Zooming feature of Magnifier

The Magnifier control provides flexible zooming through the [`ZoomFactor`](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.Magnifier.html#Syncfusion_Windows_Shared_Magnifier_ZoomFactor) property and programmatic methods. You can configure zoom levels declaratively or adjust them dynamically at runtime.

## ZoomFactor Property

The `ZoomFactor` property determines the relative size of the area displayed inside the magnifier frame. It controls the magnification level and accepts values between `0.0` and `1.0`.

### Understanding ZoomFactor Values

* **Lower values** (e.g., `0.2`) = **Higher magnification** (smaller area shown, more zoomed in)
* **Higher values** (e.g., `0.8`) = **Lower magnification** (larger area shown, less zoomed in)  
* **Value of `1.0`** = **No magnification** (content shown at original size)

The ZoomFactor property is automatically coerced to the valid range:
* Values greater than `1.0` are set to `1.0`
* Values less than `0.0` are set to `0.0`

### Setting ZoomFactor Declaratively

**XAML:**

```xml
<syncfusion:Magnifier.Current>
    <syncfusion:Magnifier ZoomFactor="0.3"
                          FrameType="Circle"
                          FrameRadius="120"/>
</syncfusion:Magnifier.Current>
```

**C#:**

```csharp
var magnifier = new Magnifier
{
    ZoomFactor = 0.3,
    FrameType = FrameType.Circle,
    FrameRadius = 120
};
```

## Programmatic Zoom Control

The Magnifier control provides [`ZoomIn()`](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.Magnifier.html#Syncfusion_Windows_Shared_Magnifier_ZoomIn_System_Double_) and [`ZoomOut()`](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.Magnifier.html#Syncfusion_Windows_Shared_Magnifier_ZoomOut_System_Double_) methods to adjust zoom levels dynamically at runtime.

### ZoomIn Method

The `ZoomIn(double zoomFactor)` method increases magnification by dividing the current `ZoomFactor` by the specified factor.

**Signature:**
```csharp
public void ZoomIn(double zoomFactor)
```

**Example:**
```csharp
// Current ZoomFactor = 0.4
magnifier.ZoomIn(2.0);
// New ZoomFactor = 0.4 / 2.0 = 0.2 (higher magnification)
```

### ZoomOut Method

The `ZoomOut(double zoomFactor)` method decreases magnification by multiplying the current `ZoomFactor` by the specified factor.

**Signature:**
```csharp
public void ZoomOut(double zoomFactor)
```

**Example:**
```csharp
// Current ZoomFactor = 0.2
magnifier.ZoomOut(2.0);
// New ZoomFactor = 0.2 * 2.0 = 0.4 (lower magnification)
```

## Implementing Zoom Controls

### Zoom Buttons Example

Add zoom in/out buttons to your application for user-controlled magnification.

**XAML:**

```xml
<Window x:Class="MagnifierSample.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:syncfusion="http://schemas.syncfusion.com/wpf"
        Title="Magnifier Zoom Control" Height="500" Width="800">
    
    <Grid>
        <Grid.RowDefinitions>
            <RowDefinition Height="Auto"/>
            <RowDefinition Height="*"/>
        </Grid.RowDefinitions>
        
        <!-- Zoom Control Panel -->
        <StackPanel Orientation="Horizontal" Margin="10" Grid.Row="0">
            <Button Content="Zoom In" 
                    Click="ZoomIn_Click" 
                    Width="80" 
                    Margin="5"/>
            <Button Content="Zoom Out" 
                    Click="ZoomOut_Click" 
                    Width="80" 
                    Margin="5"/>
            <Button Content="Reset Zoom" 
                    Click="ResetZoom_Click" 
                    Width="80" 
                    Margin="5"/>
            <TextBlock Text="Zoom Level:" 
                       VerticalAlignment="Center" 
                       Margin="10,0,5,0"/>
            <TextBlock x:Name="ZoomLevelText" 
                       VerticalAlignment="Center" 
                       FontWeight="Bold"/>
        </StackPanel>
        
        <!-- Content Area -->
        <Grid x:Name="ContentGrid" Grid.Row="1" Background="White">
            <syncfusion:Magnifier x:Name="MagnifierControl"
                                  ZoomFactor="0.5"
                                  FrameType="Circle"
                                  FrameRadius="100"
                                  FrameBackground="LightGray"/>
            
            <StackPanel Margin="20">
                <TextBlock Text="Sample Content" FontSize="20" FontWeight="Bold"/>
                <TextBlock Text="Use the zoom buttons above to adjust magnification level." 
                           TextWrapping="Wrap" 
                           Margin="0,10,0,0"/>
            </StackPanel>
        </Grid>
    </Grid>
</Window>
```

**C#:**

```csharp
using System;
using System.Windows;
using Syncfusion.Windows.Shared;

public partial class MainWindow : Window
{
    public MainWindow()
    {
        InitializeComponent();
        
        // Attach magnifier to content grid
        Magnifier.SetCurrent(ContentGrid, MagnifierControl);
        
        // Update zoom level display
        UpdateZoomLevelDisplay();
        
        // Subscribe to ZoomFactor changes
        MagnifierControl.ZoomFactorChanged += (s, e) => UpdateZoomLevelDisplay();
    }
    
    private void ZoomIn_Click(object sender, RoutedEventArgs e)
    {
        // Zoom in by factor of 1.5
        MagnifierControl.ZoomIn(1.5);
    }
    
    private void ZoomOut_Click(object sender, RoutedEventArgs e)
    {
        // Zoom out by factor of 1.5
        MagnifierControl.ZoomOut(1.5);
    }
    
    private void ResetZoom_Click(object sender, RoutedEventArgs e)
    {
        // Reset to default zoom
        MagnifierControl.ZoomFactor = 0.5;
    }
    
    private void UpdateZoomLevelDisplay()
    {
        double magnification = 1.0 / MagnifierControl.ZoomFactor;
        ZoomLevelText.Text = $"{magnification:F1}x (ZoomFactor: {MagnifierControl.ZoomFactor:F2})";
    }
}
```

### Keyboard Zoom Control

Implement keyboard shortcuts for zoom control:

```csharp
private void Window_PreviewKeyDown(object sender, KeyEventArgs e)
{
    // Ctrl + Plus = Zoom In
    if (Keyboard.Modifiers == ModifierKeys.Control && e.Key == Key.OemPlus)
    {
        e.Handled = true;
        MagnifierControl.ZoomIn(1.2);
    }
    // Ctrl + Minus = Zoom Out
    else if (Keyboard.Modifiers == ModifierKeys.Control && e.Key == Key.OemMinus)
    {
        e.Handled = true;
        MagnifierControl.ZoomOut(1.2);
    }
    // Ctrl + 0 = Reset Zoom
    else if (Keyboard.Modifiers == ModifierKeys.Control && e.Key == Key.D0)
    {
        e.Handled = true;
        MagnifierControl.ZoomFactor = 0.5;
    }
}
```

### Mouse Wheel Zoom Control

Implement mouse wheel zoom:

```csharp
private void ContentGrid_MouseWheel(object sender, MouseWheelEventArgs e)
{
    if (Keyboard.Modifiers == ModifierKeys.Control)
    {
        e.Handled = true;
        
        if (e.Delta > 0)
        {
            // Scroll up = Zoom In
            MagnifierControl.ZoomIn(1.1);
        }
        else
        {
            // Scroll down = Zoom Out
            MagnifierControl.ZoomOut(1.1);
        }
    }
}
```

## Dynamic Zoom Scenarios

### Zoom Level Presets

Provide preset zoom levels for common use cases:

```csharp
public enum ZoomPreset
{
    Low,      // 0.6
    Medium,   // 0.4
    High,     // 0.25
    VeryHigh  // 0.15
}

public void SetZoomPreset(ZoomPreset preset)
{
    MagnifierControl.ZoomFactor = preset switch
    {
        ZoomPreset.Low => 0.6,
        ZoomPreset.Medium => 0.4,
        ZoomPreset.High => 0.25,
        ZoomPreset.VeryHigh => 0.15,
        _ => 0.5
    };
}
```

### Context-Sensitive Zoom

Adjust zoom based on content type:

```csharp
private void SetZoomForContent(string contentType)
{
    switch (contentType)
    {
        case "Text":
            MagnifierControl.ZoomFactor = 0.4; // Moderate zoom for text
            break;
        case "Image":
            MagnifierControl.ZoomFactor = 0.25; // Higher zoom for images
            break;
        case "Chart":
            MagnifierControl.ZoomFactor = 0.5; // Lower zoom for charts
            break;
    }
}
```
### **Zooming demo**

![Zooming features](resources\zooming-features.gif)


## ZoomFactor and Magnification Relationship

Understanding the inverse relationship:

| ZoomFactor | Magnification | Best For |
|------------|---------------|----------|
| 0.8 - 1.0  | 1x - 1.25x    | Slight enhancement |
| 0.5 - 0.7  | 1.4x - 2x     | General inspection |
| 0.3 - 0.4  | 2.5x - 3.3x   | Detailed viewing |
| 0.15 - 0.25 | 4x - 6.7x    | Fine detail analysis |
| < 0.15     | > 7x          | Pixel-level inspection |

## Best Practices

* **Incremental adjustments**: Use zoom factors between 1.1 and 2.0 for smooth, user-friendly zoom changes.
* **Zoom limits**: Consider implementing minimum and maximum zoom levels to prevent unusable magnification states.
* **Visual feedback**: Display the current zoom level to help users understand the magnification amount.
* **Smooth transitions**: For frequent zoom changes, consider adding animation or throttling to improve user experience.
* **Context awareness**: Adjust default zoom levels based on content type (text, images, diagrams) for optimal viewing.


