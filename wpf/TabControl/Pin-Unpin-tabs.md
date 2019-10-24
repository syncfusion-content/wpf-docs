---
layout: post
title: Pin and Unpin the TabItems in TabControlExt | Syncfusion | WPF
description: Explains about pinning and unpinning behavior of TabItems in the TabControlExt for WPF
platform: wpf
control: TabControlExt
documentation: ug
---
# Pin and Unpin tab items

This section explains the pin and unpin tab items support in TabControlExt.

## Enabling/disabling pinning behavior

The [AllowPin](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.TabItemExt~AllowPin.html) property of TabItemExt decides whether the TabItemExt could be pinnable or not. The corresponding tab item will be pinned when the [AllowPin](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.TabItemExt~AllowPin.html) property is set to true. When this property is set to false, the pin and unpin behaviors of TabItem will be disabled. The default value of the [AllowPin](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.TabItemExt~AllowPin.html) property is false.

{% tabs %}

{% highlight XAML %}

  <syncfusion:TabControlExt>

            <syncfusion:TabItemExt Header="Beijing" AllowPin="True" />
            
            <syncfusion:TabItemExt Header="Madagascar" AllowPin="True"/>                      
            
</syncfusion:TabControlExt>

{% endhighlight %}

{% endtabs %}

## Pin and Unpin tab items using PinButton

The PinButton will be visible in the TabItemExt only when the [ShowPin](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.TabItemExt~ShowPin.html) property is set to true. The default value of this property is false, so the PinButton will be collapsed from header panel of tab item.

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

![Displaying PinButton to specific items](pin-unpin-tabs-images\displaying-pinbutton.png)

If the [AllowPin](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.TabItemExt~AllowPin.html) property is true, the PinButton will be enabled and will be visible. If the [ShowPin](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.TabItemExt~ShowPin.html) property is true, and the [AllowPin](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.TabItemExt~AllowPin.html) property is false, the PinButton will be displayed as a disabled button.

### Functionality of PinButton

When the pin button of the TabItemExt is visible, the corresponding TabItem can be pinned or unpinned from the Tabcontrol. When the corresponding TabItem is pinned, it will be inserted at first position of the TabItems collection(if the pinned tab item collection has zero count. Otherwise, the pinned tab item will be added to the existing collection). When the TabItem is unpinned, it will be removed from the pinned tab item collection and added to the first position of the unpinned tab item collection.

## Pin and Unpin the tab items programmatically

TabItems can be pinned or unpinned from the TabControlExt using [IsPinned](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.TabItemExt~IsPinned.html) property of TabItemExt. If the property [IsPinned](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.TabItemExt~IsPinned.html) is set to true, the corresponding item will be added to respective index. Also,if the property [IsPinned](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.TabItemExt~IsPinned.html) is set as false, the tab item will be removed from pinned collection and added to unpinned tab item collection. The default value of the property is False.

## Pin and Unpin tab items through ContextMenu

The pin or unpin operations can be done through TabItemExt's ContextMenu also. If the property [AllowPin](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.TabItemExt~AllowPin.html) is true, and the TabItem is not pinned, "Pin Tab" option will be visible. If the TabItem is pinned already, "Unpin Tab" will be visible. 

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

![Displays option to pin the TabItemExt](pin-unpin-tabs-images\pintab-option-contextmenu.png)

![Displays option to Unpin the TabItemExt](pin-unpin-tabs-images\unpintab-option-contextmenu.png)

## Re-order pinned tabs

Users can re-order the pinned item within the pinned items collection and re-order the un-pinned item within the unpinned item collection, but re-ordering between pinned and unpinned or unpinned and pinned has been restricted. If the pinned tab item is dropped in the unpinned tab item collection, the dragged item will be inserted at the last index of pinned tab item collection and if the un pinned tab item is dropped in pinned tab item collection, the dragged item will be inserted at zeroth index of un-pinned tab item collection.
