---
layout: post
title: Core Concepts of WPF Toast Notification | Syncfusion®
description: Learn about core concepts of Syncfusion® WPF Toast Notification control including modes, severity levels, variants, and placement.
platform: wpf
control: SfToastNotification
documentation: ug
---

# Core Concepts

## Toast Modes

The SfToastNotification control supports three different display modes to suit various application scenarios.

### 1. Default Mode

Uses the native operating system toast notifications. Ideal for applications that want to integrate with the OS notification system.

```csharp
SfToastNotification.Show(this, new ToastOptions
{
    Title = "System Notification",
    Message = "Using native OS toast",
    Mode = ToastMode.Default
});
```

**Characteristics:**
- Native OS appearance and behavior
- System-level notifications
- Limited customization options
- Best for critical system messages

N> When `ToastMode = Default`, **NO customizations are applicable**. The toast uses native OS styling and behavior. Default mode does not accept any customization.

### 2. Window Mode

Displays toast notifications within the owning window. Perfect for applications where you want toasts to stay within the application boundaries.

```csharp
SfToastNotification.Show(this, new ToastOptions
{
    Title = "Window Toast",
    Message = "This notification appears within the window",
    Mode = ToastMode.Window,
    Placement = ToastPlacement.BottomRight
});
```

**Characteristics:**
- Constrained to window boundaries
- Full customization support
- Respects window activation state
- Good for application-specific feedback

### 3. Screen Mode

Displays custom toast overlay globally across the screen. Useful for application-wide notifications that should be visible regardless of window focus.

```csharp
SfToastNotification.Show(this, new ToastOptions
{
    Title = "Global Notification",
    Message = "This notification appears globally on screen",
    Mode = ToastMode.Screen,
    Placement = ToastPlacement.TopCenter
});
```

**Characteristics:**
- Global screen-level display
- Full customization capabilities
- Visible regardless of window state
- Best for important application-wide events

## Toast Variants and Severity

Toast notifications provide multiple severity levels with built‑in visual styling and offer three visual variants to suit different design preferences.

```
xaml

SfToastNotification.Show(this, new ToastOptions
{
    Title = "Success",
    Message = "Variant applies filled style",
    Severity = ToastSeverity.Success,
    Variant = ToastVariant.Filled  
});

```

### Variant Behavior with Severity

| **Severity ↓ / Variant →** | **Text** | **Fill** | **Outlined** |
|----------------------------|-----------|-----------|---------------|
| **Info**                   | *Image Reference* | *Image Reference* | *Image Reference* |
| **Success**                | *Image Reference* | *Image Reference* | *Image Reference* |
| **Warning**                | *Image Reference* | *Image Reference* | *Image Reference* |
| **Error**                  | *Image Reference* | *Image Reference* | *Image Reference* |

## Accent Brush

The AccentBrush property enables you to fine‑tune the appearance of toast notifications. After severity and variant are applied, you can use this property to customize the color accents and overall visual styling.

### Accent Brush Behavior with Severity

```
// Accent brush IS applied (Severity = Error)
// Customizes the error color styling
SfToastNotification.Show(this, new ToastOptions
{
    Title = "Error",
    Message = "Accent brush customizes error styling",
    Severity = ToastSeverity.Error,
    AccentBrush = new SolidColorBrush(Colors.Crimson)  // Applied
});
```

## Toast Placement Options

The Toast control supports multiple screen placement options, allowing notifications to appear at specific positions within the application window / screen. 


TopLeft – Displays the toast in the top‑left corner.

TopCenter – Displays the toast centered at the top.

TopRight – Displays the toast in the top‑right corner.

LeftCenter – Displays the toast vertically centered on the left edge.

RightCenter – Displays the toast vertically centered on the right edge.

BottomLeft – Displays the toast in the bottom‑left corner.

BottomCenter – Displays the toast centered at the bottom.

BottomRight – Displays the toast in the bottom‑right corner.

These placement options give you full control over where toast notifications appear in the UI, enabling you to tailor the experience to your app layout or user preferences.

```csharp
// Top-Left corner
SfToastNotification.Show(this, new ToastOptions
{
    Message = "Top-Left Position",
    Placement = ToastPlacement.TopLeft,
    Mode = ToastMode.Screen
});
```

