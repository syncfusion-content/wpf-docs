---
layout: post
title: Selection Mode | SfAccordion | WPF | Syncfusion
description: Selection Mode of SfAccordion control for WPF
platform: WPF
control: SfAccordion
documentation: ug
---

# Expansion Modes

`SfAccordion` provides a property [SelectionMode](https://help.syncfusion.com/cr/wpf/Syncfusion.SfAccordion.WPF~Syncfusion.Windows.Controls.Layout.SfAccordion~SelectionMode.html) that helps to decide the number of items that can be expanded or selected at a time. The values of [SelectionMode](https://help.syncfusion.com/cr/wpf/Syncfusion.SfAccordion.WPF~Syncfusion.Windows.Controls.Layout.SfAccordion~SelectionMode.html) are

1. One
2. OneOrMore
3. ZeroOrOne
4. ZeroOrMore

The default selection mode is One. 

## SelectionMode - One

* Only one item can be in expanded/selected state.
* One item must be in expanded/selected state.
* Does not allows to unselect all the item. 

## SelectionMode - OneOrMore

* More than one item can be in expanded/selected state. 
* One item must be in expanded/selected state.
* Does not allows to unselect all the item. 

## SelectionMode - ZeroOrOne

* Only one item can be in expanded/selected state.
* Allows to unselect all the item. 

## SelectionMode - ZeroOrMore

* More than one item can be in expanded/selected state.
* Allows to unselect all the item. 

Here is an example showing OneOrMore [SelectionMode](https://help.syncfusion.com/cr/wpf/Syncfusion.SfAccordion.WPF~Syncfusion.Windows.Controls.Layout.SfAccordion~SelectionMode.html):

{% tabs %}

{% highlight XAML %}

    <layout:SfAccordion SelectionMode="OneOrMore">

    <layout:SfAccordionItem Header="WPF" Content="Essential Studio for WPF"/>

    <layout:SfAccordionItem Header="Silverlight" Content="Essential Studio for Silverlight"/>

    <layout:SfAccordionItem Header="WinRT" Content="Essential Studio for WinRT"/>

    <layout:SfAccordionItem Header="Windows Phone" Content="Essential Studio for Windows Phone"/>

    <layout:SfAccordionItem Header="Universal" Content="Essential Studio for Universal"/>

    </layout:SfAccordion>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

    accordion.SelectionMode = AccordionSelectionMode.OneOrMore;

{% endhighlight %}

{% highlight VB %}

    accordion.SelectionMode = AccordionSelectionMode.OneOrMore

{% endhighlight %}

{% endtabs %}

![Expansion modes](Selection-Mode-images/Selection-Mode-img1.jpeg)


