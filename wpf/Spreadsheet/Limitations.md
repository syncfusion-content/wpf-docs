---
layout: post
title: Limitations in WPF Spreadsheet control | Syncfusion
description: Learn here all about Limitations support in Syncfusion WPF Spreadsheet (SfSpreadsheet) control and more.
platform: wpf
control: SfSpreadsheet
documentation: ug
---

# Limitations in WPF Spreadsheet (SfSpreadsheet)

## Release memory held by AutomationPeer

SfSpreadsheet holds some instance in memory even after disposing the spreadsheet or removed the sheets from the spreadsheet. Because, the **AutomationPeer** for WPF Components holds some memory and it needs to be released manually. This can be done by using the following steps.

Create a class derived from `WindowAutomationPeer` and override it's `GetChildrenCore` method and returns “null” value that clears the **AutomationPeer** item from memory as follows

{% tabs %}
{% highlight c# %}
public class FakeWindowsPeer : WindowAutomationPeer
{

    public FakeWindowsPeer (Window window): base(window)
    { }

    protected override List<AutomationPeer> GetChildrenCore()
    {
        return null;
    }
}
{% endhighlight %}
{% endtabs %}

Now override the `OnCreateAutomationPeer` of the window and it returns the class as follows.

{% tabs %}
{% highlight c# %}
public partial class MainWindow : Window
{

    public MainWindow()
    {
        InitializeComponent();
    }

    protected override AutomationPeer OnCreateAutomationPeer()
    {
        return new FakeWindowsPeer(this);
    }
}
{% endhighlight %}
{% endtabs %}
