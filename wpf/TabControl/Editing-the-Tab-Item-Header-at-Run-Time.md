---
layout: post
title: Edit the Tab Header at Run Time | TabControlExt | wpf | Syncfusion
description: editing the tab item header at run time
platform: wpf
control: TabControlExt
documentation: ug
---

# Editing the Tab Item Header at Run Time

You can edit the header of the Tab Item at run time by enabling the [EnableLabelEdit](https://help.syncfusion.com/cr/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.TabControlExt~EnableLabelEdit.html) dependency property. The following code snippet sets this property.


{% highlight xaml %}

<!-- Adding TabControlExt  -->

<syncfusion:TabControlExt Margin="20" Name="tabControlExt" EnableLabelEdit="True">

    <!-- Adding TabItemExt -->

    <syncfusion:TabItemExt Name="tabItemExt1" Header="TabItemExt1">

        <!-- Adding content to TabItemExt -->

        <TextBlock TextWrapping="Wrap">This is TabItemExt2</TextBlock>

    </syncfusion:TabItemExt>

</syncfusion:TabControlExt>

{% endhighlight %}


![Edit the tab item header at run time](Editing-the-Tab-Item-Header-at-Run-Time_images/Editing-the-Tab-Item-Header-at-Run-Time_img1.jpeg)

{% seealso %}

[Editing the Tab Item Header at Run Time](https://help.syncfusion.com/wpf/tabext/editing-the-tab-item-header-at-run-time)

[Tab Item Header Image](https://help.syncfusion.com/wpf/tabext/tab-item-header#header-image)

[Tab Item Header Image Alignment](https://help.syncfusion.com/wpf/tabext/tab-item-header#image-alignment) 

[Context Menu for the Tab Item](https://help.syncfusion.com/wpf/tabext/setting-tablistcontextmenu-and-tabitemcontextmenu-for-tab-item)

{% endseealso %}