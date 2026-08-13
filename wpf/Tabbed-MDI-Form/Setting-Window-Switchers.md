---
layout: post
title: Setting Window Switchers in WPF Tabbed MDI Form | Syncfusion®
description: Learn here all about Setting Window Switchers support in Syncfusion® WPF Tabbed MDI Form (DocumentContainer) control and more.
platform: WPF
control: DocumentContainer
documentation: ug
---

# Setting Window Switchers in WPF Tabbed MDI Form

## Assembly Deployment

Refer to the [control dependencies](https://help.syncfusion.com/wpf/control-dependencies#documentcontainer) section to get the list of assemblies or NuGet package that needs to be added as a reference to use the control in any application.

The DocumentContainer enables the user to switch between the open windows using the keyboard. The `CTRL + TAB` keyboard shortcut opens the window switcher, which the user can then navigate through to switch to another window. The window switcher style is controlled by the [SwitchMode](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DocumentContainer.html#Syncfusion_Windows_Tools_Controls_DocumentContainer_SwitchMode) property, which uses the `Syncfusion.Windows.Tools.Controls.SwitchMode` enum.

## Supported Switcher Modes

| Value | Description |
|---|---|
| `Immediate` | Switches immediately to the next window when `CTRL + TAB` is pressed (no switcher UI). |
| `List` | Displays a list-style switcher showing all open windows. |
| `QuickTabs` | Displays a thumbnail-style switcher with previews of each window. |
| `VS2005` | Mimics the Visual Studio 2005 style of switcher. |
| `VistaFlip` | Mimics the Windows Vista Flip 3D switcher. |

## Setting the Switcher to QuickTabs

{% tabs %}
{% highlight XAML %}
<syncfusion:DocumentContainer Name="DocContainer" SwitchMode="QuickTabs" Mode="MDI">
    <!-- child elements -->
</syncfusion:DocumentContainer>
{% endhighlight %}

{% highlight C# %}
// Creating an instance of DocumentContainer
DocumentContainer docContainer = new DocumentContainer();
// Set the mode to MDI
docContainer.Mode = DocumentContainerMode.MDI;
// Set the switcher to QuickTabs
docContainer.SwitchMode = SwitchMode.QuickTabs;
// Add the control to the window
this.Content = docContainer;
{% endhighlight %}
{% endtabs %}

## See Also

* [Getting Started](Getting-Started.md)
* [Setting Mode for Document Container](Setting-Mode-for-Document-Container.md)
* [Setting Window State](Setting-Window-State.md)
