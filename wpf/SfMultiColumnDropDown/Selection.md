---
layout: post
title: Selection| SfMultiColumnDropDownControl | Wpf | Syncfusion
description: selection
platform: wpf
control: SfMultiColumnDropDownControl
documentation: ug
---

# Selection

SfMultiColumnControl allows you to select the item from the DropDownGrid. SfMultiColumnDropDownControl exposes the following properties for Selection.

* SelectedIndex - This property represents the currently selected index from the Collection. By default it is set to -1.
* SelectedItem – This property represents the currently selected item. By default, it is set to null.
* SelectedValue – This property represents the currently selected value from the SelectedItem based on the DisplayMember value .By default it is set to null.

The following code example illustrates how to set SelectedIndex in SfMultiColumnDropDownControl.

{% highlight C# %}





<Window.DataContext>

  <local:Viewmodel/>

</Window.DataContext>





<syncfusion:SfMultiColumnDropDownControl x:Name="sfmulticolumn"

SelectedIndex="3"

ValueMember="Designation"                                                   

DisplayMember="Name" 

ItemsSource="{Binding GridItemSource}">



</syncfusion:SfMultiColumnDropDownControl>
{% endhighlight %}

The following screenshot illustrates the output of the above code.

![](Features_images/Features_img7.png)



### Event



<table>
<tr>
<th>
EventName</th><th>
Description</th></tr>
<tr>
<td>
SelectionChanged</td><td>
This event is raised when the Selection is changed.The SelectionChanged event handler receives two arguments, namely Sender and SelectionChangedEventArgs{{ '_,_' | markdownify }} as objects.The SelectionChangedEventArgs object contains the following properties:* SelectedIndex: Gets the selected index of the SfDataGrid in the DropDownPopup.* SelectedItem: Gets the selected item of the SfDataGrid in the DropDownPopup.</td></tr>
</table>

## How To

### How to Select the Text When SfMultiColumnDropDownControl got Focus?


In SfMultiColumnDropDownControl, the TextSelectionOnFocus property automatically selects the text when SfMultiColumnDropDownControl got focus from one control. 

The following code example illustrates how to use TextSelectionOnFocus in SfMultiColumnDropDownControl.


{% highlight xaml %}



<syncfusion:SfMultiColumnDropDownControl x:Name="MultiColumnControl"                                          

AutoGenerateColumns="True"

DisplayMember="Title"

ItemsSource="{Binding MoviesLists}"

SelectedIndex="3"  

TextSelectionOnFocus="True"  

ValueMember="Cast">

</syncfusion:SfMultiColumnDropDownControl>

{% endhighlight %}

The following screenshot displays the SfMultiDropDownControl when setting TextSelectionOnFocus to true.

![](Features_images/Features_img8.png)



