---
layout: post
title: Selection Support | TreeMap | wpf | Syncfusion
description: This section describes selection by setting HighlightOnSelection property and group selection support by setting HighlightGroupOnSelection property in SfTreeMap.
platform: wpf
control: TreeMap
documentation: ug
---

# Selection Support in SfTreeMap

While selecting a leaf node, you can highlight it by setting HighlightOnSelection property of SfTreeMap to “True”. The border of highlight on selection can be customized by HighlightBorderBrush and HighlightBorderThickness properties of SfTreeMap. SelectionMode can also be set to either “Default” or “Multiple”. “Multiple” selection of leaf nodes is made possible by pressing the control key continuously while Mouse Click happens.


{% highlight xaml %}

<syncfusion:SfTreeMap Name="TreeMap" ItemsSource="{Binding PopulationDetails}" 

                       WeightValuePath="Population"                              

                       ColorValuePath="Growth"

                       HighlightOnSelection="True"

                       HighlightBorderBrush="Red"

                       HighlightBorderThickness="4"

                       HighlightHoverBrush="Yellow"

                       SelectionModes="Multiple">

</syncfusion:SfTreeMap>
{% endhighlight %}




![Selection Support_images](Selection-Support_images/Selection-Support_img1.png)



GroupSelection support is also provided under selection support where the whole group can be selected. While selecting a leaf node, you can highlight it by setting HighlightGroupOnSelection property of SfTreeMap to “True”. The helper properties, HighlightBorderBrush, HighlightBorderThickness, and SelectionModes are shared for both HighlightOnSelection and HighlightGroupOnSelection.


{% highlight xaml %}



<syncfusion:SfTreeMap Name="TreeMap" ItemsSource="{Binding PopulationDetails}" 

                       WeightValuePath="Population"                              

                       ColorValuePath="Growth"

                       HighlightGroupOnSelection="True"

                       HighlightBorderBrush="Red"

                       HighlightBorderThickness="4"

                       SelectionModes="Multiple" >

        </syncfusion:SfTreeMap>
{% endhighlight %}


![GroupSelection support_images](Selection-Support_images/Selection-Support_img2.png)

## see also

[How to highlight group selection](https://www.syncfusion.com/kb/7654/how-to-highlight-group-selection) 