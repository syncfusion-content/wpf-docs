---
layout: post
title: NewButton Feature | TabControlExt Control | Syncfusion
description: Learn about how to create new button in Syncfusion WPF TabControlExt control and more details about the control features.
platform: wpf
control: TabControlExt
documentation: ug
---

# NewButton Feature in TabControl (TabControlExt)

This section explains how to create new tab items using new button and its UI customization in the [TabControl](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.TabControlExt.html). 

## Adding New tab button and new tab item

You can add a new tab item at runtime by clicking the new button. You can enable it by using the [IsNewButtonEnabled](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.TabControlExt.html#Syncfusion_Windows_Tools_Controls_TabControlExt_IsNewButtonEnabled) property. You should handle the click action of the New Button and add a new tab items to `TabControl` by using the [NewButtonClick](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.TabControlExt.html) event. The new button can be aligned first or last position in the tab item header panel by using the [NewButtonAlignment](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.TabControlExt.html#Syncfusion_Windows_Tools_Controls_TabControlExt_NewButtonAlignment) property. The default value of `IsNewButtonEnabled` property is `false` and `NewButtonAlignment` property is `Last`.

{% tabs %}
{% highlight XAML %}

<syncfusion:TabControlExt NewButtonClick="tabControlExt_NewButtonClick"
                          IsNewButtonEnabled="True"
                          NewButtonAlignment="Last"
                          Name="tabControlExt">
    <syncfusion:TabItemExt Header="tabItem1" />
    <syncfusion:TabItemExt Header="tabItem2" />
</syncfusion:TabControlExt>

{% endhighlight %}
{% highlight C# %}

tabControlExt.NewButtonClick += tabControlExt_NewButtonClick;
tabControlExt.IsNewButtonEnabled = true;
tabControlExt.NewButtonAlignment = NewButtonAlignment.Last;

{% endhighlight %}
{% endtabs %}

You can handle the event as follows:

{% tabs %}
{% highlight C# %}

private void tabControlExt_NewButtonClick(object sender, EventArgs e) {
    TabItemExt tabItemExt1 = new TabItemExt()
    {
        Header = "tabItem"+ (tabControlExt.Items.Count + 1),
        Content = new TextBlock() { Text = "This is the content area of TabItem" }
    };

    //Adding new tab item into the TabControl.
    tabControlExt.Items.Add(tabItemExt1);
}

{% endhighlight %}
{% endtabs %}

![New tab item added by new button click](NewButton-Feature_images/NewButton.png)

N> View [Sample](https://github.com/SyncfusionExamples/syncfusion-wpf-tabcontrolext-examples/tree/master/Samples/NewButton) in GitHub

## Auto hide new button when no child tab item

The `TabControl` automatically hides the new button on when no child tab item present in the `TabControl`. If you want to always show the new button, use the [IsNewButtonClosedonNoChild](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.TabControlExt.html#Syncfusion_Windows_Tools_Controls_TabControlExt_IsNewButtonClosedonNoChild) property value as `false`. The default value of `IsNewButtonClosedonNoChild` property is `true`.

{% tabs %}
{% highlight XAML %}

<syncfusion:TabControlExt IsNewButtonClosedonNoChild="False"
                          Name="tabControlExt">
    <syncfusion:TabItemExt Content="This is the first tab item"
                           Header="tabItem1"/>
</syncfusion:TabControlExt>

{% endhighlight %}
{% highlight C# %}

tabControlExt.IsNewButtonClosedonNoChild = false;

{% endhighlight %}
{% endtabs %}

![TabControl always show the new button](NewButton-Feature_images/NewButtonShow.png)

N> View [Sample](https://github.com/SyncfusionExamples/syncfusion-wpf-tabcontrolext-examples/tree/master/Samples/NewButton) in GitHub

## Custom template for the new button

If you wants to change the UI for the new button, use the [NewTabButtonTemplate](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.TabControlExt.html#Syncfusion_Windows_Tools_Controls_TabControlExt_NewTabButtonTemplate) property. 

{% tabs %}
{% highlight XAML %}

<syncfusion:TabControlExt IsNewButtonEnabled="True"
                          x:Name="tabControlExt">
    <syncfusion:TabControlExt.NewTabButtonTemplate>
        <DataTemplate>
            <Button Background="Red" 
                    Content=" + "></Button>
        </DataTemplate>
    </syncfusion:TabControlExt.NewTabButtonTemplate>
    <syncfusion:TabItemExt Header="tabItem1" Name="tabItemExt1"/>
    <syncfusion:TabItemExt Header="tabItem2" Name="tabItemExt2"/>
</syncfusion:TabControlExt>

{% endhighlight %}
{% endtabs %}

![Custom UI for the new button](NewButton-Feature_images/CustomNewButton.png)

N> View [Sample](https://github.com/SyncfusionExamples/syncfusion-wpf-tabcontrolext-examples/tree/master/Samples/NewButton) in GitHub

## Change background of new button

If you want to change the background of the new button, use the [NewButtonBackground](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.TabControlExt.html#Syncfusion_Windows_Tools_Controls_TabControlExt_NewButtonBackground) property. The default value of `NewButtonBackground` property is `null`.

{% tabs %}
{% highlight XAML %}

<syncfusion:TabControlExt NewButtonBackground="Red"
                          Name="tabControlExt">
    <syncfusion:TabItemExt Content="This is the first tab item"
                           Header="tabItem1"/>
</syncfusion:TabControlExt>

{% endhighlight %}
{% highlight C# %}

tabControlExt.NewButtonBackground = Brushes.Red;

{% endhighlight %}
{% endtabs %}

![Red color applied for the new button background](NewButton-Feature_images/NewButtonBackground.png)

N> View [Sample](https://github.com/SyncfusionExamples/syncfusion-wpf-tabcontrolext-examples/tree/master/Samples/NewButton) in GitHub