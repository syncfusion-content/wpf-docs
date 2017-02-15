---
layout: post
title: Restricting Tab Item Closing | TabControlExt | wpf | Syncfusion
description: restricting tab item closing
platform: wpf
control: TabControlExt
documentation: ug
---

# Restricting Tab Item Closing

The closure of TabItem can now be restricted by setting e.Cancel to true in OnCloseButtonClick delegate. “e” represents the event argument CloseTabEventArgs for OnCloseButtonClick event. The default value of e.Cancel is false.

The following code illustrates the same.

{% tabs %}

{% highlight xaml %}

<syncfusion:TabControlExt OnCloseButtonClick="TabControlExt_OnCloseButtonClick">

            <syncfusion:TabItemExt Header="Tab1"/>
            
            <syncfusion:TabItemExt Header="Tab2"/>
            
            <syncfusion:TabItemExt Header="Tab3"/>
            
</syncfusion:TabControlExt>

{% endhighlight %}

{% highlight c# %}

private void TabControlExt_OnCloseButtonClick(object sender, CloseTabEventArgs e)

{
            
        if (e.TargetTabItem.Header.ToString() == "Tab1")
           e.Cancel = true;

 }

{% endhighlight %}

{% endtabs %}