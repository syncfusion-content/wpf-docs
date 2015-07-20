---
layout: post
title: Adding-Application-Items-to-the-Application-Menu
description: adding application items to the application menu
platform: wpf
control: Ribbon
documentation: ug
---

# Adding Application Items to the Application Menu

Application Items are the items that are displayed in the right pane of the Application menu. Application Items are used to add items like recently used programs, Recent Documents, and so on. The following lines of code are used to add Application Items to the Application Menu.



[XAML]



<ribbon:ApplicationMenu.ApplicationItems>

  <ribbon:ButtonPanel Margin="5,0,5,0">

    <ribbon:RibbonButton SizeForm = "Small" Label="Options SmallIcon="SampleImages/Options.png"/>

  </ribbon:ButtonPanel>

  <ribbon:ButtonPanel>

    <ribbon:RibbonButton SizeForm = "Small" Label="Exit" Command="ApplicationCommands.Close" SmallIcon="SampleImages/Exit.png"/>

  </ribbon:ButtonPanel>

</ribbon:ApplicationMenu.ApplicationItems>



{{ '![](Adding-Application-Items-to-the-Application-Menu_images/Adding-Application-Items-to-the-Application-Menu_img1.jpeg)' | markdownify }}
{:.image }




See Also

Adding Application Menu to the Ribbon Window, Adding Items to the Application Menu

