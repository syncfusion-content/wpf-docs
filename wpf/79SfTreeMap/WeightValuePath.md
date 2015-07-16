---
layout: post
title: WeightValuePath
description: weightvaluepath
platform: wpf
control: TreeMap
documentation: ug
---

# WeightValuePath

The WeightValuePath ofSfTreeMap is a path to a field on the source object, which serve as the "weight" of the object. 



[XAML]



    &lt;Grid Background="Black"&gt;

        &lt;Grid.DataContext&gt;

            &lt;local:PopulationViewModel/&gt;

        &lt;/Grid.DataContext&gt;

        <syncfusion:SfTreeMap ItemsSource="{Binding PopulationDetails}" 

                              WeightValuePath="Population”/>

    &lt;/Grid&gt;





> _Note:____The specified field must be available in each and every sub class (object) defined in hierarchical (nested) data collection._

{ ![](WeightValuePath_images/WeightValuePath_img1.png) | markdownify }
{:.image }


