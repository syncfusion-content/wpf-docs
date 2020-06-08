---
layout: post
title: RibbonCheckBox in Syncfusion Ribbon control
description: This section deals with explain about the RibbonCheckBox support in Syncfusion Ribbon control on WPF platform
platform: wpf
control: Ribbon
documentation: ug
---
# RibbonCheckBox in WPF Ribbon

[RibbonCheckBox](https://help.syncfusion.com/cr/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.RibbonCheckBox.html) is used to select or unselect options. It provides similar set of functionalities like normal CheckBox control in [Ribbon](https://help.syncfusion.com/cr/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.Ribbon.html).

The following code example illustrates how to use [RibbonCheckBox](https://help.syncfusion.com/cr/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.RibbonCheckBox.html) control in [Ribbon](https://help.syncfusion.com/cr/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.Ribbon.html) instance.

{% tabs %}

{% highlight XAML %}

<syncfusion:Ribbon Name="_ribbon" HorizontalAlignment="Stretch" VerticalAlignment="Top">
    <syncfusion:RibbonTab Name="_ribbonTab1" Caption="HOME"  >
        <syncfusion:RibbonBar Name="_ribbonBar1" Header="RibbonBar1">
            <syncfusion:RibbonButton Label="Cut"/>
            <syncfusion:RibbonButton Label="Copy"/>
        </syncfusion:RibbonBar>
        <syncfusion:RibbonBar Name="_ribbonBar2" Width="150" Header="RibbonBar2">
            <syncfusion:RibbonCheckBox  Width="140" Content="SelectAll" IsChecked="True"/>
        </syncfusion:RibbonBar>
    </syncfusion:RibbonTab>
    <syncfusion:RibbonTab Caption="EDIT"  IsChecked="False"/>
</syncfusion:Ribbon>

{% endhighlight %}

{% endtabs %}

Create instance of [RibbonCheckBox](https://help.syncfusion.com/cr/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.RibbonCheckBox.html) and add it to [RibbonBar](https://help.syncfusion.com/cr/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.RibbonBar.html) through code behind.

{% tabs %}

{% highlight C# %}

RibbonCheckBox _ribbonCheckBox = new RibbonCheckBox(){Content = "SelectAll", IsChecked=true };
_ribbonBar2.Items.Add(_ribbonCheckBox);

{% endhighlight %}

{% highlight VB %}

Dim _ribbonCheckBox As New RibbonCheckBox() With {
	.Content = "SelectAll",
	.IsChecked=True
}

_ribbonBar2.Items.Add(_ribbonCheckBox)

{% endhighlight %}

{% endtabs %}

![Output](RibbonCheckBox_images/RibbonCheckBox_img1.jpg)

A sample that demonstrates to add the RibbonCheckBox in Ribbon control with MVVM pattern is available [here](https://github.com/SyncfusionExamples/How-to-add-the-ribboncheckbox-in-wpf-ribbon-control-with-mvvm-pattern).
