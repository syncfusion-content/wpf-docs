---
layout: post
title: WeightValuePath in WPF TreeMap control | Syncfusion
description: Learn here all about WeightValuePath support in Syncfusion WPF TreeMap (SfTreeMap) control and more.
platform: wpf
control: TreeMap
documentation: ug
---

# WeightValuePath in WPF TreeMap (SfTreeMap)

The WeightValuePath ofSfTreeMap is a path to a field on the source object, which serve as the "weight" of the object. 


{% highlight xaml %}



    <Grid Background="Black">

        <Grid.DataContext>

            <local:PopulationViewModel/>

        </Grid.DataContext>

        <syncfusion:SfTreeMap ItemsSource="{Binding PopulationDetails}" 

                              WeightValuePath="Population”/>

    </Grid>

{% endhighlight %}



N> The specified field must be available in each and every sub class (object) defined in hierarchical (nested) data collection.

![WeightValuePath_img1](WeightValuePath_images/WeightValuePath_img1.png)



