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



<syncfusion:TabControlExt  SelectedItemChangedEvent="SelectedItemChanged" >

    <Grid syncfusion:TabControlExt.Header="Tab1" />

        <Grid syncfusion:TabControlExt.Header="Tab2" />

            <Grid syncfusion:TabControlExt.Header="Tab3" />

</syncfusion:TabControlExt>



[C#]



private void SelectedItemChangedEvent(object sender,SelectedItemChangedEventArgs e)

{

    if(e.NewSelectedItem.Header.ToString()=="Tab2")

    {

        e.Cancel=true;

    }      

}



