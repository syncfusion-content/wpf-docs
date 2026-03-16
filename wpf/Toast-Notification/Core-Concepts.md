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

{% tabs %}
{% highlight C# %}

SfToastNotification.Show(this, new ToastOptions
{
    Title = "File Saved",
    Message = "Your document has been saved.",
    Actions = new List<ToastAction>
    {
        new ToastAction
        {
            Label = "Undo",
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

{% endhighlight %}
{% endtabs %}

### Action Button with Callback

{% tabs %}
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

{% endhighlight %}
{% endtabs %}

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