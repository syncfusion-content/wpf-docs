---
layout: post
title: Adding Items to the Application Menu | Ribbon | WPF | Syncfusion
description: adding items to the application menu
platform: wpf
control: Ribbon
documentation: ug
---

# Adding Items to the Application Menu

Different menu items are added to an application menu using the MenuItems property of the ApplicationMenu class. The following lines of code should be added under the <ribbon: ApplicationMenu></ribbon:ApplicationMenu> tag to add menu items to an application menu.

{% highlight xml %}






<ribbon:Ribbon.ApplicationMenu>

 <ribbon:ApplicationMenu Width="38" Height="38" ribbon:Ribbon.KeyTip="F" ApplicationButtonImage="/SampleImages/app.png">

    <ribbon:SimpleMenuButton Label="New" Icon="/SampleImages/Document32.png"/>

    <ribbon:SimpleMenuButton Label="Open" Icon="SampleImages/Open32.png" Command="ApplicationCommands.Open" />

    <ribbon:SimpleMenuButton Label="Save" Icon="SampleImages/Save32.png" Command="ApplicationCommands.Save">

 </ribbon:ApplicationMenu>

</ribbon:Ribbon.ApplicationMenu>

 {% endhighlight %}





## Multi-line support for Menu Items



Ribbon instance now enables the user to add more detailed description to the menu items with the help of multi line support for menu items, thereby making it easy for the users to select proper menu items without any difficulties.

## See Also

[Adding Application Menu to the Ribbon Window](http://help.syncfusion.com/wpf/ribbon/adding-application-menu-to-the-ribbon-window), [Adding Application Items to the Application Menu](http://help.syncfusion.com/wpf/ribbon/adding-application-items-to-the-application-menu)

