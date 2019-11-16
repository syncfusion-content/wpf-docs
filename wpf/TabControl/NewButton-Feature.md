---
layout: post
title: NewButton Feature | TabControlExt | wpf | Syncfusion
description: newbutton feature
platform: wpf
control: TabControlExt
documentation: ug
---

# NewButton Feature

New button feature in TabControlExt is used to display NewTabButton similar to IE7. User can handle the click action of that NewButton to add new tab items to TabControlExt.

{% tabs %}

{% highlight xaml %}

<syncfusion:TabControlExt  Name=”tabcontrol” IsNewButtonEnabled=”True” NewButtonClick="TabControlExt_NewTabItemClick" >

    <Grid  syncfusion:TabControlExt.Header=”Tab1”>

        <Grid syncfusion:TabControlExt.Header=”Tab2”/>

</syncfusion:TabControlExt>

{% endhighlight %}

{% highlight c# %}

private void TabControlExt_NewTabItemClick(object sender, EventArgs e)

{

    TabItemExt item = new TabItemExt

    {

        Header = "Tab" + (tabcontrol.Items.Count + 1),

    };

    tabcontrol.Items.Add(item);

}

{% endhighlight %}

{% endtabs %}



Run the code. The following output is displayed.

![NewButton Feature](NewButton-Feature_images/NewButton-Feature_img1.jpeg)


This New button can also displayed at first end using the code below.

{% tabs %}

{% highlight xaml %}

<syncfusion:TabControlExt  Name=”tabcontrol” IsNewButtonEnabled=”True” NewButtonAlignment=”First”  NewButtonClick="TabControlExt_NewTabItemClick" >

    <Grid  syncfusion:TabControlExt.Header=”Tab1”>

        <Grid syncfusion:TabControlExt.Header=”Tab2”/>

</syncfusion:TabControlExt>

{% endhighlight %}

{% highlight c# %}

private void TabControlExt_NewTabItemClick(object sender, EventArgs e)

{

    TabItemExt item = new TabItemExt

    {

        Header = "Tab" + (tabcontrol.Items.Count + 1),

    };

    tabcontrol.Items.Add(item);

}

{% endhighlight %}

{% endtabs %}



Run the code. The following output is displayed.

![New button template](NewButton-Feature_images/NewButton-Feature_img2.jpeg)

Template and style for new button can be overridden by using NewButtonTemplate and [NewButtonStyle](https://help.syncfusion.com/cr/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.TabControlExt~NewButtonStyle.html) properties.  [NewButtonBorderThickness](https://help.syncfusion.com/cr/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.TabControlExt~NewButtonBorderThickness.html) and [NewButtonBackground](https://help.syncfusion.com/cr/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.TabControlExt~NewButtonBackground.html) can be used to specify thickness of the border and background for the new button.

The following code illustrates the same.


{% tabs %}

{% highlight xaml %}

<syncfusion:TabControlExt Name="tabcontrol" NewButtonAlignment="Last" NewButtonBackground="Yellow" NewButtonBorderThickness="20” NewButtonClick="TabControlExt_NewTabItemClick" NewButtonStyle="{StaticResource mystyle}" IsNewButtonEnabled="True" Loaded="tabcontrol_Loaded">

</syncfusion:TabControlExt>

{% endhighlight %}

{% highlight c# %}

private void TabControlExt_NewTabItemClick(object sender, EventArgs e)

{

    TabItemExt extab = new TabItemExt

    {

        Header = "content",

    };

    tabcontrol.Items.Add(extab);

}

{% endhighlight %}

{% endtabs %}



