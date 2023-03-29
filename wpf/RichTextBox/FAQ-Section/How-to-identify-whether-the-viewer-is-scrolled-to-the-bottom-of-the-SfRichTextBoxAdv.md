---
title: Identify whether the viewer is scrolled to the bottom in the WPF SfRichTextBoxAdv | Syncfusion
description: Learn here all about how to identify whether the viewer is scrolled to the bottom in Syncfusion WPF SfRichTextBoxAdv and more.
platform: wpf
control: SfRichTextBoxAdv
documentation: ug
keywords: scroll-to-bottom
---

# Identify whether the viewer is scrolled to the bottom in the WPF SfRichTextBoxAdv

This page explains how to identify whether the viewer is scrolled to the bottom in Syncfusion WPF SfRichTextBoxAdv.

SfRichTextBoxAdv scrollbars can be accessed through the [VerticalScrollBar](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.RichTextBoxAdv.SfRichTextBoxAdv.html#Syncfusion_Windows_Controls_RichTextBoxAdv_SfRichTextBoxAdv_VerticalScrollBar) and [HorizontalScrollBar](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.RichTextBoxAdv.SfRichTextBoxAdv.html#Syncfusion_Windows_Controls_RichTextBoxAdv_SfRichTextBoxAdv_HorizontalScrollBar) properties of [SfRichTextBoxAdv](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.RichTextBoxAdv.SfRichTextBoxAdv.html) class. Using these properties, we can identify when the document is scrolled to the bottom of the control. 

We can use the ValueChanged event of the [VerticalScrollBar](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.RichTextBoxAdv.SfRichTextBoxAdv.html#Syncfusion_Windows_Controls_RichTextBoxAdv_SfRichTextBoxAdv_VerticalScrollBar) for this purpose. Check if the scroll bar's value equals the [VerticalScrollBar](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.RichTextBoxAdv.SfRichTextBoxAdv.html#Syncfusion_Windows_Controls_RichTextBoxAdv_SfRichTextBoxAdv_VerticalScrollBar) Maximum property value, if these values are equal then the vertical scroll bar has been scrolled to the bottom of the control.

The following code example illustrates to identify whether the viewer is scrolled to the bottom of the SfRichTextBoxAdv.

{% endhighlight %}
{% highlight c# %}
/// <summary>
///  Occurs when the element is laid out, rendered, and ready for interaction.
/// </summary>
/// <param name="sender">The source of the event.</param>
/// <param name="e">The RoutedEventArgs instance containing the event data.</param>
 private void RichTextBoxAdv_Loaded(object sender, RoutedEventArgs e)
 {
     if (richTextBoxAdv.VerticalScrollBar != null)
	 {
         richTextBoxAdv.VerticalScrollBar.ValueChanged += VerticalScrollBar_ValueChanged;
     }
 }      

/// <summary>
/// Occurs when vertical scrollbar value is changed.
/// </summary>
/// <param name="sender">The source of the event.</param>
/// <param name="e">The RoutedPropertyChangedEventArgs instance containing the event data.</param>
 private void VerticalScrollBar_ValueChanged(object sender, RoutedPropertyChangedEventArgs<double> e)
 {
     if (e.NewValue == richTextBoxAdv.VerticalScrollBar.Maximum)
     {
             ///When the scroll bar value and its maximum value are same.
             ///Then scroll reached the bottom of the control.
     }
 }
		