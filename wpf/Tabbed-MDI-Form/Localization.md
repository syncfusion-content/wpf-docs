---
layout: post
title: Localization in WPF DocumentContainer | Syncfusion®
description: Localize the Syncfusion WPF Tabbed MDI Form (DocumentContainer) control to display text and labels in different languages and cultures.
platform: wpf
control: DocumentContainer
documentation: ug
---

# Localization in WPF DocumentContainer

## Assembly Deployment

Refer to the [control dependencies](https://help.syncfusion.com/wpf/control-dependencies#documentcontainer) section to get the list of assemblies or NuGet package that needs to be added as a reference to use the control in any application.

The DocumentContainer exposes a set of resource keys that you can override in a `.resx` file to localize its context menu items and command labels to a specific culture. You can simply provide translated string values in the resource file for a specific culture and set the culture in the application.

## Localizable Resource Keys

The following table lists the resource keys that the DocumentContainer (and DockingManager) read at runtime.

| Resource key | Description | Default menu text (en-US) |
|---|---|---|
| `MDIRestore` | Restores an MDI window from maximized or minimized state. | Restore |
| `MDIMove` | Allows the MDI window to be moved. | Move |
| `MDIResize` | Allows the MDI window to be resized. | Resize |
| `MDIFloating` | Floats the MDI window. | Floating |
| `MDIDockable` | Docks the MDI window. | Dockable |
| `MDIDocument` | Shows the window as a document. | Document |
| `MDIMinimize` | Minimizes the MDI window. | Minimize |
| `MDIMaximize` | Maximizes the MDI window. | Maximize |
| `MDIClose` | Closes the MDI window. | Close |
| `MoveToNextTabGroup` | Moves the tab to the next tab group (DockingManager and DocumentContainer). | Move to Next Tab Group |
| `MoveToPreviousTabGroup` | Moves the tab to the previous tab group (DockingManager and DocumentContainer). | Move to Previous Tab Group |
| `NewTabgroupMenuItemCancel` | Cancels a new tab group drag operation. | Cancel |
| `TabClose` | Closes the active tab. | Close |
| `CloseAllButThis` | Closes all tabs except the active one. | Close All But This |
| `TabCloseAll` | Closes all tabs. | Close All |
| `Floating` | Floats the active tab. | Floating |
| `Document` | Shows the active tab as a document. | Document |
| `Dockable` | Docks the active tab. | Dockable |
| `NewHorizontalTabGroup` | Creates a new horizontal tab group. | New Horizontal Tab Group |
| `NewVerticalTabGroup` | Creates a new vertical tab group. | New Vertical Tab Group |

## Localizing the DocumentContainer

To localize the DocumentContainer, create a resource file (for example `Syncfusion.Tools.WPF.fr-FR.resx`) in your project, add the keys above with translated values, and set the application culture at startup.

{% tabs %}
{% highlight C# %}
using System.Globalization;
using System.Threading;

Thread.CurrentThread.CurrentCulture = new CultureInfo("fr-FR");
Thread.CurrentThread.CurrentUICulture = new CultureInfo("fr-FR");
{% endhighlight %}
{% endtabs %}

N> The exact resource name prefix may differ between Syncfusion versions. If the menu strings do not change after following the steps above, use a tool such as `ILSpy` to inspect the built `Syncfusion.Tools.WPF.resources` assembly and confirm the key prefix for your installed version.

## See Also

* [Getting Started](Getting-Started.md)
* [Setting Mode for Document Container](Setting-Mode-for-Document-Container.md)
