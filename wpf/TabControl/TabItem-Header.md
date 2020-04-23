---
layout: post
title: Tab Item Header | TabControlExt | wpf | Syncfusion
description: Learn here about how to add the tab item header into Syncfusion WPF TabControlExt and add image to the header.
platform: wpf
control: TabControlExt
documentation: ug
---

# TabItem Header in WPF TabControl (TabControlExt)

This section explains how to set header text and UI customization of the tab header in the [TabControl](https://help.syncfusion.com/cr/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.TabControlExt.html).

![Tab items with header text](Tab-Item-Header_images/Header_base.png)

## Adding tab item header

You can add a text for the each tab headers by using the `TabItemExt.Header` property.

{% tabs %}
{% highlight XAML %}

<syncfusion:TabControlExt Name="tabControlExt">
    <syncfusion:TabItemExt Header="tabItem1" Name="tabItemExt1"/>
    <syncfusion:TabItemExt Header="tabItem2" Name="tabItemExt2"/>
    <syncfusion:TabItemExt Header="tabItem3" Name="tabItemExt3"/>
</syncfusion:TabControlExt>

{% endhighlight %}
{% highlight C# %}

// Creating an instances of tabitems and adding header
TabItemExt tabItemExt1 = new TabItemExt() { Header = "tabItem1" };
TabItemExt tabItemExt2 = new TabItemExt() { Header = "tabItem2" };
TabItemExt tabItemExt3 = new TabItemExt() { Header = "tabItem3" };

// Creating an instances of TabControl and adding the tabitems into the TabControl
TabControlExt tabControlExt = new TabControlExt();
tabControlExt.Items.Add(tabItemExt1);
tabControlExt.Items.Add(tabItemExt2);
tabControlExt.Items.Add(tabItemExt3);

{% endhighlight %}
{% endtabs %}

![Tab items with header text](Tab-Item-Header_images/Header.png)

## Edit tab item header at runtime

You can edit the text of the tab header at runtime by double clicking the tab header or selected a tab and pressing `F2` key. You can restrict this editing by using the [EnableLabelEdit](https://help.syncfusion.com/cr/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.TabControlExt~EnableLabelEdit.html) property value as `false`. The default value of `EnableLabelEdit` property is `true`.

{% tabs %}
{% highlight xaml %}

<syncfusion:TabControlExt EnableLabelEdit="True" Name="tabControlExt">       
    <syncfusion:TabItemExt Header="tabItem1"/>
    <syncfusion:TabItemExt Header="tabItem2"/>
</syncfusion:TabControlExt>

{% endhighlight %}
{% highlight c# %}

tabControlExt.EnableLabelEdit = true;

{% endhighlight %}
{% endtabs %}

![Tab items header text changed at runtime](Tab-Item-Header_images/Header_runtime.png)

## Setting size and alignment of tab header

You can set a size of the each tabs by using the `TabItemExt.Width` and `TabItemExt.Height` properties. You can also align the header content horizontally and vertically by using the `TabItemExt.HorizontalContentAlignment` and `TabItemExt.VerticalContentAlignment` properties. The default value of `TabItemExt.HorizontalContentAlignment` and `TabItemExt.VerticalContentAlignment` properties is `Stretch`.

{% tabs %}
{% highlight XAML %}

<syncfusion:TabControlExt Name="tabControlExt">
    <syncfusion:TabItemExt Width="200" Height="30"     
                           HorizontalContentAlignment="Left"
                           VerticalContentAlignment="Center" 
                           Header="tabItem1"
                           Name="tabItemExt1"/>
    <syncfusion:TabItemExt Width="100" Height="30"
                           VerticalContentAlignment="Bottom"
                           HorizontalContentAlignment="Right"
                           Header="tabItem2" 
                           Name="tabItemExt2"/>
</syncfusion:TabControlExt>

{% endhighlight %}
{% highlight C# %}

//Adding size and alignment of tabItemExt1 header
tabItemExt1.Width = 200;
tabItemExt1.Height = 300;
tabItemExt1.HorizontalContentAlignment = HorizontalAlignment.Left;
tabItemExt1.VerticalContentAlignment = VerticalAlignment.Center;

//Adding size and alignment of tabItemExt2 header
tabItemExt1.Width = 100;
tabItemExt1.Height = 30;
tabItemExt1.HorizontalContentAlignment = HorizontalAlignment.Right;
tabItemExt1.VerticalContentAlignment = VerticalAlignment.Bottom;

{% endhighlight %}
{% endtabs %}

![Tab item header size and alignment changed](Tab-Item-Header_images/Size.png)

## Setting image for tab item header

You can add images to the tab item headers by using the [TabItemExt.Image](https://help.syncfusion.com/cr/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.TabItemExt~Image.html) property. You can change the height and width of the header image by using the [TabItemExt.ImageHeight](https://help.syncfusion.com/cr/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.TabItemExt~ImageHeight.html) and [TabItemExt.ImageWidth](https://help.syncfusion.com/cr/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.TabItemExt~ImageWidth.html) properties.

{% tabs %}
{% highlight xaml %}

<!-- Adding TabcontrolExt  -->
<syncfusion:TabControlExt Name="tabControlExt">

    <!-- Adding TabItemExt with image  -->
    <syncfusion:TabItemExt Image="sync_icon.ico" 
                           ImageWidth="20"
                           ImageHeight="20"
                           Header="TabItemExt1"
                           Name="tabItemExt1">
    </syncfusion:TabItemExt>
</syncfusion:TabControlExt>

{% endhighlight %}
{% highlight c# %}

//Adding header image for tabItemExt1
tabItemExt1.Image = new BitmapImage(
    new Uri(@"\sync_icon.ico", UriKind.RelativeOrAbsolute));

//Setting height and width for the tab header image
tabItemExt1.ImageWidth = 20;
tabItemExt1.ImageHeight = 20;  

{% endhighlight %}
{% endtabs %}

![Tab item header with image](Tab-Item-Header_images/Tab-Item-Header_img1.png)

### Tab header image alignment

You can align the tab item header image by using the [TabItemExt.ImageAlignment](https://help.syncfusion.com/cr/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.TabItemExt~ImageAlignment.html) property. You can set a margin for the image by using the [TabItemExt.IconMargin](https://help.syncfusion.com/cr/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.TabItemExt~IconMargin.html) property. The default value of `TabItemExt.ImageAlignment` property is `LeftOfText` and `TabItemExt.IconMargin` property is `0,0,0,4`.  You can align the image to any one of the following positions.

* AboveText - Images are placed above the tab item header text.
* BelowText – Images are placed below the tab item header text.
* LeftOfText – Images are placed to the left of the tab item header text.
* RightOfText – Images are placed to the right of the tab item header text.

{% tabs %}
{% highlight xaml %}

<!-- Adding TabcontrolExt  -->
<syncfusion:TabControlExt Name="tabControlExt">

    <!-- Adding TabItemExt with image with alignment  -->
    <syncfusion:TabItemExt Image="sync.png"  
                           ImageAlignment="AboveText"
                           IconMargin= "2"
                           Header="TabItemExt1"
                           Name="tabItemExt1">
    </syncfusion:TabItemExt>
</syncfusion:TabControlExt>

{% endhighlight %}
{% highlight c# %}

//Setting alignment for the tab header image 
tabItemExt1.ImageAlignment = ImageAlignment.AboveText;
tabItemExt1.IconMargin = new Thickness(2);
{% endhighlight %}
{% endtabs %}

![Tab item header image placed above to the text](Tab-Item-Header_images/Tab-Item-Header_img2.png)

## Setting tooltip

ToolTip is used to show the information about the segment, when you mouse over on the segment. You can add a tooltip information for the each tab items by using the [TabItemExt.ItemToolTip](https://help.syncfusion.com/cr/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.TabItemExt~ItemToolTip.html) property and show it by hovering the mouse on the respective header of the tab item.

{% tabs %}
{% highlight XAML %}

<syncfusion:TabControlExt Name="tabControlExt">
    <syncfusion:TabItemExt ItemToolTip="First item" 
                           Header="tabItem1" Name="tabItemExt1"/>
    <syncfusion:TabItemExt ItemToolTip="Second item"  
                           Header="tabItem2" Name="tabItemExt2"/>
</syncfusion:TabControlExt>

{% endhighlight %}
{% highlight C# %}

tabItemExt1.ItemToolTip = "First item";
tabItemExt2.ItemToolTip = "Second item";

{% endhighlight %}
{% endtabs %}

![Tab item header shows the tooltip information](Tab-Item-Header_images/Tooltip.png)

##  Hide tab header when there is single tab item

You can hide the header of tab item only on when single tab item present in the `TabControl`. You can enable it by using the [HideHeaderOnSingleChild](https://help.syncfusion.com/cr/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.TabControlExt~HideHeaderOnSingleChild.html) property value as `true`. The Default value of `HideHeaderOnSingleChild` property is `false`.

{% tabs %}
{% highlight XAML %}

<syncfusion:TabControlExt HideHeaderOnSingleChild="True" 
                          Name="tabControlExt">
    <syncfusion:TabItemExt Content="This is the first tab item"
                           Header="tabItem1"/>
</syncfusion:TabControlExt>

{% endhighlight %}
{% highlight C# %}

tabControlExt.HideHeaderOnSingleChild = true;

{% endhighlight %}
{% endtabs %}

![TabControl contains single item without tab header](Tab-Item-Header_images/NoTabheader.png)





# Selecting a tab item

This section explains how to select tab item and selection functionalities in the [TabControl](https://help.syncfusion.com/cr/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.TabControlExt.html).

##  Select tab item using mouse and key interaction

You can select a particular tab item by using the mouse click on the tab header. You also use the `Left-Arrow` and `Right-Arrow` key , to select the previous tab item or next tab item of current selected tab item. You can get the seleted item by using the `SelectedItem` property. By default, the first tab item is selected.

N> You can select only one tab item at a time.

![Tab items selected by clicking the tab header](Tab-Item-Header_images/SelectItem.gif)

## Tab selection changed notification

The `TabControl` notifies that the selected tabitem is changed by user through the [SelectedItemChangedEvent](https://help.syncfusion.com/cr/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.TabControlExt~SelectedItemChangedEvent_EV.html) event. You can use the [OldSelectedItem](https://help.syncfusion.com/cr/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.SelectedItemChangedEventArgs~OldSelectedItem.html) and [NewSelectedItem](https://help.syncfusion.com/cr/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.SelectedItemChangedEventArgs~NewSelectedItem.html) properties to get the old and new selected tabitem in the `SelectedItemChangedEvent` event.

{% tabs %}
{% highlight XAML %}

<syncfusion:TabControlExt SelectedItemChangedEvent="TabControlExt_SelectedItemChangedEvent"
                          Name="tabControlExt" />

{% endhighlight %}
{% highlight C# %}

TabControlExt tabControlExt = new TabControlExt();
tabControlExt.SelectedItemChangedEvent += TabControlExt_SelectedItemChangedEvent;

{% endhighlight %}
{% endtabs %}

You can handle the event as follows:

{% tabs %}
{% highlight C# %}

private void TabControlExt_SelectedItemChangedEvent(object sender, SelectedItemChangedEventArgs e) {
    var newTabItem = e.NewSelectedItem.Header;
    if (e.OldSelectedItem != null) {
        var oldTabItem = e.OldSelectedItem.Header;
    }
    else {
        var oldTabItem = string.Empty;
    }
}

{% endhighlight %}
{% endtabs %}

## Load the previously selected tab item content

By default, the `TabControl` unloads the previously selected tab item content when selected item is changed. You can restrict it by setting the [IsDisableUnloadTabItemExtContent](https://help.syncfusion.com/cr/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.TabControlExt~IsDisableUnloadTabItemExtContent.html) property value as `true`. The default value of `IsDisableUnloadTabItemExtContent` property is `false`.

{% tabs %}
{% highlight XAML %}

<syncfusion:TabControlExt IsCustomTabItemContextMenuEnabled="IsCustomTabItemContextMenuEnabled"
                          Name="tabControlExt">
    <syncfusion:TabItemExt Header="tab1" Name="tabItemExt1"/>
    <syncfusion:TabItemExt Header="tab2" Name="tabItemExt2"/>
</syncfusion:TabControlExt>

{% endhighlight %}
{% highlight C# %}

tabControlExt.IsCustomTabItemContextMenuEnabled = true;

{% endhighlight %}
{% endtabs %}

![TabControl loads the previously selected tab item content](Tab-Item-Header_images/Loadall.png)

## Change selected tab header font weight

You can change the seleted tab header font weight by using the [SelectedItemFontWeight](https://help.syncfusion.com/cr/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.TabControlExt~SelectedItemFontWeight.html) property. The default value of `SelectedItemFontWeight` property is `SemiBold`.

{% tabs %}
{% highlight XAML %}

<syncfusion:TabControlExt SelectedItemFontWeight="UltraLight"
                          Name="tabControlExt">
    <syncfusion:TabItemExt Header="tabItem1" Name="tabItemExt1"/>
    <syncfusion:TabItemExt Header="tabItem2" Name="tabItemExt2"/>
</syncfusion:TabControlExt>

{% endhighlight %}
{% highlight C# %}

tabControlExt.SelectedItemFontWeight = FontWeights.UltraLight;

{% endhighlight %}
{% endtabs %}

![TabControl SelectedItem font weight changed to UltraLight](Tab-Item-Header_images/SelectedItemFontWeight.png)