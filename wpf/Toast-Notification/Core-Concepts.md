---
layout: post
title: Core Concepts of WPF Toast Notification | Syncfusion®
description: Learn about core concepts of Syncfusion® WPF Toast Notification control including modes, severity levels, variants, and placement.
platform: wpf
control: SfToastNotification
documentation: ug
---

# Core Concepts

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
            Label = "Undo",
            Callback = () => UndoLastSave()
        },
        new ToastAction
        {
            Label = "OK",
            CloseOnClick = true
        }
    }
});

private void UndoLastSave()
{
    // Implement undo logic
}
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

## Summary

| Concept | Purpose | Key Options |
|---------|---------|------------|
| **Actions** | Interactive buttons | Custom labels and callbacks |


Master these core concepts to effectively use Toast Notifications in your applications!
