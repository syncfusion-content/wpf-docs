---
layout: post
title: ColorValuePath in WPF TreeMap control | Syncfusion
description: Learn here all about ColorValuePath support in Syncfusion WPF TreeMap (SfTreeMap) control, its elements and more.
platform: wpf
control: TreeMap
 documentation: ug
---

# ColorValuePath in WPF TreeMap (SfTreeMap)

The ColorValuePath ofSfTreeMap is a path to a field on the source object, which serves as the "color" of the object. 

{% highlight xaml %}




    <Grid Background="Black">

        <Grid.DataContext>

            <local:PopulationViewModel/>

        </Grid.DataContext>

        <syncfusion:SfTreeMap ItemsSource="{Binding PopulationDetails}" 

                              ColorValuePath="Growth"/>

    </Grid> 

{% endhighlight %}



N> The specified field must be available in each and every sub class (object) defined in hierarchical (nested) data collection.



