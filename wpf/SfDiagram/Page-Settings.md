---
layout: post
title:  Customize the size and appearance of single or multiple Diagram pages.
description: How to customize the size and appearance of the Diagram pages?
platform: wpf
control: SfDiagram
documentation: ug
---

#Page Settings

Page settings enable to customize the appearance, width, and height of the Diagram pa page.

![](Page-Settings_images\Page-Settings_img1.jpeg)

##Page size and appearance

The size and appearance of the Diagram pages can be customized with the PageSettings property.

The `PageWidth` and `PageHeight` properties of page settings define the size of the page. In addition to that, you can customize the appearance of the page with a set of appearance specific properties. 

You can also customize the appearance of off-page regions with the property BackgroundColor.

The following code illustrates how to customize the page size and the appearance of page and off-page.

[XAML]

{% highlight xml %}

<diagram:SfDiagram x:Name="diagram" Background="WhiteSmoke">
  <diagram:SfDiagram.PageSettings>
    <diagram:PageSettings PageWidth="500" PageHeight="500" 
                          PageBorderThickness="4" PageBackground="White"
                          PageBorderBrush="LightGray" ShowPageBreaks="True"     
                          MultiplePage="True" PageOrientation="Portrait"/>
    </diagram:SfDiagram.PageSettings> 
  <diagram:SfDiagram.SnapSettings>
    <diagram:SnapSettings SnapConstraints="ShowLines"/>
  </diagram:SfDiagram.SnapSettings>
</diagram:SfDiagram>

{% endhighlight %}

[C#]

{% highlight C# %}

diagram.Background = new SolidColorBrush(Colors.WhiteSmoke);
diagram.PageSettings.PageWidth = 500;
diagram.PageSettings.PageHeight = 500;
diagram.PageSettings.PageBorderThickness = new Thickness(4);
diagram.PageSettings.PageBackground = new SolidColorBrush(Colors.White);
diagram.PageSettings.PageBorderBrush = new SolidColorBrush(Colors.LightGray);
diagram.PageSettings.ShowPageBreaks = true;
diagram.PageSettings.MultiplePage = true;
diagram.PageSettings.PageOrientation = PageOrientation.Portrait;
diagram.SnapSettings.SnapConstraints = SnapConstraints.ShowLines;

{% endhighlight %}

![](Page-Settings_images\Page-Settings_img2.jpeg)

![](Page-Settings_images\Page-Settings_img3.jpeg)

##MultiplePage and PageBreaks

When MutiplePage is enabled, size of the page dynamically increases or decreases in multiple of page width and height and completely fits diagram within the page boundaries. Page Breaks is used as a visual guide to see how pages are split into multiple pages.

![](Page-Settings_images\Page-Settings_img4.jpeg)

`MultiplePage` and `ShowPageBreak` properties of page settings allow you to enable/disable multiple pages and page breaks respectively. The following code illustrates how to enable multiple page and page break lines.

{% highlight C# %}

diagram.PageSettings.ShowPageBreaks = true;
diagram.PageSettings.MultiplePage = true;

{% endhighlight %}