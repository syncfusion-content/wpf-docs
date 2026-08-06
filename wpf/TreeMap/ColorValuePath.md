---
layout: post
title: Color Value Path in WPF TreeMap | Syncfusion®
description: Color value path in the WPF TreeMap maps data values to color ranges, enabling meaningful visualization and analysis of hierarchical data.
platform: wpf
control: TreeMap
documentation: ug
---

# Color Value Path in WPF TreeMap

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



