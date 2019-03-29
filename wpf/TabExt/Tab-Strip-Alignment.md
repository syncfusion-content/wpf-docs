---
layout: post
title: Tab Strip Alignment | TabControlExt | wpf | Syncfusion
description: tab strip alignment
platform: wpf
control: TabControlExt
documentation: ug
---

# Tab Strip Alignment

TabStrip of the TabControlExt can be aligned to all four sides of the TabControlExt by using the [TabStripPlacement](https://help.syncfusion.com/cr/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.TabControlSettings~TabStripPlacement.html) property. This dependency property is used to dock the Tab Header, relative to the content of the TabControlExt. It returns the docking state of the TabItem.

The following TabStrip placement options are supported by the TabControlExt.

* Top-positions the TabStrip at the top of the TabControlExt control
* Bottom-positions the TabStrip at the bottom of the TabControlExt control
* Left-positions the TabStrip to the left of the TabControlExt control
* Right-positions the TabStrip to the right of the TabControlExt control



To place the TabStrip to the "Left" of the TabControlExt, use the below code.

{% tabs %}

{% highlight xaml %}

<!-- Adding TabControlExt with TabStripPlacement is left -->

<syncfusion:TabControlExt Margin="20" Name="tabControlExt" TabStripPlacement="Left">

    <!-- Adding TabItemExt -->

    <syncfusion:TabItemExt Name="tabItemExt1" Header="TabItemExt1"/>



    <!-- Adding TabItemExt -->

    <syncfusion:TabItemExt Name="tabItemExt2" Header="TabItemExt2"/>

</syncfusion:TabControlExt>

{% endhighlight %}

{% highlight c# %}



// Creating instance of the TabControlExt control

TabControlExt tabControlExt = new TabControlExt();



//Creating the instance of StackPanel

StackPanel stackPanel = new StackPanel();



//Creating instance of the TabItemExt 

TabItemExt tabItemExt1 = new TabItemExt();



// Setting header of the TabItemExt

tabItemExt1.Header = "TabItemExt1";



//Adding TabItemExt to TabControlExt

tabControlExt.Items.Add(tabItemExt1);



//Creating instance of the TabItemExt2 

TabItemExt tabItemExt2 = new TabItemExt();



// Setting header of the TabItemExt

tabItemExt2.Header = "TabItemExt2";



//Adding TabItemExt to TabControlExt

tabControlExt.Items.Add(tabItemExt2);



//Setting TabStripPlacement property as Left

tabControlExt.TabStripPlacement = Dock.Left;



//Adding control to the StackPanel

stackPanel.Children.Add(tabControlExt); 

{% endhighlight %}

{% endtabs %}



![Tab srip placement](Tab-Strip-Alignment_images/Tab-Strip-Alignment_img1.jpeg)


## Rotating the Tab Strip

To improve the user readability, the Tab Strip text can be rotated, whenever the [TabStripPlacement](https://help.syncfusion.com/cr/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.TabControlSettings~TabStripPlacement.html) is set to _left_ or _right_. The [RotateTextWhenVertical](https://help.syncfusion.com/cr/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.TabControlExt~RotateTextWhenVertical.html) property need to be set to _true_,__to enable this feature. When this property is set to _true_, and when the [TabStripPlacement](https://help.syncfusion.com/cr/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.TabControlSettings~TabStripPlacement.html) is changed to left or right (in other words, when the tab strip is in the vertical position), the text will be rotated and placed horizontally as in the below image.

Here is the code snippet for rotating the text when tab strip is vertically placed.

{% tabs %}

{% highlight xaml %}

<!-- Adding TabControlExt with TabStripPlacement is left and RotateTextWhenVertical is true  -->

<syncfusion:TabControlExt Margin="20" Name="tabControlExt" TabStripPlacement="Left" RotateTextWhenVertical="true">

  <!-- Adding TabItemExt -->

  <syncfusion:TabItemExt Name="tabItemExt1" Header="TabItemExt1"/>

  <!-- Adding TabItemExt -->

  <syncfusion:TabItemExt Name="tabItemExt2" Header="TabItemExt2"/>

</syncfusion:TabControlExt>

{% endhighlight %}

{% highlight c# %}

// Creating instance of the TabControlExt control

TabControlExt tabControlExt = new TabControlExt();

//Creating the instance of StackPanel

StackPanel stackPanel = new StackPanel();

//Creating instance of the TabItemExt

TabItemExt tabItemExt1 = new TabItemExt();

// Setting header of the TabItemExt

tabItemExt1.Header = "TabItemExt1";

//Adding TabItemExt to TabControlExt

tabControlExt.Items.Add(tabItemExt1);

//Creating instance of the TabItemExt2

TabItemExt tabItemExt2 = new TabItemExt();

// Setting header of the TabItemExt

tabItemExt2.Header = "TabItemExt2";

//Adding TabItemExt to TabControlExt

tabControlExt.Items.Add(tabItemExt2);

//Setting TabStripPlacement property as Left

tabControlExt.TabStripPlacement = Dock.Left;

//Setting RotateTextWhenVertical property as true

tabControlExt.RotateTextWhenVertical = true;

//Adding control to the StackPanel

stackPanel.Children.Add(tabControlExt); 

{% endhighlight %}

{% endtabs %}


![Tab strip placement](Tab-Strip-Alignment_images/Tab-Strip-Alignment_img2.jpeg)