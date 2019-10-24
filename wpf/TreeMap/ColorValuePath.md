---
layout: post
title: ColorValuePath | TreeMap | wpf | Syncfusion
description: colorvaluepath
platform: wpf
control: TreeMap
documentation: ug
---

# ColorValuePath

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



