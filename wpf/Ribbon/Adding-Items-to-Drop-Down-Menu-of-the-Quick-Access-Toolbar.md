---
layout: post
title: Adding-Items-to-Drop-Down-Menu-of-the-Quick-Access-Toolbar
description: adding items to drop-down menu of the quick access toolbar
platform: wpf
control: Ribbon
documentation: ug
---

# Adding Items to Drop-Down Menu of the Quick Access Toolbar

You can add items to the drop-down menu of the Quick Access Toolbar by using the QATMenuItems property of the the QuickAccessToolbar. The following code example illustrates how to add items to the drop-down menu of the Quick Access Toolbar by using this property.



[XAML]



&lt;syncfusion:Ribbon.QuickAccessToolBar&gt;

&lt;syncfusion:QuickAccessToolBar&gt;

    &lt;syncfusion:QuickAccessToolBar.QATMenuItems&gt;

        &lt;syncfusion:RibbonButton Label="Testing1" /&gt;

        &lt;syncfusion:RibbonButton Label="Testing2" /&gt;

    &lt;/syncfusion:QuickAccessToolBar.QATMenuItems&gt;

&lt;/syncfusion:QuickAccessToolBar&gt;



You can also dynamically add items to the drop-down menu of the Quick Access Toolbar by using the Add method of the the QATMenuItems. The following code example illustrates how to add items to the drop-down menu of the Quick Access Toolbar by using this method.



[C#]



RibbonButton button1 = new RibbonButton();

button1.Label = "Testing1";



RibbonButton button2 = new RibbonButton();

button2.Label = "Testing2";



this.ribbon1.QuickAccessToolBar.QATMenuItems.Add(button1);

this.ribbon1.QuickAccessToolBar.QATMenuItems.Add(button2);



{ ![](Adding-Items-to-Drop-Down-Menu-of-the-Quick-Access-Toolbar_images/Adding-Items-to-Drop-Down-Menu-of-the-Quick-Access-Toolbar_img1.jpeg) | markdownify }
{:.image }




See Also

Quick Access Toolbar

