---
title: Mini Toolbar of WPF RichTextBox | Syncfusion
description: This section describes about how to use the mini toolbar in WPF RichTextBox.
platform: wpf
control: SfRichTextBoxAdv
documentation: ug
keywords: mini-toolbar
---
# Mini Toolbar

The SfRichTextBoxAdv supports built-in mini toolbar to provide rich text formatting options such as Bold, Italic etc. The following screenshot shows built-in mini toolbar of SfRichTextBoxAdv control.
![Shows built-in mini toolbar of WPF SfRichTextBoxAdv](Mini-Toolbar_images/Mini-Toolbar_img1.jpeg)

## Enable/Disable Mini Toolbar

In SfRichTextBoxAdv, the built-in mini toolbar is enabled by default. It is possible to enable/disable the built-in mini toolbar. The following code example demonstrates how to disable the built-in mini toolbar in SfRichTextBoxAdv.
{% tabs %}
{% highlight xaml %}
<RichTextBoxAdv:SfRichTextBoxAdv x:Name="richTextBoxAdv" EnableMiniToolBar="False" xmlns:RichTextBoxAdv="clr-namespace:Syncfusion.Windows.Controls.RichTextBoxAdv;assembly=Syncfusion.SfRichTextBoxAdv.Wpf" />

{% endhighlight %}
{% highlight c# %}
// Initializes a new instance of RichTextBoxAdv.
SfRichTextBoxAdv richTextBoxAdv = new SfRichTextBoxAdv();

//Disables the built-in mini tool bar in SfRichTextBoxAdv.
richTextBoxAdv.EnableMiniToolBar = false;

{% endhighlight %}
{% highlight VB %}
' Initializes a new instance of RichTextBoxAdv.
Dim richTextBoxAdv As New SfRichTextBoxAdv()

'Disables the built-in mini tool bar in SfRichTextBoxAdv.
richTextBoxAdv.EnableMiniToolBar = False


{% endhighlight %}
{% endtabs %}
