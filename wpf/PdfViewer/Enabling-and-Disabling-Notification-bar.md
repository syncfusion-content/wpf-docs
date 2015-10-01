---
layout: post
title: Enabling-and-Disabling-Notification-bar
description: enabling and disabling notification bar
platform: wpf
control: PDF Viewer
documentation: ug
---

# Enabling and Disabling Notification bar

Notification bar is a part of the PDF Viewer that is used to display when an unexpected error occurs in the PDF Viewer control. You can suppress the display of the Notification bar by setting the EnableNotificationBar property to false. The following code example illustrate the same.

{% tabs %}
{% highlight C# %}

// Hiding the scrollbar of the PDF Viewer

pdfviewer1.EnableNotificationBar= false;
{% endhighlight %}


{% highlight vbnet %}

' Hiding the scrollbar of the PDF Viewer

pdfviewer1.EnableNotificationBar= False

{% endhighlight %}
{% endtabs %}