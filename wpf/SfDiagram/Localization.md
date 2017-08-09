---
layout: post
title: Globalize and Localize the Diagram control.
description: How to globalize and localize the Diagram control?
platform: wpf
control: SfDiagram
documentation: ug
---

# Localization

Localization is the process of providing controls in different cultures to help you set your own culture easily. Diagram provides localization support for Context Menu items.

## Customizing Context Menu

![](Localization_images/Localization_img1.jpeg)

The following code illustrates how to provide localization support for Context Menu items.


{% highlight C# %}
System.Threading.Thread.CurrentThread.CurrentUICulture = new System.Globalization.CultureInfo("fr");//French

System.Resources.ResourceManager manager;

Assembly assembly = Application.Current.GetType().Assembly;

manager = new System.Resources.ResourceManager("Localization.Resources.Syncfusion.SfDiagram.WPF", 

          assembly);

{% endhighlight%}

![](Localization_images/Localization_img2.jpeg)

N> You have to define the textual descriptions of the context menu items for your custom cultures.

