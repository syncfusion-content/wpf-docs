---
layout: post
title: Pin and Unpin the TabItems in the Syncfusion TabControlExt
description: Explains about pinning and unpinning behavior of TabItems in the TabControlExt of WPF
platform: wpf
control: TabControlExt
documentation: ug
---
# Pin and Unpin tab items

The following section explains the Pin and Unpin tab items support in TabControlExt.

## Enabling/disabling pinning behavior

[AllowPin](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.TabItemExt~AllowPin.html) property of TabItemExt decides whether the TabItemExt is pinnable or not. The corresponding tab item will be pinned only if the property [AllowPin](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.TabItemExt~AllowPin.html) is true. When the property is false, Pin and Unpin behavior of TabItem will be disabled. The default value of the [AllowPin](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.TabItemExt~AllowPin.html) property is false.

{% tabs %}

{% highlight XAML %}

  <syncfusion:TabControlExt>

            <syncfusion:TabItemExt Header="Beijing" AllowPin="True" />
            
            <syncfusion:TabItemExt Header="Madagascar" AllowPin="True"/>                      
            
</syncfusion:TabControlExt>

{% endhighlight %}

{% endtabs %}

## Pin and Unpin tab items using PinButton

### Display PinButton in header panel of tab item

PinButton will be visible in the header panel of tab item only if the property [ShowPin](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.TabItemExt~ShowPin.html) is true. The default value of the property is false, so the PinButton will be collapsed from header panel of tab item.

{% tabs %}

{% highlight XAML %}

  <syncfusion:TabControlExt>

            <syncfusion:TabItemExt Header="Beijing" AllowPin="True" ShowPin="True" />
            
            <syncfusion:TabItemExt Header="Madagascar" ShowPin="False"/>    

            <syncfusion:TabItemExt Header="New York" AllowPin="False" ShowPin="True" />
            
            <syncfusion:TabItemExt Header="London" ShowPin="False"/>                   
            
</syncfusion:TabControlExt>

{% endhighlight %}

{% endtabs %}

![Displaying PinButton to specific items](Pin-Unpin-tabs-images\Pin-Unpin-tabs-images1.png)

If the property [AllowPin](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.TabItemExt~AllowPin.html) is true, PinButton will be enabled and visible. If the property [ShowPin](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.TabItemExt~ShowPin.html) is true and [AllowPin](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.TabItemExt~AllowPin.html) is false, PinButton will be displayed as disabled button. 


### Functionality of PinButton

When the pin button of the TabItemExt is visible, the corresponding TabItem can be pinned or unpinned from the Tabcontrol. When the corresponding TabItem is pinned, it will be inserted at first position of the TabItems collection(if the pinned tab item collection has zero count. Otherwise, the pinned tab item will be added to the existing collection). When the TabItem is unpinned, it will be removed from the pinned tab item collection and added to the first position of the unpinned tab item collection.

## Pin and Unpin the tab items programmatically

TabItems can be pinned or unpinned from the TabControlExt using [IsPinned](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.TabItemExt~IsPinned.html) property of TabItemExt. If the property [IsPinned](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.TabItemExt~IsPinned.html) is set to true, the corresponding item will be added to respective index. Also,if the property [IsPinned](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.TabItemExt~IsPinned.html) is set as false, the tab item will be removed from pinned collection and added to unpinned tab item collection. The default value of the property is False.

## Pin and Unpin tab items through ContextMenu

Pin or Unpin operations can be done through TabItemExt's ContextMenu also. If the property [AllowPin](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.TabItemExt~AllowPin.html) is true and the TabItem is not pinned "Pin Tab" option will be visible. If the TabItem is pinned already, "Unpin Tab" will be visible. 

{% tabs %}
{% highlight XAML %}
<syncfusion:TabControlExt>

            <syncfusion:TabItemExt Header="Beijing" AllowPin="True" />
            
            <syncfusion:TabItemExt Header="Madagascar" AllowPin="True"/>    

            <syncfusion:TabItemExt Header="New York" AllowPin="True />
            
            <syncfusion:TabItemExt Header="London" AllowPin="True"/>                   
            
</syncfusion:TabControlExt>
{% endhighlight %}
{% endtabs %}

The following images illustrates the same,

![Displays option to pin the TabItemExt](Pin-Unpin-tabs-images\Pin-Unpin-tabs-images2.png)

![Displays option to Unpin the TabItemExt](Pin-Unpin-tabs-images\Pin-Unpin-tabs-images3.png)

## Re-ordering behavior of tab items when pin and unpin functionality is enabled

User can re-order the pinned item within the pinned items collection and re-order the un-pinned item within the unpinned item collection but re-ordering between pinned to unpinned or unpinned to pinned is restricted. If the pinned tab item is dropped in the unpinned tab item collection, the dragged item is inserted at last index of pinned tab item collection and if the un pinned tab item is dropped in pinned tab item collection, the dragged item is inserted at zeroth index of un-pinned tab item collection.

