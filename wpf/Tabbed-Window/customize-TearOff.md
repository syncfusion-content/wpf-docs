---
layout: post
title: Customize the TearOffWindow | Syncfusion
description: Learn how to customize the window created during tear‑off operations by providing a custom window type and modifying its properties at runtime.
platform: wpf
control: TabbedWindow
documentation: ug
---

# Customize Tear-Off Windows in WPF Tabbed Window

This section explains how to customize the window created during tear‑off operations in the Tabbed Window. It covers the `NewWindowCreating` event support that allows users to control and customize window creation at runtime.

This feature allows users to replace the default tear‑off window with a custom window by providing their own window instance and modifying its properties before the tear-off window is displayed.

## Customizing the Tear-Off Window using NewWindowCreating Event

You can customize the floating Window created during the tear‑off operation by raising the `NewWindowCreating` event of the [SfTabControl](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.SfTabControl.html). This event is triggered when a tab is dragged outside the tab control to create a new window

By handling the `NewWindowCreating` event you can:

- Replace the default [SfChromelessWindow](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.SfChromelessWindow.html) with a custom window
- Modify window properties such as style, appearance, and behavior
- Access details about the	 tab item that initiated the tear‑off
- Apply custom configurations or styling the window

{% tabs %}

{% highlight XAML %}

<syncfusion:SfChromelessWindow Title="Main Window" WindowType="Tabbed">
    <syncfusion:SfTabControl 
        NewWindowCreating="CustomTab_NewWindowCreating">
        <syncfusion:SfTabItem Header="Document 1" CloseButtonVisibility="Visible">
            <TextBlock Text="Drag this tab outside to tear it off" />
        </syncfusion:SfTabItem>
        <syncfusion:SfTabItem Header="Document 2" CloseButtonVisibility="Visible">
            <TextBlock Text="Each tab can be customized" />
        </syncfusion:SfTabItem>
    </syncfusion:SfTabControl>
</syncfusion:SfChromelessWindow>

{% endhighlight %}

{% highlight C# %}

private void CustomTab_NewWindowCreating(object sender, NewWindowCreatingEventArgs e)
{
    var tabControl = sender as SfTabControl;
    var defaultWindow = e.NewWindow;
    var sourceTabItem = e.SourceTabItem;

    // Create a custom window
    var customWindow = new CustomWindow("Custom Tear-Off Window", true, WindowStyle.ToolWindow);

    // Replace the default window with the custom window
    e.NewWindow = customWindow;
}

{% endhighlight %}

{% endtabs %} 

## Advanced Customization Example

You can perform more complex customization by accessing hostWindow properties and applying custom configurations:

![WPF TabbedWindow Customizing TearOff Window](customize-tearOff-images/customized-tearOff-Window.gif)

## NewWindowCreatingEventArgs Properties

| Property       | Type                | Description                                              |
|----------------|---------------------|----------------------------------------------------------|
| NewWindow      | Window              | Gets or sets the window to be created for tear‑off       |
| SourceTabItem  | object              | Gets the tab item that initiated the tear‑off operation  |
