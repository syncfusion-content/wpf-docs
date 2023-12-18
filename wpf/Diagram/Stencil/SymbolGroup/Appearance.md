---
layout: post
title: SymbolGroup appearance in WPF Diagram control | Syncfusion
description: Learn here all about the appearance of the SymbolGroup in Stencil of the Syncfusion WPF Diagram (SfDiagram) .
platform: wpf
control: SfDiagram
documentation: ug
---

# Appearance of SymbolGroup in WPF Diagram (SfDiagram)

The appearance of the SymbolGroup in the Stencil can be changed by the SymbolGroupDisplayMode property. We can view Symbolgroups in the Accordion, List, and Tab view in the Stencil.Default value of the SymbolGroupDisplayMode is Accordion.

{% tabs %}
{% highlight xaml %}
        <!--Initialize the stencil-->
        <stencil:Stencil x:Name="stencil" Title="Shapes" SymbolGroupDisplayMode="Accordion" BorderThickness="1" BorderBrush="Black">
        </stencil:Stencil>
{% endhighlight %}
{% highlight c# %}
            //Define a Stencil.
            Stencil stencil = new Stencil()
            {
                Title = "Shapes",
                SymbolGroupDisplayMode = SymbolGroupDisplayMode.Accordion,
                BorderThickness = new Thickness(1),
                BorderBrush = new SolidColorBrush(Colors.Black),
            };
{% endhighlight %}
{% endtabs %}

|SymbolGroupDisplayMode|Description|Output|
|----------|-----------|-----------|
| Accordion | Symbolgroups will be displayed in the Accordion view. |![Accordion_View](SymbolGroup_images/Accordion.png)|
| List | Symbolgroups will be displayed in the List view. |![List_View](SymbolGroup_images/List.png)|
| Tab | Symbolgroups will be displayed in the Tab view. |![Tab_View](SymbolGroup_images/Tab.png)|