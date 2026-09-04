---
layout: post
title: Full Screen in WPF DocumentContainer | Syncfusion®
description: Display the active document of the Syncfusion WPF Tabbed MDI Form (DocumentContainer) control in full-screen mode for focused viewing.
platform: wpf
control: Tabbed MDI Form
documentation: ug
---

# Full Screen in WPF Document Container

## TDIFullScreenMode

`TDIFullScreenMode` is the property used to define the full-screen mode for TDI items. When a value is set for this property, the parent window is displayed in full-screen mode and the tab item header is visible only when the cursor passes over the top of the window. This property is an enum (`Syncfusion.Windows.Tools.Controls.FullScreenMode`) with the following values:

* `ControlMode` — Makes the tab header visible on mouseover.
* `WindowMode` — Performs the full-screen operation and makes the tab header visible on mouseover.
* `None` — Default value; full-screen mode is disabled.

{% tabs %}
{% highlight XAML %}
<syncfusion:DocumentContainer Name="documentcontainer1" Mode="TDI" TDIFullScreenMode="WindowMode" />
{% endhighlight %}

{% highlight C# %}
using Syncfusion.Windows.Tools.Controls;

documentcontainer1.TDIFullScreenMode = FullScreenMode.WindowMode;
{% endhighlight %}
{% endtabs %}

N> This feature is also applicable for `TabControlExt`, where the equivalent property is `FullScreenMode` of type `Syncfusion.Windows.Tools.Controls.FullScreenMode`.

{% tabs %}
{% highlight XAML %}
<syncfusion:TabControlExt Name="tabcontrol1" FullScreenMode="WindowMode"/>
{% endhighlight %}

{% highlight C# %}
tabcontrol1.FullScreenMode = FullScreenMode.WindowMode;
{% endhighlight %}
{% endtabs %}

## Adding a Toolbar to the Header Panel of TDI Items

A toolbar can be placed in the header panel of TDI items in the WPF Document Container; for this, the `TDIToolBarTray` attached property is used.

![Full-Screen-in-DocumentContainer_img1](Full-Screen-in-DocumentContainer_images/Full-Screen-in-DocumentContainer_img1.jpeg)

{% tabs %}
{% highlight XAML %}
<Window xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:syncfusion="http://schemas.syncfusion.com/wpf"
        x:Class="DocumentContainerSample.MainWindow"
        Title="DocumentContainer Sample" Height="350" Width="525">
    <Grid>
        <syncfusion:DocumentContainer Name="documentcontainer1" Mode="TDI">
            <syncfusion:DocumentContainer.TDIToolBarTray>
                <ToolBarTray>
                    <ToolBar>
                        <Button Content="Tool" />
                    </ToolBar>
                </ToolBarTray>
            </syncfusion:DocumentContainer.TDIToolBarTray>
            <Grid syncfusion:DocumentContainer.Header="tab1" />
            <Grid syncfusion:DocumentContainer.Header="tab2" />
        </syncfusion:DocumentContainer>
    </Grid>
</Window>
{% endhighlight %}

{% highlight C# %}
using System.Windows.Controls;

ToolBarTray tooltray = new ToolBarTray();
ToolBar toolbar = new ToolBar();
toolbar.Items.Add(new Button { Content = "Tool" });
tooltray.ToolBars.Add(toolbar);
documentcontainer1.TDIToolBarTray = tooltray;
{% endhighlight %}
{% endtabs %}

This feature is also applicable to `TabControlExt`, as demonstrated in the following code.

{% tabs %}
{% highlight XAML %}
<syncfusion:TabControlExt Name="tabcontrol">
    <syncfusion:TabControlExt.ToolBarTray>
        <ToolBarTray>
            <ToolBar>
                <Button Content="Tool" />
            </ToolBar>
        </ToolBarTray>
    </syncfusion:TabControlExt.ToolBarTray>
</syncfusion:TabControlExt>
{% endhighlight %}

{% highlight C# %}
ToolBarTray tooltray = new ToolBarTray();
ToolBar toolbar = new ToolBar();
toolbar.Items.Add(new Button { Content = "Tool" });
tooltray.ToolBars.Add(toolbar);
tabcontrol.ToolBarTray = tooltray;
{% endhighlight %}
{% endtabs %}

## SizeToContent for an MDI Window

`SizeToContentInMDI` is used to resize an MDI window to its child size. This is an attached property and can be applied to individual children inside the WPF Document Container. To enable this behavior, set the `Mode` property to `MDI`.

{% tabs %}
{% highlight XAML %}
<Window xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:syncfusion="http://schemas.syncfusion.com/wpf"
        x:Class="DocumentContainerSample.MainWindow"
        Title="DocumentContainer Sample" Height="350" Width="525">
    <Grid>
        <syncfusion:DocumentContainer Mode="MDI">
            <Grid x:Name="grid1" syncfusion:DocumentContainer.SizeToContentInMDI="True" Width="200" Height="200" />
        </syncfusion:DocumentContainer>
    </Grid>
</Window>
{% endhighlight %}

{% highlight C# %}
DocumentContainer.SetSizeToContentInMDI(grid1, true);
{% endhighlight %}
{% endtabs %}

