---
layout: post
title: WeightValuePath | TreeMap | wpf | Syncfusion
description: weightvaluepath
platform: wpf
control: TreeMap
documentation: ug
---

# WeightValuePath

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

![](WeightValuePath_images/WeightValuePath_img1.png)



