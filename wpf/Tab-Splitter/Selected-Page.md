---
layout: post
title: Selected Page | TabSplitter | wpf | Syncfusion
description: selected page
platform: wpf
control: TabSplitter
documentation: ug
---

# Selected Page

You can set the selected page by using the [IsSelectedPage](https://help.syncfusion.com/cr/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.SplitterPage~IsSelectedPage.html) property. If this property is set to _true_, the page is selected, else it is not selected.

{%tabs%}
{% highlight xaml %}

 <!-- Adding TabSplitter -->

<syncfusion:TabSplitter Name="tabsplitter">



    <!-- Adding TabSplitterItem -->

<syncfusion:TabSplitterItem Header="Window1.xml"  Name="tabSplitterItem1">



        <!-- Adding TopPanelItems -->

        <syncfusion:TabSplitterItem.TopPanelItems> 

            <!-- Adding SplitterPage -->

<syncfusion:SplitterPage IsSelectedPage="True" Name="splitterPage1" Header="XAML">

            </syncfusion:SplitterPage>

        </syncfusion:TabSplitterItem.TopPanelItems>



        <!-- Adding BottomPanelItems -->

        <syncfusion:TabSplitterItem.BottomPanelItems> 

            <!-- Adding SplitterPage -->

            <syncfusion:SplitterPage Name="splitterPage2" Header="Design">

            </syncfusion:SplitterPage>

        </syncfusion:TabSplitterItem.BottomPanelItems>



    </syncfusion:TabSplitterItem>



</syncfusion:TabSplitter>
{% endhighlight %}

{% highlight c# %}



// Enable the IsSelectedPage property.

splitterPage1.IsSelectedPage = true;
{% endhighlight %}

{%endtabs%}
![Selected page](Selected-Page_images/Selected-Page_img1.png)





