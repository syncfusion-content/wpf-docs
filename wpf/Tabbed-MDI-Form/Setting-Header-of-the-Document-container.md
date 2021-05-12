---
layout: post
title: Setting Header of Document container in Tabbed MDI Form | Syncfusion
description: Learn here all about Setting Header of the Document container support in Syncfusion WPF Tabbed MDI Form (DocumentContainer) control and more.
platform: wpf
control: Tabbed MDI Form
documentation: ug
---

# Setting Header of the Document container in WPF Tabbed MDI Form

Using the `Header` property, user can set the header for the DocumentContainer elements. Use the following code snippet, to set the header for the DocumentContainer element.


{% highlight xaml %}

<!-- Adding Document Container -->

<syncfusion:DocumentContainer Name="DocContainer"  Mode="MDI">

<FlowDocumentScrollViewer x:Name="flow" syncfusion:DocumentContainer.Header="Features">

</FlowDocumentScrollViewer>

…....

…....

</syncfusion:DocumentContainer>

{% endhighlight %}

### Setting header programmatically

Header of the DocumentContainer elements can be set by `SetHeader` method. 

{% tabs %}

{% highlight C# %}

//Set the Header of the DocumentContainer

DocumentContainer.SetHeader(flow, "Features");

{% endhighlight %}

{% endtabs %}

![Setting-Header-of-the-Document-container_img1](Setting-Header-of-the-Document-container_images/Setting-Header-of-the-Document-container_img1.jpeg)


