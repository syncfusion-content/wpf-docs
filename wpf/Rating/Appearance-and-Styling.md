---
layout: post
title: Customizing Appearance and Styling in WPF Rating Control | Syncfusion®
description: Discover how to customize the appearance and styling of the Syncfusion® WPF Rating (SfRating) control, focusing on item sizes, colors, and styles.
platform: WPF
control: SfRating
documentation: ug
---

# Customizing Appearance and Styling in WPF Rating (SfRating)

The default view of the SfRating control can be altered to suit your needs by customizing the size, item count, and spacing between rating items.

> **Note**: These properties are available in `SfRatingItem`. To set these properties, use the `ItemContainerStyle` property of the SfRating control.

## Setting Fill Colors

The SfRating control allows for specifying fill colors for both selected and unselected items.

### Selected Items

Use the `RatedFill` property to fill the rated area with a specified color in the SfRating control.

{% highlight xaml %}

    <rating:SfRating ItemsCount="5" Value="2" >
        <rating:SfRating.ItemContainerStyle>
            <Style TargetType="rating:SfRatingItem">
                <Setter Property="RatedFill" Value="Green"></Setter>
            </Style>
        </rating:SfRating.ItemContainerStyle>
    </rating:SfRating>
	
{% endhighlight %}

![Rated item](images/rated_fill.png)

### Unselected Items

The `UnRatedFill` property fills the unrated area with a specified color in the SfRating control.

{% highlight xaml %}

    <rating:SfRating ItemsCount="5" Value="2" >
        <rating:SfRating.ItemContainerStyle>
            <Style TargetType="rating:SfRatingItem">
                <Setter Property="UnratedFill" Value="Green">
                </Setter>
            </Style>
        </rating:SfRating.ItemContainerStyle>
    </rating:SfRating>

{% endhighlight %}

![Unrated item](images/unrated_fill.png)

## Set stroke color

SfRating control supports setting stroke colors for both selected and unselected items.

### Selected Items

The `RatedStroke` property sets the stroke color for the rated area with the specified color.

{% highlight xaml %}

    <rating:SfRating ItemsCount="5" Value="2" >
        <rating:SfRating.ItemContainerStyle>
            <Style TargetType="rating:SfRatingItem">
                <Setter Property="RatedStroke" Value="Green">
                </Setter>
            </Style>
        </rating:SfRating.ItemContainerStyle>
    </rating:SfRating>
	
{% endhighlight %}

![Rated item stroke color](images/ratedstroke.png)

### Unselected Items

The `UnRatedStroke` property specifies the stroke color for the unrated area.
{% highlight xaml %}

    <rating:SfRating ItemsCount="5" Value="2" >
        <rating:SfRating.ItemContainerStyle>
            <Style TargetType="rating:SfRatingItem">
                <Setter Property="UnratedStroke" Value="Green">
                </Setter>
            </Style>
        </rating:SfRating.ItemContainerStyle>
    </rating:SfRating>

{% endhighlight %}

![Unrated item stroke color](images/unratedstroke.png)

## Setting Stroke Thickness

The SfRating control also supports customizing stroke thickness for selected and unselected items.

### Selected Items

The `RatedStrokeThickness` property defines the stroke thickness for the rated area.

{% highlight xaml %}

    <rating:SfRating ItemsCount="5" Value="2" >
        <rating:SfRating.ItemContainerStyle>
            <Style TargetType="rating:SfRatingItem">
                <Setter Property="RatedStroke" Value="Green"></Setter>
                <Setter Property="RatedStrokeThickness" Value="2"></Setter>
            </Style>
        </rating:SfRating.ItemContainerStyle>
    </rating:SfRating>

{% endhighlight %}

![Rated item stroke thickness](images/ratedstrokethickness.png)

### Unselected Items

The `UnRatedStrokeThickness` property sets the stroke thickness for unrated items.

