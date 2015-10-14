---
layout: post
title: Adding Items to Drop Down Menu of the Quick Access Toolbar | Ribbon | WPF | Syncfusion
description: adding items to drop-down menu of the quick access toolbar
platform: wpf
control: Ribbon
documentation: ug
---

# Adding Items to Drop-Down Menu of the Quick Access Toolbar

You can add items to the drop-down menu of the Quick Access Toolbar by using the QATMenuItems property of the the QuickAccessToolbar. The following code example illustrates how to add items to the drop-down menu of the Quick Access Toolbar by using this property.

{% highlight xml %}

    



<syncfusion:Ribbon.QuickAccessToolBar>

<syncfusion:QuickAccessToolBar>

    <syncfusion:QuickAccessToolBar.QATMenuItems>

        <syncfusion:RibbonButton Label="Testing1" />

        <syncfusion:RibbonButton Label="Testing2" />

    </syncfusion:QuickAccessToolBar.QATMenuItems>

</syncfusion:QuickAccessToolBar>

 {% endhighlight %}





You can also dynamically add items to the drop-down menu of the Quick Access Toolbar by using the Add method of the the QATMenuItems. The following code example illustrates how to add items to the drop-down menu of the Quick Access Toolbar by using this method.

{% highlight c# %}
 
    



RibbonButton button1 = new RibbonButton();

button1.Label = "Testing1";



RibbonButton button2 = new RibbonButton();

button2.Label = "Testing2";



this.ribbon1.QuickAccessToolBar.QATMenuItems.Add(button1);

this.ribbon1.QuickAccessToolBar.QATMenuItems.Add(button2);

 {% endhighlight %}





![](Adding-Items-to-Drop-Down-Menu-of-the-Quick-Access-Toolbar_images/Adding-Items-to-Drop-Down-Menu-of-the-Quick-Access-Toolbar_img1.jpeg)




## See Also

[Quick Access Toolbar](http://help.syncfusion.com/wpf/ribbon/quick-access-toolbar)

