---
layout: post
title: LeafItemSettings
description: leafitemsettings
platform: wpf
control: TreeMap
documentation: ug
---

# LeafItemSettings

LeafItemSettings of SfTreeMap is a setting by which we can settings the template for the leafNode.


{% highlight xml %}
[XAML]



    <Grid Background="Black">

        <Grid.DataContext>

            <local:PopulationViewModel/>

        </Grid.DataContext>

        <syncfusion:SfTreeMap Name="TreeMap" ItemsSource="{Binding PopulationDetails}" WeightValuePath="Population" ColorValuePath="Growth"

                              ItemsLayoutMode="Squarified" Margin="10">

            <syncfusion:SfTreeMap.LeafItemSettings>

                <syncfusion:LeafItemSettings/>

            </syncfusion:SfTreeMap.LeafItemSettings>

       </syncfusion:SfTreeMap>

    </Grid> 

{% endhighlight %}



> _Note: The specified field must be available in each and every sub class (object) defined in hierarchical (nested) data collection._



## LabelPath

LabelPath of the leaves is WeightValuePath by default and you can change the LabelPath as desired based on the data provided.


{% highlight xml %}
[XAML]



    <Grid Background="Black">

        <Grid.DataContext>

            <local:PopulationViewModel/>

        </Grid.DataContext>

        <syncfusion:SfTreeMap Name="TreeMap" ItemsSource="{Binding PopulationDetails}" WeightValuePath="Population" ColorValuePath="Growth"

                              ItemsLayoutMode="Squarified" Margin="10">

            <syncfusion:SfTreeMap.LeafItemSettings>

                <syncfusion:LeafItemSettings LabelPath="Country"/>                                                                                      </syncfusion:SfTreeMap.LeafItemSettings>

       </syncfusion:SfTreeMap>

    </Grid> 
{% endhighlight %}


## LabelTemplate

LabelTemplate of LeafitemSettings class provides the template for the labels of the leafNodes.


{% highlight xml %}
[XAML]



    <Grid Background="Black">

        <Grid.DataContext>

            <local:PopulationViewModel/>

        </Grid.DataContext>

        <syncfusion:SfTreeMap Name="TreeMap" ItemsSource="{Binding PopulationDetails}" WeightValuePath="Population" ColorValuePath="Growth"

                              ItemsLayoutMode="Squarified" Margin="10">

            <syncfusion:SfTreeMap.LeafItemSettings>

                <syncfusion:LeafItemSettings>

                    <syncfusion:LeafItemSettings.LabelTemplate>

                            <DataTemplate>

                                <TextBlock Text="{Binding Data.Country}" Foreground="White" FontSize="16" FontWeight="Normal" HorizontalAlignment="Left" VerticalAlignment="Top" Margin="5,5,0,0"/>

                            </DataTemplate>



                    </syncfusion:LeafItemSettings.LabelTemplate>

                </syncfusion:LeafItemSettings>

            </syncfusion:SfTreeMap.LeafItemSettings>

       </syncfusion:SfTreeMap>

    </Grid> 
{% endhighlight %}


## Gap

Gap provides the gap between the leaves at Leaf Level.


{% highlight xml %}
[XAML]



    <Grid Background="Black">

        <Grid.DataContext>

            <local:PopulationViewModel/>

        </Grid.DataContext>

        <syncfusion:SfTreeMap Name="TreeMap" ItemsSource="{Binding PopulationDetails}" WeightValuePath="Population" ColorValuePath="Growth"

                              ItemsLayoutMode="Squarified" Margin="10">

            <syncfusion:SfTreeMap.LeafItemSettings>

                <syncfusion:LeafItemSettings Gap="5">

                </syncfusion:LeafItemSettings>

            </syncfusion:SfTreeMap.LeafItemSettings>

       </syncfusion:SfTreeMap>

    </Grid> 
{% endhighlight %}


## BorderBrush

BorderBrush provides the border color for the leafNodes and BorderThickness provides the thickness of the BorderBrush.


{% highlight xml %}
[XAML]



    <Grid Background="Black">

        <Grid.DataContext>

            <local:PopulationViewModel/>

        </Grid.DataContext>

        <syncfusion:SfTreeMap Name="TreeMap" ItemsSource="{Binding PopulationDetails}" WeightValuePath="Population" ColorValuePath="Growth"

                              ItemsLayoutMode="Squarified" Margin="10">

            <syncfusion:SfTreeMap.LeafItemSettings>

                <syncfusion:LeafItemSettings BorderBrush="Red" BorderThickness="3"/>  

            </syncfusion:SfTreeMap.LeafItemSettings>

       </syncfusion:SfTreeMap>

    </Grid> 
{% endhighlight %}




![](LeafItemSettings_images/LeafItemSettings_img1.png)



