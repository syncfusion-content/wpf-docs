---
layout: post
title: Context menu in WPF TabControl control | Syncfusion
description: Learn here all about Context menu support in Syncfusion WPF TabControl (TabControlExt) control and more.
platform: wpf
control: TabControlExt
documentation: ug
---

# Context menu in WPF TabControl (TabControlExt)

This section explains how to show the tab list and tab item context menu and add custom context menu in [TabControl](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.TabControlExt.html).

## Default tab item context menu

You can close the one or more tab items by using the context menu. You can enable it by using the  [ShowTabItemContextMenu](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.TabControlExt.html#Syncfusion_Windows_Tools_Controls_TabControlExt_ShowTabItemContextMenu) property to `true`. You can open this context menu by right click on tab header. The default value of `ShowTabItemContextMenu` property is `false`.

The built-in tabitem context menu has the following menu items:

* `Close` - Closes the selected tab item.
* `Close All But This` - Closes all the tab items, except the selected tab item.
* `Close All` - Closes all the tab items.

N> The [CloseMode](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.TabControlExt.html#Syncfusion_Windows_Tools_Controls_TabControlExt_CloseMode) in `TabControl` is an enum that includes option `Hide` and `Delete`. When you click any default options (Close, Close All and Close All But This) in tabitem context menu and when the `CloseMode` is set to `Hide`, the tabitem moves to the hidden state or when the `CloseMode` is set to `Delete`, the tabitem is completely deleted from `TabControl`.

{% tabs %}
{% highlight XAML %}

<syncfusion:TabControlExt ShowTabItemContextMenu="True" 
                          CloseMode="Hide"
                          Name="tabControlExt">
    <syncfusion:TabItemExt Content="This is the first tab item"
                           Header="tabItem1"/>
</syncfusion:TabControlExt>

{% endhighlight %}
{% highlight C# %}

tabControlExt.ShowTabItemContextMenu = true;
tabControlExt.CloseMode = CloseMode.Hide;

{% endhighlight %}
{% endtabs %}

![Enable context menu of tab item in TabControl](Contextmenu_images/wpf-tabcontrol-contextmenu.gif)

N> View [Sample](https://github.com/SyncfusionExamples/syncfusion-wpf-tabcontrolext-examples/tree/master/Samples/ContextMenu) in GitHub

### Tab item context menu events

Closing the tab items using the context menu can be notified by following events.

* `Close` option - [OnCloseButtonClick](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.TabControlExt.html) event
* `Close All But This` option - [OnCloseOtherTabs](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.TabControlExt.html) event
* `Close All` option - [OnCloseAllTabs](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.TabControlExt.html) event.

You can use the [CloseTabEventArgs.ClosingTabItems](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.CloseTabEventArgs.html#Syncfusion_Windows_Tools_Controls_CloseTabEventArgs_ClosingTabItems) property to find out which tabitem is closing from the `OnCloseOtherTabs` and  `OnCloseAllTabs` events and use the [CloseTabEventArgs.TargetTabItem](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.CloseTabEventArgs.html#Syncfusion_Windows_Tools_Controls_CloseTabEventArgs_TargetTabItem) property to find out which tabitem is closing from the `OnCloseButtonClick` event.

{% tabs %}
{% highlight XAML %}

<syncfusion:TabControlExt OnCloseAllTabs="TabControlExt_OnCloseAllTabs"
                          OnCloseButtonClick="TabControlExt_OnCloseButtonClick"
                          OnCloseOtherTabs="TabControlExt_OnCloseAllTabs"
                          Name="tabControlExt">
</syncfusion:TabControlExt>

{% endhighlight %}
{% highlight C# %}

tabControlExt.OnCloseAllTabs += TabControlExt_OnCloseAllTabs;
tabControlExt.OnCloseButtonClick += TabControlExt_OnCloseButtonClick;
tabControlExt.OnCloseOtherTabs += TabControlExt_OnCloseOtherTabs;

{% endhighlight %}
{% endtabs %}

You can handle this events as follows,

{% tabs %}
{% highlight C# %}

private void TabControlExt_OnCloseAllTabs(object sender, CloseTabEventArgs e) {
    var closingTabItems = e.ClosingTabItems;
}
private void TabControlExt_OnCloseButtonClick(object sender, CloseTabEventArgs e) {
    var closingTabItem = e.TargetTabItem;
}
private void TabControlExt_OnCloseOtherTabs(object sender, CloseTabEventArgs e) {
    var closingTabItems = e.ClosingTabItems;
}

{% endhighlight %}
{% endtabs %}

## Custom context menu item for the tab items

You can add the custom context menu item for the tab item using the [TabItemExt.ContextMenuItems](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.TabItemExt.html#Syncfusion_Windows_Tools_Controls_TabItemExt_ContextMenuItems) property. You can perform any operation by handling the `CustomMenuItem.Click` event. You can enable it by setting the [TabControlExt.IsCustomTabItemContextMenuEnabled](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.TabControlExt.html#Syncfusion_Windows_Tools_Controls_TabControlExt_IsCustomTabItemContextMenuEnabled) property to `true`. The default value of `TabControlExt.IsCustomTabItemContextMenuEnabled` property is `false`.

{% tabs %}
{% highlight XAML %}

<syncfusion:TabControlExt IsCustomTabItemContextMenuEnabled="True"
                          Name="tabControlExt" >
    <syncfusion:TabItemExt Header="tabItem1">
        
        <!--Adding custom context menu items-->
        <syncfusion:TabItemExt.ContextMenuItems>
            <syncfusion:CustomMenuItem Header="Edit" />
        </syncfusion:TabItemExt.ContextMenuItems>
    </syncfusion:TabItemExt>
</syncfusion:TabControlExt>

{% endhighlight %}
{% highlight C# %}

// Enable custom tabitem context menu
tabControlExt.IsCustomTabItemContextMenuEnabled = true;

// Adding custom context menu for the tabitem
CustomMenuItem customMenuItem = new CustomMenuItem();
customMenuItem.Header = "Edit";
tabItemExt1.ContextMenuItems.Add(customMenuItem);

{% endhighlight %}
{% endtabs %}

![Added custom context menu for tabitem in TabControl](Contextmenu_images/wpf-tabcontrol-customcontextmenu.png)

N> View [Sample](https://github.com/SyncfusionExamples/syncfusion-wpf-tabcontrolext-examples/tree/master/Samples/ContextMenu) in GitHub

### Check or uncheck the custom context menu items

You can check or uncheck the custom menu items by using `CustomMenuItem.IsChecked` property. You can disable the checkable functionalities of the custom context menu item by using the `CustomMenuItem.IsCheckable` property value as `false`. The default value of `CustomMenuItem.IsCheckable` property is `true` and `CustomMenuItem.IsChecked` property value is `false`. 

{% tabs %}
{% highlight XAML %}

<syncfusion:TabControlExt IsCustomTabItemContextMenuEnabled="True"
                          Name="tabControlExt" >
    <syncfusion:TabItemExt Header="tabItem1">
        
        <!--Adding custom context menu items-->
        <syncfusion:TabItemExt.ContextMenuItems>
            <syncfusion:CustomMenuItem Header="Edit"
                                       IsChecked="True"
                                       IsCheckable="True" />
        </syncfusion:TabItemExt.ContextMenuItems>
    </syncfusion:TabItemExt>
</syncfusion:TabControlExt>

{% endhighlight %}
{% highlight C# %}

// Enable custom tabitem context menu
tabControlExt.IsCustomTabItemContextMenuEnabled = true;

// Adding custom context menu for the tabitem
CustomMenuItem customMenuItem = new CustomMenuItem();
customMenuItem.Header = "Edit";
customMenuItem.IsCheckable = true;
customMenuItem.IsChecked = true;
tabItemExt1.ContextMenuItems.Add(customMenuItem);

{% endhighlight %}
{% endtabs %}

![Checked custom context menu for tabitem in TabControl](Contextmenu_images/checkedcustomcontextmenu.png)

N> View [Sample](https://github.com/SyncfusionExamples/syncfusion-wpf-tabcontrolext-examples/tree/master/Samples/ContextMenu) in GitHub

### Adding sub menu items for custom context menu item

You can add sub menu items for custom context menu item with any level by adding that sub `CustomMenuItem` to the parent `CustomMenuItem`.

{% tabs %}
{% highlight XAML %}

<syncfusion:TabControlExt IsCustomTabItemContextMenuEnabled="True"
                          Name="tabControlExt" >
    <syncfusion:TabItemExt Name="tabItem1" Header="tabItem1">
        <syncfusion:TabItemExt.ContextMenuItems>
            <syncfusion:CustomMenuItem Header="Edit">

                <!--Adding sub custom context menu items-->
                <syncfusion:CustomMenuItem Header="SubItem0"/>
                <syncfusion:CustomMenuItem Header="SubItem1"/>
                <syncfusion:CustomMenuItem Header="SubItem2">
                    <syncfusion:CustomMenuItem Header="Level 2"/>
                </syncfusion:CustomMenuItem>
            </syncfusion:CustomMenuItem>
        </syncfusion:TabItemExt.ContextMenuItems>
    </syncfusion:TabItemExt>
    <syncfusion:TabItemExt Name="tabItem2" Header="tabItem2">
        <syncfusion:TabItemExt.ContextMenuItems>
            <syncfusion:CustomMenuItem Header="Edit">

                <!--Adding sub custom context menu items-->
                <syncfusion:CustomMenuItem Header="SubItem0"/>
                <syncfusion:CustomMenuItem Header="SubItem1"/>
                <syncfusion:CustomMenuItem Header="SubItem2">
                    <syncfusion:CustomMenuItem Header="Level 2"/>
                </syncfusion:CustomMenuItem>
            </syncfusion:CustomMenuItem>
        </syncfusion:TabItemExt.ContextMenuItems>
    </syncfusion:TabItemExt>
</syncfusion:TabControlExt>

{% endhighlight %}
{% highlight C# %}

// Enable custom tabitem context menu
tabControlExt.IsCustomTabItemContextMenuEnabled = true;

CustomMenuItem editMenuItem = new CustomMenuItem() { Header = "Edit" };

CustomMenuItem customMenuItem1 = new CustomMenuItem() { Header = "SubItem1" };
CustomMenuItem customMenuItem2 = new CustomMenuItem() { Header = "SubItem2" };
CustomMenuItem customMenuItem3 = new CustomMenuItem() { Header = "SubItem3" };

//Adding sub menu items for 'SubItem3' custom menu item
CustomMenuItem level2_customMenuItem = new CustomMenuItem() { Header = "Level 2" };
customMenuItem3.Items.Add(level2_customMenuItem);

//Adding sub menu items
editMenuItem.Items.Add(customMenuItem1);
editMenuItem.Items.Add(customMenuItem2);
editMenuItem.Items.Add(customMenuItem3);

tabItem1.ContextMenuItems.Add(editMenuItem);
tabItem2.ContextMenuItems.Add(editMenuItem);


{% endhighlight %}
{% endtabs %}

![Added custom context menu with sub items for tabitem in TabControl](Contextmenu_images/subcustomcontextmenu.png)

N> View [Sample](https://github.com/SyncfusionExamples/syncfusion-wpf-tabcontrolext-examples/tree/master/Samples/ContextMenu) in GitHub

## Hide default context menu items

If you want to show only custom context menu items in the default context menu, then you can hide the default context menu item using [TabControlExt.DefaultContextMenuItemVisibility](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.TabControlExt.html#Syncfusion_Windows_Tools_Controls_TabControlExt_DefaultContextMenuItemVisibility) property value as `false`. The default value of `TabControlExt.DefaultContextMenuItemVisibility` property is `true`.

{% tabs %}
{% highlight XAML %}

<syncfusion:TabControlExt IsCustomTabItemContextMenuEnabled="True"
                          DefaultContextMenuItemVisibility="Collapsed"
                          Name="tabControlExt" >
    <syncfusion:TabItemExt Header="tabItemExt1">
        <syncfusion:TabItemExt.ContextMenuItems>
            <syncfusion:CustomMenuItem Header="Edit" />
            <syncfusion:CustomMenuItem Header="Copy" />
            <syncfusion:CustomMenuItem Header="Paste" />
        </syncfusion:TabItemExt.ContextMenuItems>
    </syncfusion:TabItemExt>
</syncfusion:TabControlExt>

{% endhighlight %}
{% highlight C# %}

//Collapse the default contextmenu visibility
tabControlExt.DefaultContextMenuItemVisibility = Visibility.Collapsed;

//Adding custom context menu for the first tabitem
CustomMenuItem customMenuItem1 = new CustomMenuItem() { Header = "Edit"};
CustomMenuItem customMenuItem2 = new CustomMenuItem() { Header = "Copy"};
CustomMenuItem customMenuItem3 = new CustomMenuItem() { Header = "Paste"};

tabItemExt1.ContextMenuItems.Add(customMenuItem1);
tabItemExt1.ContextMenuItems.Add(customMenuItem2);
tabItemExt1.ContextMenuItems.Add(customMenuItem3);

{% endhighlight %}
{% endtabs %}

![Show only the custom context menu items in Default context menu](Contextmenu_images/wpf-tabcontrol-disabledefaultmenu.png)

N> View [Sample](https://github.com/SyncfusionExamples/syncfusion-wpf-tabcontrolext-examples/tree/master/Samples/ContextMenu) in GitHub

## Custom template for default tab item context menu

You can customize the default tab item context menu appearance for the each tab items by using the [TabItemExt.TabItemContextMenuItemTemplate](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.TabItemExt.html#Syncfusion_Windows_Tools_Controls_TabItemExt_TabItemContextMenuItemTemplate) property.

{% tabs %}
{% highlight XAML %}

<Window.Resources>

    <!--Custom data template for the TabItem ContextMenu-->
    <DataTemplate x:Key="TabItemContextMenuItemTemplate"
          DataType="syncfusion:TabItemExt">
        <TextBlock FontFamily="Calibri"
                   Foreground="Blue"
                   FontStyle="Oblique"
                   Text="{Binding}"/>
    </DataTemplate>
</Window.Resources>

<syncfusion:TabControlExt ShowTabItemContextMenu="True" 
                          Name="tabControlExt">
    <syncfusion:TabItemExt TabItemContextMenuItemTemplate=
                                "{StaticResource TabItemContextMenuItemTemplate}"
                           Header="tabItem1"/>
    <syncfusion:TabItemExt TabItemContextMenuItemTemplate=
                                "{StaticResource TabItemContextMenuItemTemplate}"
                           Header="tabItem2" />
</syncfusion:TabControlExt>

{% endhighlight %}
{% endtabs %}

![Customize the default tab item context menu](Contextmenu_images/wpf-tabcontrol-style1.png)

N> View [Sample](https://github.com/SyncfusionExamples/syncfusion-wpf-tabcontrolext-examples/tree/master/Samples/Templates) in GitHub

## Tab list context menu for switching tabs

You can easily navigate to any tab item by using the tab list menu which is placed in the top-right corner of the tab header panel .The header of all visible tab item’s are shown as a menu item in the tab list menu. You can hide this tab list menu by using the [ShowTabListContextMenu](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.TabControlExt.html#Syncfusion_Windows_Tools_Controls_TabControlExt_ShowTabListContextMenu) property value as `false`.  The default value of `ShowTabListContextMenu` property is `true`.

N> The currently selected tab item has a tick mark on the TabListContextMenu.

{% tabs %}
{% highlight XAML %}

<syncfusion:TabControlExt ShowTabListContextMenu="True"
                          Name="tabControlExt">
    <syncfusion:TabItemExt Header="tabItem1" />
    <syncfusion:TabItemExt Header="tabItem2" />
</syncfusion:TabControlExt>

{% endhighlight %}
{% highlight C# %}

tabControlExt.ShowTabListContextMenu = true;

{% endhighlight %}
{% endtabs %}

![Tab items navigate by tab menu items](Tab-Item-Header_images/ShowTabListContextMenu.png)

N> View [Sample](https://github.com/SyncfusionExamples/syncfusion-wpf-tabcontrolext-examples/tree/master/Samples/ContextMenu) in GitHub

## Show hidden tab items in tab list context menu

By default, all the tab items except hidden items are listed in the tab list context menu. If you wants to show the hidden tab items into tab list context menu to navigate, use the [TabListContextMenuOptions](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.TabControlExt.html#Syncfusion_Windows_Tools_Controls_TabControlExt_TabListContextMenuOptions) property value as `Default, ShowHiddenItems`. 

You can set the multiple options for the `TabListContextMenuOptions` to show different types of tab items into the context menu. The default value of `TabListContextMenuOptions` property is `Default`.

{% tabs %}
{% highlight XAML %}

<syncfusion:TabControlExt TabListContextMenuOptions="Default, ShowHiddenItems"
                          ShowTabListContextMenu="True"
                          Name="tabControlExt">
    <syncfusion:TabItemExt Header="tabItem1" Visibility="Collapsed"/>
    <syncfusion:TabItemExt Header="tabItem2"/>
    <syncfusion:TabItemExt Header="tabItem3" Visibility="Collapsed"/>
    <syncfusion:TabItemExt Header="tabItem4" IsEnabled="False"/>
    <syncfusion:TabItemExt Header="tabItem5"/>
    <syncfusion:TabItemExt Header="tabItem6" Visibility="Collapsed"/>
</syncfusion:TabControlExt>

{% endhighlight %}
{% highlight C# %}

tabControlExt.ShowTabListContextMenu = true;
tabControlExt.TabListContextMenuOptions = TabListContextMenuOptions.Default | 
                                          TabListContextMenuOptions.ShowHiddenItems;

{% endhighlight %}
{% endtabs %}

![TabControl shows hidden tab items in tab list context menu](Tab-Item-Header_images/HiddenItems.png)

## Show specific type tab items in tab list context menu

If you want to show the specific type tab items in tab list context menu, set the single option to the `TabListContextMenuOptions` property. If you wants to show only the hidden tab items into tab list context menu to navigate, use the `TabListContextMenuOptions` property value as `ShowHiddenItems`. If you wants to show only the enabled tab items into tab list context menu to navigate, use the `TabListContextMenuOptions` property value as `ShowEnabledItems`. If you wants to show only the disabled tab items into tab list context menu to navigate, use the `TabListContextMenuOptions` property value as `ShowDisabledItems`.

{% tabs %}
{% highlight XAML %}

<syncfusion:TabControlExt TabListContextMenuOptions="ShowEnabledItems"
                          ShowTabListContextMenu="True"
                          Name="tabControlExt">
    <syncfusion:TabItemExt Header="tabItem1" Visibility="Collapsed"/>
    <syncfusion:TabItemExt Header="tabItem2"/>
    <syncfusion:TabItemExt Header="tabItem3" Visibility="Collapsed"/>
    <syncfusion:TabItemExt Header="tabItem4" IsEnabled="False"/>
    <syncfusion:TabItemExt Header="tabItem5"/>
    <syncfusion:TabItemExt Header="tabItem6" Visibility="Collapsed"/>
</syncfusion:TabControlExt>

{% endhighlight %}
{% highlight C# %}

tabControlExt.ShowTabListContextMenu = true;
tabControlExt.TabListContextMenuOptions = TabListContextMenuOptions.ShowEnabledItems;

{% endhighlight %}
{% endtabs %}

![TabControl show only enabled, disabled or hidden tab items on tab list context menu](Tab-Item-Header_images/SingleOption.png)

N> View [Sample](https://github.com/SyncfusionExamples/syncfusion-wpf-tabcontrolext-examples/tree/master/Samples/TabListContextMenuOptions) in GitHub

## Show multi-type tab items in tab list context menu

If you want to show the multiple type of tab items like enabled, disabled or hidden tab items together in tab list context menu, set the multiple options for the `TabListContextMenuOptions` property.

{% tabs %}
{% highlight XAML %}

<syncfusion:TabControlExt TabListContextMenuOptions="ShowDisabledItems,ShowHiddenItems"
                          ShowTabListContextMenu="True"
                          Name="tabControlExt">
    <syncfusion:TabItemExt Header="tabItem1" Visibility="Collapsed"/>
    <syncfusion:TabItemExt Header="tabItem2"/>
    <syncfusion:TabItemExt Header="tabItem3" Visibility="Collapsed"/>
    <syncfusion:TabItemExt Header="tabItem4" IsEnabled="False"/>
    <syncfusion:TabItemExt Header="tabItem5"/>
    <syncfusion:TabItemExt Header="tabItem6" Visibility="Collapsed"/>
</syncfusion:TabControlExt>

{% endhighlight %}
{% highlight C# %}

tabControlExt.ShowTabListContextMenu = true;
tabControlExt.TabListContextMenuOptions = TabListContextMenuOptions.ShowDisabledItems | 
                                          TabListContextMenuOptions.ShowHiddenItems

{% endhighlight %}
{% endtabs %}

![TabControl multiple type of tab items on tab list context menu](Tab-Item-Header_images/MultiOption.png)

## Custom tab list context menu item

You can add the custom tab list context menu items by using the [TabControlExt.TabListContextMenuItems](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.TabcontrolExt.html#Syncfusion_Windows_Tools_Controls_TabControlExt_TabListContextMenuItems) property. You can show only the custom tab list context menu items by setting the [CollapseDefaultTabListContextMenuItems](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.TabControlExt.html#Syncfusion_Windows_Tools_Controls_TabControlExt_CollapseDefaultTabListContextMenuItems) property to `true`. The default value of `CollapseDefaultTabListContextMenuItems` property is `false`.

{% tabs %}
{% highlight XAML %}

<syncfusion:TabControlExt CollapseDefaultTabListContextMenuItems="True"
                          Name="tabControlExt" >
    <syncfusion:TabControlExt.TabListContextMenuItems>
        
        <!--Adding custom context menu items-->
        <syncfusion:CustomMenuItem Header="Menu 1" />
        <syncfusion:CustomMenuItem Header="Menu 2" />
    </syncfusion:TabControlExt.TabListContextMenuItems>
    <syncfusion:TabItemExt Header="tabItem1"/>
    <syncfusion:TabItemExt Header="tabItem2"/>
</syncfusion:TabControlExt>

{% endhighlight %}
{% highlight C# %}

// Display only the custom tab list context menu items
tabControlExt.CollapseDefaultTabListContextMenuItems = true;

// Adding custom tab list context menu items
CustomMenuItem customMenuItem1 = new CustomMenuItem();
customMenuItem1.Header = "Menu 1";
CustomMenuItem customMenuItem2 = new CustomMenuItem();
customMenuItem2.Header = "Menu 2";

tabControlExt.TabListContextMenuItems.Add(customMenuItem1);
tabControlExt.TabListContextMenuItems.Add(customMenuItem2);

{% endhighlight %}
{% endtabs %}

![Added custom tab list context menu item in TabControl](Tab-Item-Header_images/tablistcustomcontextmenu.png)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-tabcontrolext-examples/tree/master/Samples/TabListContextMenuOptions)

### Check or uncheck the custom tab list menu items

You can check or uncheck the custom tab list menu items by using `CustomMenuItem.IsChecked` property. You can disable the checkable functionalities of the tab list menu items by using the `CustomMenuItem.IsCheckable` property value as `false`. The default value of `CustomMenuItem.IsCheckable` property is `true` and `CustomMenuItem.IsChecked` property value is `false`.

{% tabs %}
{% highlight XAML %}

<syncfusion:TabControlExt CollapseDefaultTabListContextMenuItems="True"
                          Name="tabControlExt" >
        
    <!--Adding custom tab list context menu items-->
    <syncfusion:TabControlExt.TabListContextMenuItems>
        
        <!--Adding custom context menu items-->
        <syncfusion:CustomMenuItem Header="Menu 1"
                                   IsCheckable="True"
                                   IsChecked="True"/>
        <syncfusion:CustomMenuItem Header="Menu 2"
                                   IsCheckable="False"/>
    </syncfusion:TabControlExt.TabListContextMenuItems>
    <syncfusion:TabItemExt Header="tabItem1"/>
    <syncfusion:TabItemExt Header="tabItem2"/>

</syncfusion:TabControlExt>

{% endhighlight %}
{% highlight C# %}

// Disaply only the custom tab list context menu
tabControlExt.CollapseDefaultTabListContextMenuItems = true;

// Adding custom tab list context menu items
CustomMenuItem customMenuItem1 = new CustomMenuItem();
customMenuItem1.Header = "Menu 1";
customMenuItem1.IsCheckable = true;
customMenuItem1.IsChecked = true;
CustomMenuItem customMenuItem2 = new CustomMenuItem();
customMenuItem2.Header = "Menu 2";
customMenuItem2.IsCheckable = false;

tabControlExt.TabListContextMenuItems.Add(customMenuItem1);
tabControlExt.TabListContextMenuItems.Add(customMenuItem2);

{% endhighlight %}
{% endtabs %}

![Checked custom tab list context menu in TabControl](Tab-Item-Header_images/checkedcustomtablistcontextmenu.png)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-tabcontrolext-examples/tree/master/Samples/TabListContextMenuOptions)

### Adding sub menu items for custom context menu item

You can add sub menu items for custom context menu item with any level by adding that sub `CustomMenuItem` to the parent `CustomMenuItem`.

{% tabs %}
{% highlight XAML %}

<syncfusion:TabControlExt CollapseDefaultTabListContextMenuItems="True"
                          Name="tabControlExt" >
        
    <!--Adding custom tab list context menu items-->
    <syncfusion:TabControlExt.TabListContextMenuItems>

        <!--Adding custom context menu items-->
        <syncfusion:CustomMenuItem Header="Menu 1">

            <!--Adding sub custom context menu items-->
            <syncfusion:CustomMenuItem Header="SubMenu 1"/>
            <syncfusion:CustomMenuItem Header="SubMenu 2">

                <!--Adding sub custom context menu items for 'SubMenu 2'-->
                <syncfusion:CustomMenuItem Header="Level 2"/>
            </syncfusion:CustomMenuItem>
            <syncfusion:CustomMenuItem Header="SubMenu 3"/>
        </syncfusion:CustomMenuItem>
        <syncfusion:CustomMenuItem Header="Menu 2">

            <!--Adding sub custom context menu items-->
            <syncfusion:CustomMenuItem Header="SubMenu 1"/>
            <syncfusion:CustomMenuItem Header="SubMenu 2"/>
            <syncfusion:CustomMenuItem Header="SubMenu 3">

                <!--Adding sub custom context menu items for 'SubMenu 3'-->
                <syncfusion:CustomMenuItem Header="Level 2"/>
            </syncfusion:CustomMenuItem>
        </syncfusion:CustomMenuItem>
    </syncfusion:TabControlExt.TabListContextMenuItems>
    <syncfusion:TabItemExt Header="tabItem1"/>
    <syncfusion:TabItemExt Header="tabItem2"/>    
</syncfusion:TabControlExt>

{% endhighlight %}
{% highlight C# %}

// Disaply only the custom tab list context menu
tabControlExt.CollapseDefaultTabListContextMenuItems = true;

// Adding custom tab list context menu items
CustomMenuItem menu1 = new CustomMenuItem();
menu1.Header = "Menu 1";
CustomMenuItem menu2 = new CustomMenuItem();
menu2.Header = "Menu 2";

// Creating custom sub menu tab list context menu items
CustomMenuItem customMenuItem1 = new CustomMenuItem() { Header = "SubMenu 1" };
CustomMenuItem customMenuItem2 = new CustomMenuItem() { Header = "SubMenu 2" };
CustomMenuItem customMenuItem3 = new CustomMenuItem() { Header = "SubMenu 3" };

//Adding sub menu items for 'SubMenu 2' and 'SubMenu 3' custom tablist menu item
CustomMenuItem level2_customMenuItem = new CustomMenuItem() { Header = "Level 2" };
customMenuItem3.Items.Add(level2_customMenuItem);

menu2.Items.Add(customMenuItem1);
menu2.Items.Add(customMenuItem2);
menu2.Items.Add(customMenuItem3);

tabControlExt.TabListContextMenuItems.Add(menu1);
tabControlExt.TabListContextMenuItems.Add(menu2);

{% endhighlight %}
{% endtabs %}

![Added custom tab list context menu with sub items in TabControl](Tab-Item-Header_images/subcustomtablistcontextmenu.png)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-tabcontrolext-examples/tree/master/Samples/TabListContextMenuOptions)

## CustomMenuItem as Separator

You can display the separator between custom menu items by using [CustomMenuItem.IsSeparator](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.CustomMenuItem.html#Syncfusion_Windows_Tools_Controls_CustomMenuItem_IsSeparator) property. If  `IsSeparator` property is set to `true`, the `CustomMenuItem` will act as separator. The default value of `CustomMenuItem.IsSeparator` property is `false`.

{% tabs %}
{% highlight XAML %}

<syncfusion:TabControlExt CollapseDefaultTabListContextMenuItems="True"
                          Name="tabControlExt" >
        
    <!--Adding custom tab list context menu items-->
    <syncfusion:TabControlExt.TabListContextMenuItems>

        <!--Adding custom context menu items-->
        <syncfusion:CustomMenuItem Header="Menu 1">

            <!--Adding sub custom context menu items-->
            <syncfusion:CustomMenuItem Header="SubMenu 1"/>
            <syncfusion:CustomMenuItem Header="SubMenu 2">

                <!--Adding sub custom context menu items for 'SubMenu 2'-->
                <syncfusion:CustomMenuItem Header="Level 2"/>
            </syncfusion:CustomMenuItem>
            <syncfusion:CustomMenuItem Header="SubMenu 3"/>
        </syncfusion:CustomMenuItem>

        <!--Adding custom context menu item as Seperator-->
        <syncfusion:CustomMenuItem IsSeparator="True"
                                   Height="1"/>

        <syncfusion:CustomMenuItem Header="Menu 2">

            <!--Adding sub custom context menu items-->
            <syncfusion:CustomMenuItem Header="SubMenu 1"/>
            <syncfusion:CustomMenuItem Header="SubMenu 2"/>
            <syncfusion:CustomMenuItem Header="SubMenu 3">

                <!--Adding sub custom context menu items for 'SubMenu 3'-->
                <syncfusion:CustomMenuItem Header="Level 2"/>
            </syncfusion:CustomMenuItem>
        </syncfusion:CustomMenuItem>
    </syncfusion:TabControlExt.TabListContextMenuItems>
    <syncfusion:TabItemExt Header="tabItem1"/>
    <syncfusion:TabItemExt Header="tabItem2"/>    
</syncfusion:TabControlExt>

{% endhighlight %}
{% highlight C# %}

// Disaply only the custom tab list context menu
tabControlExt.CollapseDefaultTabListContextMenuItems = true;

// Adding custom tab list context menu items
CustomMenuItem menu1 = new CustomMenuItem();
menu1.Header = "Menu 1";
CustomMenuItem menu2 = new CustomMenuItem();
menu2.Header = "Menu 2";

// Adding custom tab list context menu item as Seperator
CustomMenuItem seperator = new CustomMenuItem();
seperator.Seperator = true;
seperator.Height = 1;

// Creating custom sub menu tab list context menu items
CustomMenuItem customMenuItem1 = new CustomMenuItem() { Header = "SubMenu 1" };
CustomMenuItem customMenuItem2 = new CustomMenuItem() { Header = "SubMenu 2" };
CustomMenuItem customMenuItem3 = new CustomMenuItem() { Header = "SubMenu 3" };

//Adding sub menu items for 'SubMenu 2' and 'SubMenu 3' custom tablist menu item
CustomMenuItem level2_customMenuItem = new CustomMenuItem() { Header = "Level 2" };
customMenuItem3.Items.Add(level2_customMenuItem);

menu2.Items.Add(customMenuItem1);
menu2.Items.Add(customMenuItem2);
menu2.Items.Add(customMenuItem3);

tabControlExt.TabListContextMenuItems.Add(menu1);
tabControlExt.TabListContextMenuItems.Add(seperator);
tabControlExt.TabListContextMenuItems.Add(menu2);

{% endhighlight %}
{% endtabs %}

![Added custom menu item as seperator](Tab-Item-Header_images/Seperatorsubcustomtablistcontextmenu.png)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-tabcontrolext-examples/tree/master/Samples/TabListContextMenuOptions)

## Custom template for the tab list context menu

You can customize the tab list menu appearance by using the [TabListContextMenuTemplate](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.TabControlExt.html#Syncfusion_Windows_Tools_Controls_TabControlExt_TabListContextMenuTemplate) property.

{% tabs %}
{% highlight XAML %}

<syncfusion:TabControlExt ShowTabListContextMenu="True" 
                          Name="tabControlExt" >
    <syncfusion:TabControlExt.TabListContextMenuTemplate>
        <ControlTemplate>
            <Border Background="Green">
                <Border Background="Yellow"
                        Margin="5">
                    <Grid>
                        <ItemsPresenter/>
                    </Grid>
                </Border>
            </Border>
        </ControlTemplate>
    </syncfusion:TabControlExt.TabListContextMenuTemplate>
    <syncfusion:TabItemExt Header="tabItem1"/>
    <syncfusion:TabItemExt Header="tabItem2"/>
    <syncfusion:TabItemExt Header="tabItem3"/>
</syncfusion:TabControlExt>

{% endhighlight %}
{% endtabs %}

![Customize the tab list context menu](Contextmenu_images/wpf-tabcontrol-style5.png)

## Custom template for the tab list menu item

You can customize the tab list menu items appearance by using the [TabListContextMenuItemTemplate](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.TabControlExt.html#Syncfusion_Windows_Tools_Controls_TabControlExt_TabListContextMenuItemTemplate) property.

{% tabs %}
{% highlight XAML %}

<syncfusion:TabControlExt ShowTabListContextMenu="True" 
                          Name="tabControlExt" >
    <syncfusion:TabControlExt.TabListContextMenuItemTemplate>
        <DataTemplate>
            <TextBlock FontFamily="Calibri"
                       Foreground="Blue"
                       FontStyle="Oblique"
                       Text="{Binding}"/>
        </DataTemplate>
    </syncfusion:TabControlExt.TabListContextMenuItemTemplate>
    <syncfusion:TabItemExt Header="tabItem1" />
    <syncfusion:TabItemExt Header="tabItem2" />
</syncfusion:TabControlExt>

{% endhighlight %}
{% endtabs %}

![Customize the tab list context menu items](Contextmenu_images/wpf-tabcontrol-style.png)

N> View [Sample](https://github.com/SyncfusionExamples/syncfusion-wpf-tabcontrolext-examples/tree/master/Samples/Templates) in GitHub
