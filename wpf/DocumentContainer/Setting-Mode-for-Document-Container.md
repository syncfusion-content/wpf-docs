---
layout: post
title: Setting-Mode-for-Document-Container
description: setting mode for document container
platform: wpf
control: DocumentContainer
documentation: ug
---

# Setting Mode for Document Container

Document Container supports two important modes which are listed below. 

* TDI - Tabbed Document Interface
* MDI - Multiple Document Interface

To set the Document Container in TDI mode, use the following code snippet.


{% highlight xml %}
<!-- Adding Document Container -->
<syncfusion:DocumentContainer Name="DocContainer" Mode="TDI">
…...
.…....</syncfusion:DocumentContainer>
{% endhighlight %}

{% highlight C# %}
//Creating instance of Document Containe
rDocumentContainer DocContainer = new DocumentContainer();
//Set mode as TDI
DocContainer.Mode = DocumentContainerMode.TDI;
….......….......
//Adding control to window
this.Content = DocContainer;
{% endhighlight %}


The following is the screen shot of a document container, which is in TDI mode.



![](Setting-Mode-for-Document-Container_images/Setting-Mode-for-Document-Container_img1.jpeg)





To set the Document Container in MDI mode, use the following code snippet.


{% highlight xml %}
<!-- Adding Document Container -->
<syncfusion:DocumentContainer Name="DocContainer" Mode="MDI">
  ….... 
  …....
  </syncfusion:DocumentContainer>
  {% endhighlight %}
  
{% highlight C# %} 
//Creating instance of Document Container
DocumentContainer DocContainer = new DocumentContainer();
//Set mode as MDIDocContainer.Mode = DocumentContainerMode.MDI;
….......
….......
//Adding control to window
this.Content = DocContainer;
{% endhighlight %}


The following screen shot shows the document container in MDI mode.



![](Setting-Mode-for-Document-Container_images/Setting-Mode-for-Document-Container_img2.jpeg)



