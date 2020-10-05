---
layout: post
title: Popup customization in SfMultiColumnDropDownControl.
description: How to handle the popup customizations, popupsizing in SfMultiColumnDropDownControl.
platform: wpf
control: SfMultiColumnDropDownControl
documentation: ug
---

# Popup customization
SfMultiColumnDropDownControl allows you to customize the Popup appearance by setting [PopupBackground](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfMultiColumnDropDownControl.html#Syncfusion_UI_Xaml_Grid_SfMultiColumnDropDownControl_PopupBackground), [PopupBorderBrush](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfMultiColumnDropDownControl.html#Syncfusion_UI_Xaml_Grid_SfMultiColumnDropDownControl_PopupBorderBrush), [PopupDropDownGridBackground](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfMultiColumnDropDownControl.html#Syncfusion_UI_Xaml_Grid_SfMultiColumnDropDownControl_PopupDropDownGridBackground) and [PopupBorderThickness](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfMultiColumnDropDownControl.html#Syncfusion_UI_Xaml_Grid_SfMultiColumnDropDownControl_PopupBorderThickness) properties.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfMultiColumnDropDownControl x:Name="sfMultiColumn"
                                         Width="175"
                                         Height="30"                                                     
                                         DisplayMember="CustomerName"
                                         ItemsSource="{Binding Orders}"
                                         PopupBackground="Beige"
                                         PopupBorderBrush="Aqua"
                                         PopupBorderThickness="3"
                                         ValueMember="CustomerName">
                <syncfusion:SfMultiColumnDropDownControl.Columns>
                    <syncfusion:GridTextColumn MappingName="CustomerName" />
                    <syncfusion:GridTextColumn MappingName="OrderID" />
                    <syncfusion:GridTextColumn MappingName="CustomerID" />
                    <syncfusion:GridTextColumn MappingName="Country" />
                </syncfusion:SfMultiColumnDropDownControl.Columns>
</syncfusion:SfMultiColumnDropDownControl>
{% endhighlight %}
{% endtabs %}

![](Popup-customization_images/Popup-customization_img1.png)

You can change the drop down grid background by setting [PopupDropDownGridBackground](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfMultiColumnDropDownControl.html#Syncfusion_UI_Xaml_Grid_SfMultiColumnDropDownControl_PopupDropDownGridBackground).

{% tabs %}
{% highlight xaml %}
<syncfusion:SfMultiColumnDropDownControl x:Name="sfMultiColumn"
                                         Width="175"
                                         Height="30"
                                         DisplayMember="CustomerName"
                                         ItemsSource="{Binding Orders}"
                                         PopupDropDownGridBackground="LightGreen"
                                         ValueMember="CustomerName">
                <syncfusion:SfMultiColumnDropDownControl.Columns>
                    <syncfusion:GridTextColumn MappingName="CustomerName" />
                    <syncfusion:GridTextColumn MappingName="OrderID" />
                    <syncfusion:GridTextColumn MappingName="CustomerID" />
                    <syncfusion:GridTextColumn MappingName="Country" />
                </syncfusion:SfMultiColumnDropDownControl.Columns>
</syncfusion:SfMultiColumnDropDownControl>
{% endhighlight %}
{% endtabs %}

![](Popup-customization_images/Popup-customization_img2.png)

## Popup sizing

You can change the pop-up height and width by setting [PopupWidth](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfMultiColumnDropDownControl.html#Syncfusion_UI_Xaml_Grid_SfMultiColumnDropDownControl_PopupWidth) and [PopupHeight](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfMultiColumnDropDownControl.html#Syncfusion_UI_Xaml_Grid_SfMultiColumnDropDownControl_PopupHeight) properties. The `PopupWidth` will be set based on[PopupMinWidth](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfMultiColumnDropDownControl.html#Syncfusion_UI_Xaml_Grid_SfMultiColumnDropDownControl_PopupMinWidth) and [PopupMaxWidth](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfMultiColumnDropDownControl.html#Syncfusion_UI_Xaml_Grid_SfMultiColumnDropDownControl_PopupMaxWidth) properties when the value is not between them. By default, the `PopupMinWidth` value is 200.0. 

Similarly, the `PopupHeight` will be set based on[PopupMinHeight](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfMultiColumnDropDownControl.html#Syncfusion_UI_Xaml_Grid_SfMultiColumnDropDownControl_PopupMinHeight) and [PopupMaxHeight](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfMultiColumnDropDownControl.html#Syncfusion_UI_Xaml_Grid_SfMultiColumnDropDownControl_PopupMaxHeight) when the value is not between them. The default value of `PopupMinHeight` is 300.0. 

### Auto sizing

SfMultiColumnDropDownControl can automatically adjust the popup width and height based on the width and height of SfDataGrid when setting [IsAutoPopupSize](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfMultiColumnDropDownControl.html#Syncfusion_UI_Xaml_Grid_SfMultiColumnDropDownControl_IsAutoPopupSize) as `true`.
N> When `IsAutoPopupSize` is `true`, then the popup width and height is not calculated based on `PopupHeight` and `PopupWidth`.

## Resizing popup

You can allow the end-user to resize the drop-down popup through resizing thumb by setting [ResizingThumbVisibility](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfMultiColumnDropDownControl.html#Syncfusion_UI_Xaml_Grid_SfMultiColumnDropDownControl_ResizingThumbVisibility) property to `Visible`.

## Keep DropDownPopup as StaysOpen

You can keep the popup in SfMultiColumnDropDownControl as always open by using `StaysOpen` property. You can get the popup from template of SfMultiColumnDropDownControl in its loaded event and set the `StaysOpen` property as `true`.

{% tabs %}
{% highlight c# %}
sfMultiColumn.Loaded += (o, e) =>
{
   var popup = sfMultiColumn.Template.FindName("PART_Popup", sfMultiColumn) as Popup;
   popup.StaysOpen = true;
};
{% endhighlight %}
{% endtabs %}

## Events

SfMultiColumnDropDownControl provides the following events for popup customizations,
 
### PopupClosing event

[PopupClosing](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfMultiColumnDropDownControl.html) event is fired when the popup is closing. You can use this event to skip the popup closing and [PopupClosingEventArgs](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.PopupClosingEventArgs.html) provides data for `PopupClosing` event. You can skip the popup closing by setting `args.Cancel` as true.

{% tabs %}
{% highlight c# %}
sfMultiColumn.PopupClosing += sfMultiColumn_PopupClosing;

void sfMultiColumn_PopupClosing(object sender, PopupClosingEventArgs args)
{
}
{% endhighlight %}
{% endtabs %}

### PopupClosed event

[PopupClosed](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfMultiColumnDropDownControl.html) event is fired when the popup is closed. [PopupClosedEventArgs](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.PopupClosedEventArgs.html) provides data for `PopupClosed` event

{% tabs %}
{% highlight c# %}
sfMultiColumn.PopupClosed += sfMultiColumn_PopupClosed;

void sfMultiColumn_PopupClosed(object sender, PopupClosedEventArgs args)
{
}
{% endhighlight %}
{% endtabs %}

### PopupOpening event

[PopupOpening](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfMultiColumnDropDownControl.html) event is fired when the popup is opening. You can use this event to skip the popup opening and [PopupOpeningEventArgs](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.PopupOpeningEventArgs.html) provides data for `PopupOpening` event. You can skip the popup opening by setting `args.Cancel` as true.

{% tabs %}
{% highlight c# %}
sfMultiColumn.PopupOpening += sfMultiColumn_PopupOpening;

void sfMultiColumn_PopupOpening(object sender, PopupOpeningEventArgs args)
{
}
{% endhighlight %}
{% endtabs %}

### PopupOpened event

[PopupOpened](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfMultiColumnDropDownControl.html) event is fired when the popup is opened. [PopupOpenedEventArgs](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.PopupOpenedEventArgs.html) provides data for `PopupOpened` event

{% tabs %}
{% highlight c# %}
sfMultiColumn.PopupOpened += sfMultiColumn_PopupOpened;

void sfMultiColumn_PopupOpened(object sender, PopupOpenedEventArgs args)
{
}
{% endhighlight %}
{% endtabs %}
