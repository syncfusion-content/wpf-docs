---
layout: post
title: Setting Mode in WPF DocumentContainer | Syncfusion®
description: Switch the document container between MDI and TDI modes in the Syncfusion WPF Tabbed MDI Form (DocumentContainer) control as needed.
platform: wpf
control: DocumentContainer
documentation: ug
---

# Setting Mode in WPF DocumentContainer

The DocumentContainer supports the following two modes:

* **TDI** - Tabbed Document Interface (default)
* **MDI** - Multiple Document Interface

You can change the mode using the [Mode](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DocumentContainer.html#Syncfusion_Windows_Tools_Controls_DocumentContainer_Mode) property of the DocumentContainer, which uses the `Syncfusion.Windows.Tools.Controls.DocumentContainerMode` enum.

## Setting the Mode to TDI

{% tabs %}
{% highlight XAML %}
<syncfusion:DocumentContainer Name="DocContainer" Mode="TDI">
    <!-- child elements -->
</syncfusion:DocumentContainer>
{% endhighlight %}

{% highlight C# %}
// Creating an instance of DocumentContainer
DocumentContainer docContainer = new DocumentContainer();
// Set the mode to TDI
docContainer.Mode = DocumentContainerMode.TDI;
// Add the control to the window
this.Content = docContainer;
{% endhighlight %}
{% endtabs %}

![DocumentContainer in TDI mode](Setting-Mode-for-Document-Container_images/Setting-Mode-for-Document-Container_img1.jpeg)

## Setting the Mode to MDI

{% tabs %}
{% highlight XAML %}
<syncfusion:DocumentContainer Name="DocContainer" Mode="MDI">
    <!-- child elements -->
</syncfusion:DocumentContainer>
{% endhighlight %}

{% highlight C# %}
// Creating an instance of DocumentContainer
DocumentContainer docContainer = new DocumentContainer();
// Set the mode to MDI
docContainer.Mode = DocumentContainerMode.MDI;
// Add the control to the window
this.Content = docContainer;
{% endhighlight %}
{% endtabs %}

![DocumentContainer in MDI mode](Setting-Mode-for-Document-Container_images/Setting-Mode-for-Document-Container_img2.jpeg)
