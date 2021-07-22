---
title: Document Properties in WPF RichTextBox control | Syncfusion
description: Learn here all about Document Properties support in Syncfusion WPF RichTextBox (SfRichTextBoxAdv) control and more.
platform: wpf
control: SfRichTextBoxAdv
documentation: ug
keywords: Word count, paragraph count, page count, current page number.
---
# Document Properties in WPF RichTextBox (SfRichTextBoxAdv)
[WPF RichTexBox](https://www.syncfusion.com/wpf-controls/richtextbox) keep tracking the statistics about your documents. These statistics contains information about word count, paragraph count and pages count.

## Word Count
RichTextBox automatically counts the number of words in a document while you type. You can get the words count from [WordCount](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.RichTextBoxAdv.SfRichTextBoxAdv.html#Syncfusion_Windows_Controls_RichTextBoxAdv_SfRichTextBoxAdv_WordCount.html) property. The default value of this property is 0. 

The following sample code demonstrates how to get the total number of words in the document.
{% tabs %}
{% highlight Xaml %}
<TextBlock Text="{Binding Path=WordCount, Mode=TwoWay}"  />

{% endhighlight %}
{% highlight C# %}
int wordCount.Text = richTextBoxAdv.WordCount.ToString();

{% endhighlight %}
{% highlight VB %}
wordCount.Text = richTextBoxAdv.WordCount.ToString()

{% endhighlight %}
{% endtabs %}

## Paragraph Count
RichTextBox automatically counts the number of paragraphs in a document while you type. You can get the paragraph count from [ParagraphCount](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.RichTextBoxAdv.SfRichTextBoxAdv.html#Syncfusion_Windows_Controls_RichTextBoxAdv_SfRichTextBoxAdv_ParagraphCount.html) property. The default value of this property is 0. Also, it ignores empty paragraphs.

The following sample code demonstrates how to get the total number of paragraphs in the document.
{% tabs %}
{% highlight Xaml %}
<TextBlock Name="ParagraphCount" Text="{Binding Path=ParagraphCount, Mode=TwoWay}" />

{% endhighlight %}
{% highlight C# %}
int paragraphCount.Text = richTextBoxAdv.ParagraphCount.ToString();

{% endhighlight %}
{% highlight VB %}
paragraphCount.Text = richTextBoxAdv.ParagraphCount.ToString()

{% endhighlight %}
{% endtabs %}

## Page Count
RichTextBox counts the number of pages in a document while you type. You can get the pages count from [PageCount](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.RichTextBoxAdv.SfRichTextBoxAdv.html#Syncfusion_Windows_Controls_RichTextBoxAdv_SfRichTextBoxAdv_ParagraphCount.html) property. The default value of this property is 0.

The following sample code demonstrates how to get the total number of pages in the document.
{% tabs %}
{% highlight Xaml %}
<TextBlock x:Name="PageCount" Grid.Row="0" />
<RichTextBoxAdv:SfRichTextBoxAdv Grid.Row="1" x:Name="richTextBoxAdv" SelectionChanged="RichTextBoxAdv_SelectionChanged"/>

{% endhighlight %}
{% highlight C# %}
private void RichTextBoxAdv_SelectionChanged(object obj, SelectionChangedEventArgs args)
{
	pageCount.Text = richTextBoxAdv.PageCount.ToString();
}

{% endhighlight %}
{% highlight VB %}
Private Sub RichTextBoxAdv_SelectionChanged(ByVal obj As Object, ByVal args As SelectionChangedEventArgs)
pageCount.Text = richTextBoxAdv.PageCount.ToString()
End Sub

{% endhighlight %}
{% endtabs %}

## Current Page number
The [CurrentPageNumber](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.RichTextBoxAdv.SfRichTextBoxAdv.html#Syncfusion_Windows_Controls_RichTextBoxAdv_SfRichTextBoxAdv_CurrentPageNumber.html) property in the RichTextBox control returns the page number where the selection(cursor) is present.

The following sample code demonstrates how to get current page number in the document.

{% tabs %}
{% highlight Xaml %}
<TextBlock x:Name="CurrentPageNumber" Grid.Row="0" />
<RichTextBoxAdv:SfRichTextBoxAdv Grid.Row="1" x:Name="richTextBoxAdv" SelectionChanged="RichTextBoxAdv_SelectionChanged"/>

{% endhighlight %}
{% highlight C# %}
private void RichTextBoxAdv_SelectionChanged(object obj, SelectionChangedEventArgs args)
{
	currentPageNumber.Text = richTextBoxAdv.CurrentPageNumber.ToString();
}

{% endhighlight %}
{% highlight VB %}
Private Sub RichTextBoxAdv_SelectionChanged(ByVal obj As Object, ByVal args As SelectionChangedEventArgs)
    currentPageNumber.Text = richTextBoxAdv.CurrentPageNumber.ToString()
End Sub

{% endhighlight %}
{% endtabs %}

N> The above PageCount and CurrentPageNumber properties are not a dependency property. And it is not notifying for dynamic changes. So, get these properties value in
selection changed event.
You can also explore our [WPF RichTextBox example](https://github.com/syncfusion/wpf-demos/tree/master/richtextbox) to knows how to render and configure the editing tools. 

