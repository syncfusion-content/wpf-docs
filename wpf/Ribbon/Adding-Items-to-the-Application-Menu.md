---
layout: post
title: Adding-Items-to-the-Application-Menu
description: adding items to the application menu
platform: wpf
control: Ribbon
documentation: ug
---

# Adding Items to the Application Menu

Different menu items are added to an application menu using the MenuItems property of the ApplicationMenu class. The following lines of code should be added under the &lt;ribbon: ApplicationMenu&gt;&lt;/ribbon:ApplicationMenu&gt; tag to add menu items to an application menu.



[XAML]



&lt;ribbon:Ribbon.ApplicationMenu&gt;

 &lt;ribbon:ApplicationMenu Width="38" Height="38" ribbon:Ribbon.KeyTip="F" ApplicationButtonImage="/SampleImages/app.png"&gt;

    &lt;ribbon:SimpleMenuButton Label="New" Icon="/SampleImages/Document32.png"/&gt;

    &lt;ribbon:SimpleMenuButton Label="Open" Icon="SampleImages/Open32.png" Command="ApplicationCommands.Open" /&gt;

    &lt;ribbon:SimpleMenuButton Label="Save" Icon="SampleImages/Save32.png" Command="ApplicationCommands.Save"&gt;

 &lt;/ribbon:ApplicationMenu&gt;

&lt;/ribbon:Ribbon.ApplicationMenu&gt;



Multi-line support for Menu Items



Ribbon instance now enables the user to add more detailed description to the menu items with the help of multi line support for menu items, thereby making it easy for the users to select proper menu items without any difficulties.

See Also

Adding Application Menu to the Ribbon Window, Adding Application Items to the Application Menu

