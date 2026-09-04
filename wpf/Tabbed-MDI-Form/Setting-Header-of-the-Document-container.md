---
layout: post
title: Setting Header in WPF DocumentContainer | Syncfusion®
description: Set or customize the header text of documents in the Syncfusion WPF Tabbed MDI Form (DocumentContainer) control for clear identification.
platform: wpf
control: Tabbed MDI Form
documentation: ug
---

# Setting Header in WPF Document Container

Using the `Header` attached property, the user can set the header for each child element. The `Header` accepts any `object`, so the header text can be customized using a `HeaderTemplate`. Use the following code snippet to set the header for a WPF Document Container element.

{% tabs %}
{% highlight XAML %}
<syncfusion:DocumentContainer Name="DocContainer" Mode="MDI">
    <FlowDocumentScrollViewer x:Name="flow" syncfusion:DocumentContainer.Header="Features" />
    <!-- additional child windows -->
</syncfusion:DocumentContainer>
{% endhighlight %}
{% endtabs %}

## Setting the Header Programmatically

The header of a WPF Document Container element can be set by the `SetHeader` static method.

{% tabs %}
{% highlight C# %}
DocumentContainer.SetHeader(flow, "Features");
{% endhighlight %}
{% endtabs %}

![Setting-Header-of-the-Document-container_img1](Setting-Header-of-the-Document-container_images/Setting-Header-of-the-Document-container_img1.jpeg)


