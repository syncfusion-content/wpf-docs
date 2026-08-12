---
layout: post
title: Weight Value Path in WPF TreeMap | Syncfusion®
description: Weight value path in the WPF TreeMap maps data values to item sizes, enabling proportional visualization of hierarchical data.
platform: wpf
control: TreeMap
documentation: ug
---

# Weight Value Path in WPF TreeMap

The [WeightValuePath](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeMap.SfTreeMap.html#Syncfusion_UI_Xaml_TreeMap_SfTreeMap_WeightValuePath) of [SfTreeMap](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeMap.SfTreeMap.html) is a path to a field on the source object, which serve as the "weight" of the object. 


{% highlight xaml %}

<Grid Background="Black">
    <Grid.DataContext>
        <local:PopulationViewModel />
    </Grid.DataContext>

    <syncfusion:SfTreeMap ItemsSource="{Binding PopulationDetails}"
                          WeightValuePath="Population" />
</Grid>

{% endhighlight %}

N> The specified field must be available in each and every sub class (object) defined in hierarchical (nested) data collection.

![WeightValuePath_img1](WeightValuePath_images/WeightValuePath_img1.png)



