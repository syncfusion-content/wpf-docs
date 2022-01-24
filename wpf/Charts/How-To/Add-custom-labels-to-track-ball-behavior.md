---
layout: post
title: Add custom labels to track ball behavior| SfChart | Wpf | Syncfusion
description: Add custom labels to track ball behavior in Syncfusion WPF Chart (SfChart) control, its elements and more.
platform: wpf
control: SfChart
documentation: ug
---

# Add custom labels to track ball behavior

In the ChartTrackBallBehavior, each data point will have a label aligned vertically and horizontally using the LabelVerticalAlignment and LabelHorizontalAlignment properties by default. However, you can also add custom labels to the ChartTrackBallBehavior.

In order to add a custom label, you need to write a class derived from ChartTrackBallBehavior. You need to override GenerateLabels method, which will be called whenever new labels are going to be generated, and add the labels using AddLabel method. The following code sample demonstrates this:


{% highlight c# %}

public class CustomTrackBallBehavior : ChartTrackBallBehavior
{
    public DataTemplate CustomLabelTemplate
    {
        get { return (DataTemplate)GetValue(CustomLabelTemplateProperty); }
        set { SetValue(CustomLabelTemplateProperty, value); }
    }

    // Using a DependencyProperty as the backing store for CustomLabelTemplate.  This enables animation, styling, binding, etc.
    public static readonly DependencyProperty CustomLabelTemplateProperty =
        DependencyProperty.Register("CustomLabelTemplate", typeof(DataTemplate), typeof(CustomTrackBallBehavior), new PropertyMetadata(null));

    protected override void GenerateLabels()
    {
        AddLabel(PointInfos[0], LabelVerticalAlignment, LabelHorizontalAlignment, PointInfos[0].Series.TrackBallLabelTemplate);
        AddLabel(PointInfos[1], LabelVerticalAlignment, LabelHorizontalAlignment, PointInfos[1].Series.TrackBallLabelTemplate);

        ChartPointInfo pointInfo1 = PointInfos[0];
        ChartPointInfo pointInfo2 = PointInfos[1];

        CustomLabel label = new CustomLabel();
        label.Value1 = pointInfo2.ValueY;
        label.Value2 = pointInfo1.ValueY;

        Rect rect = this.ChartArea.SecondaryAxis.ArrangeRect;

        //Custom label.
        AddLabel(label, LabelVerticalAlignment, LabelHorizontalAlignment, CustomLabelTemplate, pointInfo1.X, rect.Top);
    }
}

public class CustomLabel
{
    public string Value1 { get; set; }
    public string Value2 { get; set; }
}

{% endhighlight  %}

{% highlight xaml %}

<chart:SfChart x:Name="chart" >

    <chart:SfChart.Resources>
        <DataTemplate x:Key="customLabel">
            <Border BorderThickness="1" BorderBrush="Black" Background="LightBlue">
                <StackPanel>
                    <StackPanel Orientation="Horizontal">
                        <Label Content="Series1:" Foreground="Red"/>
                        <Label Content="{Binding Value1}" Foreground="DarkBlue"/>
                    </StackPanel>

                    <StackPanel Orientation="Horizontal">
                        <Label Content="Series2:" Foreground="Red"/>
                        <Label Content="{Binding Value2}" Foreground="DarkBlue"/>
                    </StackPanel>
                </StackPanel>
            </Border>
        </DataTemplate>
    </chart:SfChart.Resources>

    <chart:SfChart.PrimaryAxis>
        <chart:NumericalAxis/>
    </chart:SfChart.PrimaryAxis>
    
    <chart:SfChart.SecondaryAxis>
        <chart:NumericalAxis />
    </chart:SfChart.SecondaryAxis>

    <!--Add LineSeries-->
    <chart:LineSeries Palette="LightCandy"
            ItemsSource="{Binding Data}" 
            XBindingPath="XValue"                            
            YBindingPath="YValue" />

    <!--Add LineSeries-->
    <chart:LineSeries Palette="Metro"
            ItemsSource="{Binding Data1}"                             
            XBindingPath="XValue"                            
            YBindingPath="YValue" />

    <!--Add custom trackball behavior-->
    <chart:SfChart.Behaviors>
        <local:CustomTrackBallBehavior CustomLabelTemplate="{StaticResource customLabel}"/>
    </chart:SfChart.Behaviors>

</chart:SfChart>

{% endhighlight %}
