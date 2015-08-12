---
layout: post
title: SplitMenuButton-Popup-KeyTip
description: splitmenubutton popup keytip
platform: wpf
control: Ribbon
documentation: ug
---

# SplitMenuButton Popup KeyTip

SplitMenuButton has now comes with separate key tip for pop-up menu. Separate keytips can be assigned for SplitMenuButton to:

* Invoke the SplitMenuButton
* Open the popup



The following code snippet illustrates how to set keytip for SplitMenuButton Popup.



{% highlight xml %}


[XAML]
<syncfusion:SplitMenuButton Label="Print" Name="printBtn" syncfusion:Ribbon.SplitMenuKeyTip="U" syncfusion:Ribbon.KeyTip="PR">
{% endhighlight %}

{% highlight C# %}


[C#]
Ribbon.SetKeyTip(printBtn, "PR");Ribbon.SetSplitMenuKeyTip(printBtn, "U");
{% endhighlight %}


![](SplitMenuButton-Popup-KeyTip_images/SplitMenuButton-Popup-KeyTip_img1.jpeg)



