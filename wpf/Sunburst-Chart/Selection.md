---

layout: post
title: Selection in WPF Sunburst Chart control | Syncfusion
description: Learn here all about Selection support in Syncfusion WPF Sunburst Chart (SfSunburstChart) control and more.
platform: wpf 
control: SfSunburstChart 
documentation: ug

---

# Selection in WPF Sunburst Chart (SfSunburstChart)

Sunburst chart supports selection that enables you to select a segment by using [`SunburstSelectionBehavior`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.SunburstChart.SunburstSelectionBehavior.html). 

The below code shows, how to enable the selection behavior.  

{% tabs %}

{% highlight xaml %}

<sunburst:SfSunburstChart.Behaviors>

   <sunburst:SunburstSelectionBehavior/>

</sunburst:SfSunburstChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

SunburstSelectionBehavior selection = new SunburstSelectionBehavior();
chart.Behaviors.Add(selection);

{% endhighlight %}

{% endtabs %}

![Selection_img1](Selection_images/Selection_img1.jpeg)


## SelectionDisplayMode

You can customize the selected segment appearance by using brush or opacity. You can choose between color or opacity using the [`SelectionDisplayMode`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.SunburstChart.SunburstSelectionBehavior.html#Syncfusion_UI_Xaml_SunburstChart_SunburstSelectionBehavior_SelectionDisplayMode) property in the selection behavior 

* HighlightByColor – To display the selected segment appearance using brush.
* HighlightByOpacity – To display the selected segment appearance using opacity.

The following code shows, how to set the display mode using brush.

{% tabs %}

{% highlight xaml %}

<sunburst:SfSunburstChart.Behaviors>

                <sunburst:SunburstSelectionBehavior EnableSelection="True"
                                                    SelectionBrush="Black"
                                                    SelectionDisplayMode="HighlightByColor"/>
            
</sunburst:SfSunburstChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

SunburstSelectionBehavior selection = new SunburstSelectionBehavior();
selection.EnableSelection = true;
selection.SelectionBrush = new SolidColorBrush(Colors.Black);
selection.SelectionDisplayMode = SelectionDisplayMode.HighlightByColor;
chart.Behaviors.Add(selection);

{% endhighlight %}

{% endtabs %}

![Selection_img2](Selection_images/Selection_img2.jpeg)


N> The default value of SelectionDisplayMode is HighlightByOpacity.

## SelectionMode

Sunburst chart provides support to select or highlight the segment by clicking or hovering the mouse over a segment. By default, this property value is MouseClick.

* Both – Select the segment using mouse move and mouse click.
* MouseClick – Select the segment using mouse click.
* MouseMove – Select the segment using mouse move.

{% tabs %}

{% highlight xaml %}

 <sunburst:SfSunburstChart.Behaviors>

     <sunburst:SunburstSelectionBehavior EnableSelection="True"
                                         SelectionMode="MouseClick"/>
</sunburst:SfSunburstChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

SunburstSelectionBehavior selection = new SunburstSelectionBehavior();
selection.EnableSelection = true;
selection.SelectionMode = Syncfusion.UI.Xaml.SunburstChart.SelectionMode.MouseClick;
chart.Behaviors.Add(selection);

{% endhighlight %}

{% endtabs %}

## SelectionType

Sunburst chart provides multiple option to represent the selected categories. You can select the segment categories by using the [`SelectionType`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.SunburstChart.SunburstSelectionBehavior.html#Syncfusion_UI_Xaml_SunburstChart_SunburstSelectionBehavior_SelectionType) property in selection behavior.

* Child – To select the child of selected parent.
* Group – To select the entire categories in group.
* Parent – To select the parent of selected child.
* Single - To select single item in the category.

### Child

The following code shows, how to set the selection type as child.

{% tabs %}

{% highlight xaml %}

 <sunburst:SfSunburstChart.Behaviors>

                <sunburst:SunburstSelectionBehavior EnableSelection="True"
                                                    SelectionType="Child"  />
</sunburst:SfSunburstChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

SunburstSelectionBehavior selection = new SunburstSelectionBehavior();
selection.EnableSelection = true;
selection.SelectionType = SelectionType.Child;
chart.Behaviors.Add(selection);

{% endhighlight %}

{% endtabs %}

![Selection_img3](Selection_images/Selection_img3.jpeg)


### Group

The following code shows, how to set the selection type as group.

{% highlight xaml %}

<sunburst:SfSunburstChart.Behaviors>

                <sunburst:SunburstSelectionBehavior EnableSelection="True"
                                                    SelectionType="Group"  />
</sunburst:SfSunburstChart.Behaviors>

{% endhighlight %}

![Selection_img4](Selection_images/Selection_img4.jpeg)


### Parent

The following code shows, how to set the selection type as parent.

{% highlight xaml %}

<sunburst:SfSunburstChart.Behaviors>

                <sunburst:SunburstSelectionBehavior EnableSelection="True"
                                                    SelectionType="Parent"  />
</sunburst:SfSunburstChart.Behaviors>

{% endhighlight %}

![Selection_img5](Selection_images/Selection_img5.jpeg)

### Single

The following code shows, how to set the selection type as single.

{% highlight xaml %}

<sunburst:SfSunburstChart.Behaviors>

                <sunburst:SunburstSelectionBehavior EnableSelection="True"
                                                    SelectionType="Single"  />
</sunburst:SfSunburstChart.Behaviors>

{% endhighlight %}

![Selection_img6](Selection_images/Selection_img6.jpeg)

## Selection Cursor

SelectionCursor property allows you to customize the cursor when mouse is hovered over the segment. 

The following code shows, how to set the selection cursor as hand.

{% tabs %}

{% highlight xaml %}

<sunburst:SfSunburstChart.Behaviors>

              <sunburst:SunburstSelectionBehavior EnableSelection="True"
                                                  SelectionCursor="Hand" />

</sunburst:SfSunburstChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

SunburstSelectionBehavior selection = new SunburstSelectionBehavior();
selection.EnableSelection = true;
selection.SelectionCursor = Cursors.Hand;
chart.Behaviors.Add(selection);

{% endhighlight %}

{% endtabs %}

![Selection_img7](Selection_images/Selection_img7.jpeg)


