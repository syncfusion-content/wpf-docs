---
layout: post
title: Events — TabbedWindow | Syncfusion®
description: Key events and example handlers for `TabbedWindow`.
platform: WPF
control: TabbedWindow
documentation: ug
---

# Events

This page lists the events raised by `TabbedWindow` / `SfTabControl` and gives small, named-handler examples to explain the events.

## NewTabRequested

Raised when the user invokes the new‑tab action (new‑tab button) or when the app programmatically requests a new tab. Handle this event to supply the initial `SfTabItem` or to cancel creation.

Common event-args properties:

- `Item` — the `SfTabItem` or view model that will be inserted; assign this to provide default content.

{% tabs %}
{% highlight C# %}

MainTabControl.NewTabRequested += MainTabControl_NewTabRequested;

private void MainTabControl_NewTabRequested(object sender, NewTabRequestedEventArgs e)
{
    e.Item = new SfTabItem { Header = "Untitled", Content = new TextBlock { Text = "New" } };
}
{% endhighlight %}
{% endtabs %}

![WPF New Tab](Events_images/wpf_newtab.gif)

## PreviewTabMerge

Raised before an incoming tab is merged into a target `SfTabControl` (for example when a tab is dropped from another window or tab control). Use this event to validate, transform, or reject incoming tabs.

Event-args properties:

- `ResultingItem` — the tab item as it would appear after the merge.
- `DraggedItem` — get the original dragged tab item.
- `SourceControl` — get the originating `SfTabControl`.
- `TargetControl` — get the receiving `SfTabControl`.
- `Allow` (bool) — set to `false` to reject the merge.

{% tabs %}
{% highlight C# %}

MainTabControl.PreviewTabMerge += MainTabControl_PreviewTabMerge;

private void MainTabControl_PreviewTabMerge(object sender, TabMergePreviewEventArgs e)
{
    e.Allow = true;
	if (!(e.ResultingItem is SfTabItem))
    {
        e.ResultingItem = new SfTabItem
        {
            Header = "NewTab",
            Content = "NewContent"
        };
	}
}
{% endhighlight %}
{% endtabs %}

![WPF TabbedWindow Merging](Events_images/tabbedwindow-merging.gif)

N> If the source and target tab item types are different, the PreviewTabMerge event allows us to replace the resulting item with a compatible type as per our convenience.