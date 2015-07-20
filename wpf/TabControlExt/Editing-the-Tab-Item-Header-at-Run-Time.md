---
layout: post
title: Editing-the-Tab-Item-Header-at-Run-Time
description: editing the tab item header at run time
platform: wpf
control: TabControlExt
documentation: ug
---

# Editing the Tab Item Header at Run Time

You can edit the header of the Tab Item at run time by enabling the EnableLabelEdit dependency property. The following code snippet sets this property.



[XAML]



<!-- Adding TabControlExt  -->

<syncfusion:TabControlExt Margin="20" Name="tabControlExt" EnableLabelEdit="True">



    <!-- Adding TabItemExt -->

    <syncfusion:TabItemExt Name="tabItemExt1" Header="TabItemExt1">



        <!-- Adding content to TabItemExt -->

        <TextBlock TextWrapping="Wrap">This is TabItemExt2</TextBlock>

    </syncfusion:TabItemExt>

</syncfusion:TabControlExt>



{{ '![](Editing-the-Tab-Item-Header-at-Run-Time_images/Editing-the-Tab-Item-Header-at-Run-Time_img1.jpeg)' | markdownify }}
{:.image }




See Also

Editing the Tab Item Header at Run Time, Tab Item Header Image, Tab Item Header Image Alignment, Context Menu for the Tab Item

