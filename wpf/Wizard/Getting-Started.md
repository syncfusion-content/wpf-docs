---
layout: post
title: Getting Started | Wizard | wpf | Syncfusion
description: getting started
platform: wpf
control: Wizard
documentation: ug
---

# Getting Started

This section guides you on getting started with Wizard control. It covers the following topics:

## Why to use our Wizard control

Here are some highlights of our Wizard control.

* Wizard controls contains the Wizard Page, which is used to add wizard pages
* Each wizard page has the Next, Close, Back, Help and Finish buttons for navigating through the wizard pages
* Provides support to customize the appearance



## Creating Wizard Control

Wizard control is created programmatically by using either XAML or C# code. The following lines of code can be used to create the Wizard control.


{%tabs%}
{% highlight xaml %}




<syncfusion:WizardControl Name="wizardControl"/>
{% endhighlight %}

{% highlight C# %}




// "grid" is the name of grid panel

WizardControl wizardControl = new WizardControl();            

grid.Children.Add(wizardControl); 
{% endhighlight %}

{%endtabs%}

N> For creating Wizard control using C# code, you must already have a panel in which you are going to add the control. Otherwise, the control cannot be displayed.

 

![](Getting-Started_images/Getting-Started_img1.jpeg)



