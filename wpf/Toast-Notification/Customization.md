---
layout: post
title: Customization of WPF Toast Notification | Syncfusion®
description: Learn about the various customization in Syncfusion Essential WPF Toast Notification control, its elements, and more.
platform: wpf
control: SfToastNotification
documentation: ug
---


# Customization in WPF Toast Notification

## Dealing with ActionButtons

Toast notifications can include interactive action buttons:

### Simple Action Button

{% tabs %}
{% highlight C# %}

SfToastNotification.Show(this, new ToastOptions
{
    Title = "File Saved",
    Message = "Your document has been saved.",
    Actions = new List<ToastAction>
    {
        new ToastAction("Undo"),
        new ToastAction("OK")
    }
});

private void UndoLastSave()
{
    // Implement undo logic
}

{% endhighlight %}
{% endtabs %}

### Action Button with Callback

{% tabs %}
{% highlight C# %}

SfToastNotification.Show(this, new ToastOptions
{
    Mode = ToastMode.Screen,
    Title = "New Message",
    Message = "You have a new message.",
    Actions = new List<ToastAction>
    {
        new ToastAction("Reply")
        {
            Callback = () => OpenReplyWindow(),
            CloseOnClick = true
        },
        new ToastAction("Later")
        {
            CloseOnClick = true
        }
    }
});

private void OpenReplyWindow()
{
    // Open reply window
}

{% endhighlight %}
{% endtabs %}


## Handling Action Button Click Events in System Toast Notifications

The **SfToastNotification** control supports system toast notifications with interaction support, allowing you to add action buttons and handle click events using Windows notification APIs.

### Prerequisites

To handle system toast action button click events, install the following package:

- **CommunityToolkit.WinUI.Notifications**

This package is required only for **handling activation events** (such as button clicks) from system toast notifications.

### .NET Framework Projects

In .NET Framework WPF applications, system toast action button click events can be handled by registering for the [ToastNotificationManagerCompat.OnActivated](https://learn.microsoft.com/en-us/windows/apps/develop/notifications/app-notifications/send-local-toast?tabs=desktop#tabpanel_1_desktop) event.

{% tabs %}
{% highlight C# %}

SfToastNotification.Show(this, new ToastOptions
{
    Mode = ToastMode.Default,
    Title = "File Saved",
    Message = "Your document has been saved.",
    Actions = new List<ToastAction>
    {
        new ToastAction("Open", "action=open"),
        new ToastAction("Dismiss", "action=close")
    }
});

// Register activation handler
ToastNotificationManagerCompat.OnActivated += ToastNotificationManagerCompat_OnActivated;

private void ToastNotificationManagerCompat_OnActivated(ToastNotificationActivatedEventArgsCompat e)
{
    ToastArguments arguments = ToastArguments.Parse(e.Argument);

    if (arguments.TryGetValue("action", out string action))
    {
        switch (action)
        {
            case "Open":
                // Handle Open action
                MessageBox.Show("Open action clicked");
                break;

            case "Dismiss":
                // Handle Dismiss action
                MessageBox.Show("Dismiss action clicked");
                break;
        }
    }
}

{% endhighlight %}
{% endtabs %}

---

### .NET Core / .NET (Windows) Projects

For .NET Core and modern .NET projects, system toast notifications require the [Target Framework Moniker (TFM)](https://learn.microsoft.com/en-us/windows/apps/develop/notifications/app-notifications/send-local-toast?tabs=desktop#step-1-install-nuget-package) to include a **minimum Windows OS version** to access the toast notification APIs.

{% tabs %}
{% highlight XML %}

<TargetFramework>net8.0-windows10.0.19041.0.0</TargetFramework>

{% endhighlight %}
{% endtabs %}

Once configured, action buttons and click event handling work the same way as in .NET Framework projects.

N> View [Sample](https://github.com/SyncfusionExamples/SystemToast-ActionButton-Handling) in GitHub

## Customizing Action Buttons with ActionTemplate

Each action button in a toast notification can be individually customized using the `ActionTemplate` property available in the `ToastAction` class. When defining actions within a toast, you can optionally specify a custom data template to control the appearance and behavior of each action button.

Custom styles or templates are defined in XAML, and the template’s resource name is then bound to the `ActionTemplate` property of the corresponding `ToastAction`. When a template is provided, the toast will use your custom styling; if not, the default action button style defined in the toast’s control template will be applied.

{% tabs %}
{% highlight XAML %}

<DataTemplate x:Key="CustomizedActionTemplate">
    <Button Style="{StaticResource ToastActionButtonStyle}"
            Margin="4,0,4,0"
            Width="132" Height="24"
            HorizontalAlignment="Center"
            Tag="{Binding}"
            Content="{Binding Label}" />
</DataTemplate>

<Style x:Key="ToastActionButtonStyle" TargetType="Button">
    <Setter Property="Background" Value="Blue"/>
    <Setter Property="Foreground" Value="Orange"/>
    <Setter Property="BorderThickness" Value="0" />
    <Setter Property="Padding" Value="6,4" />
    <Setter Property="Width" Value="56" />
    <Setter Property="Height" Value="28" />
 </Style>   
{% endhighlight %}
{% highlight C# %}

SfToastNotification.Show(this, new ToastOptions
{
    Title = "New Message",
    Message = "You have a new message.",
    Actions = new List<ToastAction>
    {
        new ToastAction
        {
            Label = "Reply",
            ActionTemplate = (DataTemplate)Application.Current.Resources["CustomizedActionTemplate"]
        },
        new ToastAction
        {
            Label = "Later"
        }
    }
});

{% endhighlight %}
{% endtabs %}