{% highlight xaml %}

    <rating:SfRating ItemsCount="5" Value="2" >
        <rating:SfRating.ItemContainerStyle>
            <Style TargetType="rating:SfRatingItem">
                <Setter Property="UnratedStroke" Value="Green"></Setter>
                <Setter Property="UnratedStrokeThickness" Value="2"></Setter>
            </Style>
        </rating:SfRating.ItemContainerStyle>
    </rating:SfRating>
	
{% endhighlight %}

![Unrated item stroke thickness](images/unratedstrokethickness.png)

## Pointer Over Effects

SfRating enables customization of interactions through pointer effects.

### PointerOverFill
The `PointerOverFill` property fills the area under the mouse pointer with a specified color.

{% highlight xaml %}

    <rating:SfRating ItemsCount="5">
        <rating:SfRating.ItemContainerStyle>
            <Style TargetType="rating:SfRatingItem">
                <Setter Property="PointerOverFill" Value="Green"></Setter>
            </Style>
        </rating:SfRating.ItemContainerStyle>
    </rating:SfRating>

{% endhighlight %}

![PointerOverFill](images/pointover_fill.png)

### PointerOverStroke

Sets the stroke color for the area under the mouse pointer using the `PointerOverStroke` property.
{% highlight xaml %}

    <rating:SfRating ItemsCount="5">
        <rating:SfRating.ItemContainerStyle>
            <Style TargetType="rating:SfRatingItem">
                <Setter Property="PointerOverStroke" Value="Green"></Setter>
            </Style>
        </rating:SfRating.ItemContainerStyle>
    </rating:SfRating>

{% endhighlight %}

![PointerOverStroke](images/pointover_stroke.png)

### PointerOverStrokeThickness

The `PointerOverStrokeThickness` property sets stroke thickness for the mouse-over area.

{% highlight xaml %}

    <rating:SfRating ItemsCount="5">
        <rating:SfRating.ItemContainerStyle>
            <Style TargetType="rating:SfRatingItem">
                <Setter Property="PointerOverStroke" Value="Green"></Setter>
                <Setter Property="PointerOverStrokeThickness" Value="2"></Setter>
            </Style>
        </rating:SfRating.ItemContainerStyle>
    </rating:SfRating>

{% endhighlight %}

![PointerOverStrokeThickness](images/pointover_strokethickness.png)

## Customizing Item Height
Adjust the height of each `SfRatingItem` by using the `Height` property.

{% tabs %}

{% highlight xaml %}

    <rating:SfRating Value="3" >
        <rating:SfRatingItem  Height="20"/>
        <rating:SfRatingItem  Height="18"/>
        <rating:SfRatingItem  Height="16"/>
        <rating:SfRatingItem  Height="14"/>
        <rating:SfRatingItem  Height="12"/>
    </rating:SfRating>

{% endhighlight %}

{% highlight C# %}

SfRating rating;
public MainWindow()
{
    InitializeComponent();
    rating = new SfRating();
    rating.Value = 3;
    rating.Items.Add(new SfRatingItem() { Height = 20 });
    rating.Items.Add(new SfRatingItem() { Height = 18 });
    rating.Items.Add(new SfRatingItem() { Height = 16 });
    rating.Items.Add(new SfRatingItem() { Height = 14 });
    rating.Items.Add(new SfRatingItem() { Height = 12 });
    Content = rating;
}

{% endhighlight %}

{% endtabs %}

![SfRating item custom height](images/height_customization.png)

To set the same height for each `SfRatingItem`, use the `ItemContainerStyle` property.

{% highlight xaml %}

    <rating:SfRating Value="4" ItemsCount="10" >
        <rating:SfRating.ItemContainerStyle>
            <Style TargetType="rating:SfRatingItem">
                <Setter Property="Height" Value="12"></Setter>
            </Style>
        </rating:SfRating.ItemContainerStyle>
    </rating:SfRating>

{% endhighlight %}

![SfRating item uniform height](images/equal_height.png)
