---
layout: post
title: TabItemValidation-Support
description: tabitemvalidation support
platform: wpf
control: TabControlExt
documentation: ug
---

# TabItemValidation Support

TabItem now allows you cancel the selection of a tab item by setting e.Cancel=true in SelectedItemChangedEvent delegate.

The following code illustrates the same.



[XAML]



&lt;syncfusion:TabControlExt  SelectedItemChangedEvent="SelectedItemChanged" &gt;

    &lt;Grid syncfusion:TabControlExt.Header="Tab1" /&gt;

        &lt;Grid syncfusion:TabControlExt.Header="Tab2" /&gt;

            &lt;Grid syncfusion:TabControlExt.Header="Tab3" /&gt;

&lt;/syncfusion:TabControlExt&gt;



[C#]



private void SelectedItemChangedEvent(object sender,SelectedItemChangedEventArgs e)

{

    if(e.NewSelectedItem.Header.ToString()=="Tab2")

    {

        e.Cancel=true;

    }      

}



