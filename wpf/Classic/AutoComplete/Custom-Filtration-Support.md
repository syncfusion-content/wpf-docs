---
layout: post
title: Custom Filtration Support in WPF AutoComplete Control | Syncfusion
description: Learn here all about Custom Filtration Support in Syncfusion WPF AutoComplete (Classic) control and more.
platform: wpf
control: AutoComplete
documentation: ug
---

# Custom Filtration Support in WPF AutoComplete (Classic)

AutoComplete supports Custom Filtration of items, which allows you to specify three different search modes for displaying the drop-down list. The [StringMode](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.AutoComplete.html#Syncfusion_Windows_Tools_Controls_AutoComplete_StringMode) property is used to specify the search mode.

When the value of the [StringMode](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.AutoComplete.html#Syncfusion_Windows_Tools_Controls_AutoComplete_StringMode) property is set as StartChar, AutoComplete begins its search from starting index of the strings in the source list collection and the matching results will be displayed in the drop-down list. In the figure shown below, AutoComplete searches using the entered key “D” and displays the matched list.

![custom filteration support](Custom-Filtration-Support_images/Custom-Filtration-Support_img1.png)

StringMode—StartChar
{:.caption}

When the value of the StringMode property is set as IndexBased, starting index value can be set using the StringModeIndex property. In this mode AutoComplete begins its search from the user specified index of the strings in the source list collection and the matching results will be displayed in the drop-down list. In the figure shown below StringModeIndex value is set as “2” and the entered text is “i”. The AutoComplete displays the list of items which has “i” in the specified index.

![custom filteration support](Custom-Filtration-Support_images/Custom-Filtration-Support_img2.png)

StringMode—IndexBased
{:.caption}

When the value of the StringMode property is set as AnyChar, the AutoComplete searches for the strings which has substrings entered in the AutoComplete control. In the figure shown below, based on the entered text “I”, the AutoComplete displays the list of items which has as a substring in it.

![custom filteration support](Custom-Filtration-Support_images/Custom-Filtration-Support_img3.png)

StringMode—AnyChar
{:.caption}

## Using custom filtration support in an application 

The [StringMode](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.AutoComplete.html#Syncfusion_Windows_Tools_Controls_AutoComplete_StringMode) property will be used to attain this functionality by setting its value as StartChar or IndexBased or AnyChar.

{% tabs %}
{% highlight xaml %}

<syncfusion:AutoComplete x:Name="AutoComplete1" StringMode="StartChar"/>
<syncfusion:AutoComplete x:Name="AutoComplete2" StringMode="IndexBased"/>
<syncfusion:AutoComplete x:Name="AutoComplete3" StringMode="AnyChar"/>

{% endhighlight %}

{% highlight c# %}

AutoComplete autoComplete1 = new AutoComplete();
this.autoComplete1.StringMode = StringMode.StartChar;
AutoComplete autoComplete2 = new AutoComplete();
this.autoComplete2.StringMode = StringMode.IndexBased;
this.autoComplete2.StringModeIndex = 2;
AutoComplete autoComplete3 = new AutoComplete();
this.autoComplete3.StringMode = StringMode.AnyChar;

{% endhighlight %}
{% endtabs %}

## Sample Link

WPF Sample Browser-> Tools -> Editors -> AutoComplete Demo
