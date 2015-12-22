---
layout: Post
title: Mini-Toolbar-Support
description: mini toolbar support
platform: wpf
control: RichTextBoxAdv
documentation: ug
---
### Mini Toolbar support 

The **RichTextBoxAdv** provides support for built-in **Mini** **Toolbar** that is enabled by default. You can enable/disable the built-in Mini Toolbar by using the **EnableMiniToolBar** property of the **RichTextBoxAdv**. 

![](Mini-Toolbar-Support_images/Mini-Toolbar-Support_img1.jpeg)


The following code example demonstrates how to disable the built-in mini toolbar in the **RichTextBoxAdv**. 

{% highlight xaml %}
<syncfusion:SfRichTextBoxAdv x:Name="richTextBoxAdv" EnableMiniToolBar="False" xmlns:Syncfusion="clr-namespace:Syncfusion.Windows.Controls.RichTextBoxAdv;assembly=Syncfusion.SfRichTextBoxAdv.WPF" />



{% endhighlight %}

{% highlight c# %}
//Disables the built-in mini toolbar in the RichTextBoxAdv.

richTextBoxAdv.EnableMiniToolBar = false;



{% endhighlight %}

![](Mini-Toolbar-Support_images/Mini-Toolbar-Support_img2.jpeg)
__**Note**____**:**__ __**The**__ __**mini**__ __**tool**__ __**bar**__ __**is**__ __**automatically**__ __**disabled**__ __**when**__ __**IsReadOnly**__ __**property**__ __**is**__ __**set**__ __**to**__ __**True**__ __**and**__ __**also**__ __**in**__ __**Block**__ __**layout**____**.**____****__

