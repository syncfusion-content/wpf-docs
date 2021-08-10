---
layout: post
title: Popup Options| SfMultiColumnDropDownControl | Wpf | Syncfusion
description: Popup options in Syncfusion WPF MultiColumnDropDown (SfMultiColumnDropDown) control, its elements and more.
platform: wpf
control: SfMultiColumnDropDownControl
documentation: ug
---

# Popup Options in WPF MultiColumnDropDown control

SfMultiColumnDropDownControl allows you to customize the DropDownPopup appearance by setting Popup Background, BorderBrush and BorderThickness etc.

The following code example illustrates how to customize the DropDownPopup.
{% highlight xaml %}





<Window.DataContext>

  <local:Viewmodel/>

</Window.DataContext>





<syncfusion:SfMultiColumnDropDownControl x:Name="sfmulticolumn"

                                           AllowIncrementalFiltering="True"

                                           DisplayMember="Name" 

                                           ValueMember="Title"  

                                           PopupBorderBrush="Aqua"

                                           PopupBorderThickness="3"

                                           PopupBackground="Beige"

                                                  PopupDropDownGridBackground="AliceBlue"                                                              

                                           ItemsSource="{Binding GridItemSource}">



</syncfusion:SfMultiColumnDropDownControl>
{% endhighlight %}
The following screenshot displays the output for above code example.

![Features_images11](Features_images/Features_img11.png)



SfMultiColumnDropDownControl allows you to resize the DropDownPopup. You can resize the DropDownPopup by using Resize Thumb that shows Right bottom of the DropDownPopup. 

SfMultiColumnDropDownControl exposes the following properties to Resize and Customize the DropDownPopup

Property Table

<table>
<tr>
<th>
Property</th><th>
Type</th><th>
Description</th><th>
Default Value</th></tr>
<tr>
<td>
ActualPopupHeight</td><td>
Double</td><td>
Gets the actual height of the Popup.</td><td>
Double.NaN</td></tr>
<tr>
<td>
ActualPopupWidth</td><td>
Double</td><td>
Gets the actual width of the Popup.</td><td>
Double.NaN</td></tr>
<tr>
<td>
IsAutoPopupSize</td><td>
Bool</td><td>
Specifies whether the size of the Popup should be based on the actual size of the Grid.</td><td>
False</td></tr>
<tr>
<td>
PopupHeight</td><td>
Double</td><td>
Gets or sets the height of the Popup.</td><td>
Double.NaN</td></tr>
<tr>
<td>
PopupMaxHeight</td><td>
Double</td><td>
Gets or sets the maximum height of the Popup.</td><td>
Double.PositiveInfinity</td></tr>
<tr>
<td>
PopupMaxWidth</td><td>
Double</td><td>
Gets or sets the maximum width of the Popup.</td><td>
Double.PositiveInfinity</td></tr>
<tr>
<td>
PopupMinHeight</td><td>
Double</td><td>
Gets or sets the minimum height of the Popup.</td><td>
DefaultPopupHeight</td></tr>
<tr>
<td>
PopupMinWidth</td><td>
Double</td><td>
Gets or sets the minimum width of the Popup.</td><td>
DefaultPopUpWidth</td></tr>
<tr>
<td>
PopupWidth</td><td>
Double</td><td>
Gets or sets the width of the Popup.</td><td>
Double.NaN</td></tr>
<tr>
<td>
PopupBackground</td><td>
Brush</td><td>
Get or Set the Popup Background</td><td>
Gainsboro</td></tr>
<tr>
<td>
PopupBorderBrush</td><td>
Brush</td><td>
Get or Set the Popup BorderBrush</td><td>
Black</td></tr>
<tr>
<td>
PopupBorderThickness</td><td>
Thickness</td><td>
Get or Set the PopupBorderThickness</td><td>
1</td></tr>
<tr>
<td>
PopupDropDownGridBackground</td><td>
Brush</td><td>
Get or Set the PopupDropDownGrid</td><td>
White</td></tr>
<tr>
<td>
PopupContentTemplate</td><td>
ContentTemplate</td><td>
Get or Sets the PopupContent </td><td>
Null</td></tr>
</table>
Events

Events Table

<table>
<tr>
<th>
Event</th><th>
Description</th></tr>
<tr>
<td>
PopupClosed</td><td>
This event is raised when the Popup is closed.The PopupClosed event handler receives two arguments, namely Sender and PopupClosedEventArgs, as objects.</td></tr>
<tr>
<td>
PopupClosing</td><td>
This event is raised before the Popup is closed; the event can be canceled.The PopupClosing event handler receives two arguments, namely Sender and PopupClosingEventArgs, as objects.The PopupClosingEventArgs object uses the following property to cancel an event:Cancel: When set to true, the event is canceled and the Popup is not closed.</td></tr>
<tr>
<td>
PopupOpened</td><td>
This event is raised when the Popup is opened.The PopupOpened event handler receives two arguments, namely Sender and PopupOpenedEventArgs{{ '_,_' | markdownify }} as objects.</td></tr>
<tr>
<td>
PopupOpening</td><td>
This event is raised before the Popup is opened; the event can be canceled.The PopupOpening event handler receives two arguments, namely Sender and PopupOpeningEventArgs{{ '_,_'| markdownify }} as objects.The PopupOpeningEventArgs object uses the following property to cancel an event:Cancel: When set to true, the event is canceled and the Popup is not opened.</td></tr>
</table>

### How To

#### How to keep DropDownPopup StaysOpen always?

You can keep the DropDownPopup of SfMultiColumnDropDownControl open always by using the StaysOpen property. In Loaded event, you can get the “PART_Popup” template from the SfMultiColumnDropDownControl and set the StaysOpen property to true.

The following code example illustrates how to set StaysOpen property for DropDownPopup.
{% highlight C# %}





sfmulticolumn.Loaded += (o, e) =>

   {

    var popup= sfmulticolumn.Template.FindName("PART_Popup", sfmulticolumn) as Popup;

    popup.StaysOpen=true;

   };
{% endhighlight %}

