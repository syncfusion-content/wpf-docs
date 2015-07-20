---
layout: post
title: Disables-the-Unload-of-TabItemExt-Content
description: disables the unload of tabitemext content
platform: wpf
control: TabControlExt
documentation: ug
---

# Disables the Unload of TabItemExt Content

While switching the TabItems in TabControl the content of previously selected items will be unloaded. To enable or disable unload of TabItemExt content the IsDisableUnloadTabItemExtContent property can be used. 



XAML

&lt;syncfusion:TabControlExt Name="tabcontrol" IsDisableUnloadTabItemExtContent="True"&gt;

   &lt;syncfusion:TabItemExt Header="tab1"&gt;

     &lt;TextBlock Text="content1" Unloaded="TextBlock_Unloaded"/&gt;

   &lt;/syncfusion:TabItemExt&gt;

   &lt;syncfusion:TabItemExt Header="tab2"&gt;

     &lt;TextBlock Text="content2" Unloaded="TextBlock_Unloaded_1"/&gt;

   &lt;/syncfusion:TabItemExt&gt;

&lt;/syncfusion:TabControlExt&gt;





C#

tabcontrol.IsDisableUnloadTabItemExtContent = true;



When the value is set to true the TabItem content will not get unloaded during tab switching.

