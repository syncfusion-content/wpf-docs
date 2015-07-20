---
layout: post
title: Adding-Application-Menu-to-the-Ribbon-Window
description: adding application menu to the ribbon window
platform: wpf
control: Ribbon
documentation: ug
---

# Adding Application Menu to the Ribbon Window

You can add an application menu to the ribbon window. An application menu contains standard commands that are performed in any office applications. This menu is viewed by clicking the button at the top-left corner of the window. You can also customize the image in the application menu button. An application menu is added to a ribbon window by using the ApplicationMenu property of the Ribbon class. The following code snippet is used to add an application menu to a ribbon window.



[XAML]



&lt;ribbon:Ribbon.ApplicationMenu&gt;

  &lt;ribbon:ApplicationMenu Width="38" Height="38" ribbon:Ribbon.KeyTip="F"&gt;

    ...

  &lt;/ribbon:ApplicationMenu&gt;

&lt;/ribbon:Ribbon.ApplicationMenu&gt;



Image is added to application menu button by using the ApplicationButtonImage property of the ApplicationMenu class. The following code is used to add an image to application menu button.



[XAML]



&lt;ribbon:Ribbon.ApplicationMenu&gt;

  &lt;ribbon:ApplicationMenu Width="38" Height="38" ribbon:Ribbon.KeyTip="F" ApplicationButtonImage="/SampleImages/app.png" &gt;

  &lt;/ribbon:ApplicationMenu&gt;

&lt;/ribbon:Ribbon.ApplicationMenu&gt;



{ ![](Adding-Application-Menu-to-the-Ribbon-Window_images/Adding-Application-Menu-to-the-Ribbon-Window_img1.jpeg) | markdownify }
{:.image }




See Also

Adding Items to the Application Menu, Adding Application Items to the Application Menu