## Action Buttons

Toast notifications can include interactive action buttons:

### Simple Action Button

```csharp
SfToastNotification.Show(this, new ToastOptions
{
    Title = "File Saved",
    Message = "Your document has been saved.",
    Actions = new List<ToastAction>
    {
        new ToastAction
        {
            Label = "Undo"
        },
        new ToastAction
        {
            Label = "OK",
        }
    }
});

```

### Action Button with Callback

```csharp
SfToastNotification.Show(this, new ToastOptions
{
    Title = "New Message",
    Message = "You have a new message.",
    Actions = new List<ToastAction>
    {
        new ToastAction
        {
            Label = "Reply",
            Callback = () => OpenReplyWindow(),
            CloseOnClick = true
        },
        new ToastAction
        {
            Label = "Later",
            CloseOnClick = true
        }
    }
});

private void OpenReplyWindow()
{
    // Open reply window
}
```

## Toast Lifecycle

Understanding the lifecycle of a toast helps in managing notifications effectively.

### States

1. **Creation** - Toast is created with ToastOptions
2. **Display** - Toast appears on screen according to placement and mode
3. **Duration** - Toast remains visible for specified duration
4. **Dismissal** - Toast closes via auto-close timeout, close button, or programmatic close

### Managing Toast Lifecycle

```csharp
// Create a toast with custom ID
var options = new ToastOptions
{
    Id = "unique-toast-id",
    Title = "Tracked Toast",
    Message = "This toast can be managed",
    Duration = TimeSpan.FromSeconds(10)
};

SfToastNotification.Show(this, options);

// Manually close specific toast
SfToastNotification.Close("unique-toast-id");

// Close all toasts
SfToastNotification.CloseAll();
```

## Animation Types

Toast notifications support 14+ built-in animations.

| Animation | In | Out |
|-----------|----|----|
| **Fade** | FadeIn | FadeOut |
| **Zoom** | FadeZoomIn | FadeZoomOut |
| **Slide** | SlideBottomIn | SlideBottomOut |
| **Flip Left Down** | FlipLeftDownIn | FlipLeftDownOut |
| **Flip Left Up** | FlipLeftUpIn | FlipLeftUpOut |
| **Flip Right Down** | FlipRightDownIn | FlipRightDownOut |
| **None** | None | None |

## Customization Reference

This section provides a **complete reference** for all customization applicability rules.

| Feature | Default Mode | Window/Screen + Severity=None | Window/Screen + Severity Levels |
|---|---|---|---|
| **Severity** (Info/Success/Warning/Error) | ❌ NO (OS controlled) | ✅ YES | ✅ YES |
| **Variant** (Text/Outlined/Filled) | ❌ NO | ❌ NO (not applicable for None) | ✅ YES |
| **AccentBrush** (Custom colors) | ❌ NO | ❌ NO (not applicable for None) | ✅ YES |
| **Placement** (8 positions) | ❌ NO (OS managed) | ✅ YES | ✅ YES |
| **Animations** (14+ types) | ❌ NO | ✅ YES | ✅ YES |
| **Actions** (Interactive buttons) | ⚠️ LIMITED | ✅ YES | ✅ YES |
| **Duration** (Auto-close timing) | ❌ NO | ✅ YES | ✅ YES |
| **Title/Message** (Text content) | ✅ YES | ✅ YES | ✅ YES |

**Key Points:**
- ✅ Features marked **YES** are fully supported
- ❌ Features marked **NO** are not supported
- ⚠️ **LIMITED** means basic support only
- **Variant** and **AccentBrush** require severity levels (not applicable when Severity = None)
- **Placement**, **Animations**, **Actions** require Window/Screen modes (not available in Default mode)

## Summary

| Concept | Purpose | Key Options |
|---------|---------|------------|
| **Modes** | Where toast appears | Default, Screen, Window |
| **Severity** | Toast importance level | None, Info, Success, Warning, Error |
| **Variants** | Visual styling | Text, Outlined, Filled |
| **Accent Brush** | Custom color scheme | RGB colors |
| **Placement** | Screen position | 8 positions |
| **Actions** | Interactive buttons | Custom labels and callbacks |
| **Animations** | Show/hide effects | 14+ animation types |
| **Duration** | Auto-close timing | Timespan in seconds |

