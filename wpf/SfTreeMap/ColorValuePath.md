---
layout: post
title: ColorValuePath
description: colorvaluepath
platform: wpf
control: TreeMap
documentation: ug
---

# ColorValuePath

The ColorValuePath ofSfTreeMap is a path to a field on the source object, which serves as the "color" of the object. 



[XAML]



    &lt;Grid Background="Black"&gt;

        &lt;Grid.DataContext&gt;

            &lt;local:PopulationViewModel/&gt;

        &lt;/Grid.DataContext&gt;

        <syncfusion:SfTreeMap ItemsSource="{Binding PopulationDetails}" 

                              ColorValuePath="Growth"/>

    &lt;/Grid&gt; 





> _Note: The specified field must be available in each and every sub class (object) defined in hierarchical (nested) data collection._



