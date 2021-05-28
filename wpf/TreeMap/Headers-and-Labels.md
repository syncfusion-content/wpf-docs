---
layout: post
title: Headers and Labels in WPF TreeMap control | Syncfusion
description: Learn here all about Headers and Labels support in Syncfusion WPF TreeMap (SfTreeMap) control and more.
platform: wpf
control: TreeMap
documentation: ug
---

# Headers and Labels in WPF TreeMap (SfTreeMap)

## Headers

To show headers in TreeMap, you can set the HeaderHeight property of TreeMapLevel. For customizing default Header appearance, you can specify the HeaderTemplate.

### TreeMap with Flat Collection:

If HeaderTemplate is specified for TreeMapLevel, then the header can be bound by referring Header object to the data template.


{% highlight xaml %}



<Grid Background="Black">

    <Grid.DataContext>

        <local:PopulationViewModel/>

    </Grid.DataContext>

    <syncfusion:SfTreeMap ItemsSource="{Binding PopulationDetails}" 

                        WeightValuePath="Population" ColorValuePath="Growth">

        <syncfusion:SfTreeMap.Levels>

            <syncfusion:TreeMapFlatLevel GroupPath="Continent" GroupGap="10" HeaderHeight="50"/>

            <syncfusion:TreeMapFlatLevel GroupPath="Country" GroupGap="5"/>

        </syncfusion:SfTreeMap.Levels>

    </syncfusion:SfTreeMap>

</Grid>
{% endhighlight %}


![Headers-and-Labels_img1](Headers-and-Labels_images/Headers-and-Labels_img1.png)



### TreeMap with Hierarchical Collection:

For TreeMap with Hierarchical Collection, HeaderPath must be specified. The header can be bound by referring Data.<FieldName> to the data template where FieldName refers to the field of object specified in the particular treemap level.


{% highlight xaml %}



<Grid Background="Black">

    <Grid.Resources>

        <local:CountrySalesCollection x:Key="countrySalesCollection"/>

    </Grid.Resources>

    <syncfusion:SfTreeMap ItemsSource="{Binding Source={StaticResource countrySalesCollection}}" WeightValuePath="Sales" ColorValuePath="Expense">

        <syncfusion:SfTreeMap.Levels>

            <syncfusion:TreeMapHierarchicalLevel ChildPath="RegionalSalesCollection" ChildGap="10" HeaderHeight="25" HeaderPath="Name">

            </syncfusion:TreeMapHierarchicalLevel>

        </syncfusion:SfTreeMap.Levels>

    </syncfusion:SfTreeMap>

</Grid>
{% endhighlight %}

## Labels

To show labels in TreeMap, ShowLabels of TreeMapLevel should be enabled to True. For customizing default label appearance, you can specify LabelTemplate.

### TreeMap with Flat Collection:

If LabelTemplate is specified for TreeMapLevel, then the label can be bound by referring Label object to the data template.


{% highlight xaml %}



<Grid Background="Black">

    <Grid.DataContext>

        <local:PopulationViewModel/>

    </Grid.DataContext>

    <syncfusion:SfTreeMap ItemsSource="{Binding PopulationDetails}"

                          WeightValuePath="Population" 

                          ColorValuePath="Growth">

        <syncfusion:SfTreeMap.Levels>

            <syncfusion:TreeMapFlatLevel GroupPath="Continent" GroupGap="10" ShowLabels="True"/>

        </syncfusion:SfTreeMap.Levels>

    </syncfusion:SfTreeMap>

</Grid>
{% endhighlight %}




![Headers-and-Labels_img2](Headers-and-Labels_images/Headers-and-Labels_img2.png)


### TreeMap with Hierarchical Collection:

For TreeMap with Hierarchical Collection, LabelPath must be specified. The label can be bound by referring Data. <FieldName> to the data template where FieldName refers to the field of object specified in the particular treemap level.


{% highlight xaml %}

<Grid Background="Black">

    <Grid.Resources>

        <local:CountrySalesCollection x:Key="countrySalesCollection"/>

    </Grid.Resources>

    <syncfusion:SfTreeMap ItemsSource="{Binding Source={StaticResource countrySalesCollection}}"

                      WeightValuePath="Sales" ColorValuePath="Expense">

        <syncfusion:SfTreeMap.Levels>

            <syncfusion:TreeMapHierarchicalLevel ChildPath="RegionalSalesCollection" ChildGap="10" ShowLabels="True" LabelPath="Name">

            </syncfusion:TreeMapHierarchicalLevel>

        </syncfusion:SfTreeMap.Levels>

    </syncfusion:SfTreeMap>

</Grid>
{% endhighlight %}


