---
layout: post
title: Restricting-Tab-Item-Closing
description: restricting tab item closing
platform: wpf
control: TabControlExt
documentation: ug
---

# Restricting Tab Item Closing

The closure of TabItem can now be restricted by setting e.Cancel to true in OnCloseButtonClick delegate. “e” represents the event argument CloseTabEventArgs for OnCloseButtonClick event. The default value of e.Cancel is false.

The following code illustrates the same.



[XAML]



&lt;syncfusion:TabControlExt  OnCloseButtonClick="OnCloseButtonClick" &gt;

&lt;Grid syncfusion:TabControlExt.Header="Tab1" /&gt;

    &lt;Grid syncfusion:TabControlExt.Header="Tab2" /&gt;

        &lt;Grid syncfusion:TabControlExt.Header="Tab3" /&gt;

&lt;/syncfusion:TabControlExt&gt;



[C#]



private void SelectedItemChangedEvent(object sender, CloseTabEventArgs e)

{

    if(e.TargetTabItem.Header.ToString()=="Tab2")

    {

        e.Cancel=true;

    }      

}



