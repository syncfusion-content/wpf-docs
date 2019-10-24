---
layout: post
title: TabItemValidation Support | TabControlExt | wpf | Syncfusion
description: tabitemvalidation support
platform: wpf
control: TabControlExt
documentation: ug
---

# TabItemValidation Support

TabItem now allows you cancel the selection of a tab item by setting e.Cancel=true in [SelectedItemChangedEvent](https://help.syncfusion.com/cr/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.TabControlExt~SelectedItemChangedEvent_EV.html) delegate.

The following code illustrates the same.

{% tabs %}

{% highlight xaml %}

<syncfusion:TabControlExt  SelectedItemChangedEvent="SelectedItemChanged" >

    <Grid syncfusion:TabControlExt.Header="Tab1" />

        <Grid syncfusion:TabControlExt.Header="Tab2" />

            <Grid syncfusion:TabControlExt.Header="Tab3" />

</syncfusion:TabControlExt>

{% endhighlight %}

{% highlight c# %}

private void SelectedItemChangedEvent(object sender,SelectedItemChangedEventArgs e)

{

    if(e.NewSelectedItem.Header.ToString()=="Tab2")

    {

        e.Cancel=true;

    }      

}

{% endhighlight %}

{% endtabs %}
