---
layout: post
title: Pin and Unpin the TabItems in the Syncfusion TabControlExt
description: Explains about pinning and unpinning behavior of TabItems in the TabControlExt of WPF
platform: wpf
control: TabControlExt
documentation: ug
---
# Pin and Unpin TabItems support in TabControlExt

The following section explains the Pin and Unpin TabItems support in TabControlExt.

## Enabling Pin and Unpin support

`AllowPin` property of TabItemExt decides whether the TabItemExt is pinnable or not. The corresponding tab item will be pinned only if the property `AllowPin` is true. When the property is false, Pin and Unpin behavior of TabItem will be disabled. The default value of the `AllowPin` property is false.

{% tabs %}

{% highlight XAML %}

  <syncfusion:TabControlExt>

            <syncfusion:TabItemExt Header="Beijing" AllowPin="True" />
            
            <syncfusion:TabItemExt Header="Madagascar" AllowPin="True"/>                      
            
</syncfusion:TabControlExt>

{% endhighlight %}

{% endtabs %}

## Pin and Unpin tab items using PinButton

### Display PinButton in TabItemExt

PinButton will be visible in the TabItemExt only if the property `ShowPin` is true. The default value of the property is false, so the PinButton will be collapsed in the TabItemExt.

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

![Displaying PinButton to specific items](Pin-and-Unpin-TabItems-support-in-TabControlExt-images\Pin-and-Unpin-TabItems-support-in-TabControlExt-images1.png)

If the property `AllowPin` is true, PinButton will be enabled and visible. If the property `ShowPin` is true and `AllowPin` is false, PinButton will be displayed as disabled button. 


### Functionality of PinButton

When the pin button of the TabItemExt is visible, the corresponding TabItem can be pinned or unpinned from the Tabcontrol. When the corresponding TabItem is pinned, it will be inserted at first position of the TabItems collection(if the pinned tab item collection has zero count. Otherwise, the pinned tab item will be added to the existing collection). When the TabItem is unpinned, it will be removed from the pinned tab item collection and added to the first position of the unpinned tab item collection.

## Pin and Unpin the tab items programmatically

TabItems can be pinned or unpinned from the TabControlExt using `IsPinned` property of TabItemExt. If the property `IsPinned` is set to true, the corresponding item will be added to respective index. Also,if the property `IsPinned` is set as false, the tab item will be removed from pinned collection and added to unpinned tab item collection. The default value of the property is False.

## Pin and Unpin tab items through ContextMenu

Pin or Unpin operations can be done through TabItemExt's ContextMenu also. If the property `AllowPin` is true and the TabItem is not pinned "Pin Tab" option will be visible. If the TabItem is pinned already, "Unpin Tab" will be visible. 

<syncfusion:TabControlExt>

            <syncfusion:TabItemExt Header="Beijing" AllowPin="True" />
            
            <syncfusion:TabItemExt Header="Madagascar" AllowPin="True"/>    

            <syncfusion:TabItemExt Header="New York" AllowPin="True />
            
            <syncfusion:TabItemExt Header="London" AllowPin="True"/>                   
            
</syncfusion:TabControlExt>

The following images illustrates the same,

![Displaying option to pin the TabItemExt](Pin-and-Unpin-TabItems-support-in-TabControlExt-images\Pin-and-Unpin-TabItems-support-in-TabControlExt-images2.png)

![Displaying option to Unpin the TabItemExt](Pin-and-Unpin-TabItems-support-in-TabControlExt-images\Pin-and-Unpin-TabItems-support-in-TabControlExt-images3.png)

## Re-ordering behavior of TabItems when Pin and Unpin functionality is enabled

User can re-order the pinned item within the pinned items collection and re-order the un-pinned item within the unpinned item collection but re-ordering between pinned to unpinned or unpinned to pinned is restricted. If the pinned tab item is dropped in the unpinned tab item collection, the dragged item is inserted at last index of pinned tab item collection and if the un pinned tab item is dropped in pinned tab item collection, the dragged item is inserted at zeroth index of un-pinned tab item collection.

