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

<syncfusion:Ribbon Name="ribbon" HorizontalAlignment="Stretch" VerticalAlignment="Top">
    <syncfusion:RibbonTab Name="ribbonTab1" Caption="HOME"  >
        <syncfusion:RibbonBar Name="ribbonBar1" Header="RibbonBar1">
            <syncfusion:RibbonButton Label="Cut"/>
            <syncfusion:RibbonButton Label="Copy"/>
        </syncfusion:RibbonBar>
        <syncfusion:RibbonBar Name="ribbonBar2" Width="150" Header="RibbonBar2">
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

RibbonCheckBox ribbonCheckBox = new RibbonCheckBox(){ Content = "SelectAll", IsChecked=true };
ribbonBar2.Items.Add(ribbonCheckBox);

{% endhighlight %}

{% highlight VB %}

Dim ribbonCheckBox As New RibbonCheckBox() With {
	.Content = "SelectAll",
	.IsChecked=True
}

ribbonBar2.Items.Add(ribbonCheckBox)

{% endhighlight %}

{% endtabs %}

![Output](RibbonCheckBox_images/RibbonCheckBox_img1.jpg)

## See Also

[How to add the RibbonCheckBox in WPF Ribbon control with MVVM pattern?](https://github.com/SyncfusionExamples/How-to-add-the-ribboncheckbox-in-wpf-ribbon-control-with-mvvm-pattern).
