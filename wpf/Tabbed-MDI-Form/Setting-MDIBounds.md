---
layout: post
title: Setting MDIBounds in WPF DocumentContainer | Syncfusion®
description: Configure the bounds such as position and size for MDI child windows in the Syncfusion WPF Tabbed MDI Form (DocumentContainer) control.
platform: wpf
control: DocumentContainer
documentation: ug
---

# Setting MDIBounds in WPF Document Container

The `MDIBounds` attached property helps the WPF Document Container place its elements within the container in MDI mode. The property is set on each child element, rather than to the container itself.

The general syntax of the `MDIBounds` attached property is given below.

```
Syncfusion:DocumentContainer.MDIBounds="x,y,width,height"
```

where:

* The first two values (`x` and `y`) stand for the X and Y coordinates of the MDI bounds.
* The next two values (`width` and `height`) stand for the width and height of the element in the WPF Document Container.

To set the MDI bounds, use the following code snippet.

{% tabs %}
{% highlight XAML %}
<syncfusion:DocumentContainer Name="DocContainer" Mode="MDI">
    <FlowDocumentScrollViewer syncfusion:DocumentContainer.MDIBounds="0,0,200,300" />
    <!-- additional child windows -->
</syncfusion:DocumentContainer>
{% endhighlight %}
{% highlight C# %}
FlowDocumentScrollViewer flow = new FlowDocumentScrollViewer();
DocumentContainer.SetMDIBounds(flow, new Rect(0, 0, 200, 300));
DocContainer.Items.Add(flow);
{% endhighlight %}
{% endtabs %}

![DocumentContainer with a child window placed using MDIBounds](Setting-MDIBounds_images/Setting-MDIBounds_img1.jpeg)



