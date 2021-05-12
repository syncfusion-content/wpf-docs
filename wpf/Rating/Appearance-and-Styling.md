---
layout: post
title: Appearance and Styling in WPF Rating control | Syncfusion
description: Learn here all about Appearance and Styling support in Syncfusion WPF Rating (SfRating) control and more.
platform: wpf
control: SfRating
documentation: ug
---

# Appearance and Styling in WPF Rating (SfRating)

When the default view is not needed, you can customize the view of WPF SfRating control. The SfRating control provides support to customize the size, item count, and space between rating items.

N> These properties are available in SfRatingItem. To set this property, use the ItemContainerStyle property of the SfRating control.

## Set fill color

The SfRating control supports to set the fill color to the selected and unselected items.

### Selected items

The `RatedFill` property fills the rated area with the specified solid color in the SfRating control.

{% highlight xaml %}

    <rating:SfRating ItemsCount="5" Value="2" >
        <rating:SfRating.ItemContainerStyle>
            <Style TargetType="rating:SfRatingItem">
                <Setter Property="RatedFill" Value="Green"></Setter>
            </Style>
        </rating:SfRating.ItemContainerStyle>
    </rating:SfRating>
	
{% endhighlight %}

![Rated item ](images/rated_fill.png)

### Unselected items

The `UnRatedFill` property fills the unrated area with the specified solid color in the SfRating control.

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

The SfRating control supports to set the stroke color to the selected and unselected items.

### Selected items

The `RatedStroke` property sets the stroke color to the rated area with the specified solid color to the selected items in the SfRating control.

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

### Unselected items

The `UnratedStroke` property sets the stroke color to the unrated area with the specified solid color in the SfRating control.

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

## Set stroke thickness

The SfRating control supports to set the stroke thickness to the selected and unselected items.

### Selected items

The `RatedStrokeThickness` property sets the stroke thickness to the rated area with the specified value in the SfRating control.

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

### Unselected items

The `UnratedStrokeThickness` property sets the stroke thickness to the unrated area with the specified value in the SfRating control.

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

### PointerOverFill

The `PointerOverFill` property fills the mouse over area with the specified solid color in the SfRating control.

{% highlight xaml %}

    <rating:SfRating ItemsCount="5">
        <rating:SfRating.ItemContainerStyle>
            <Style TargetType="rating:SfRatingItem">
                <Setter Property="PointerOverFill" Value="Green"></Setter>
            </Style>
        </rating:SfRating.ItemContainerStyle>
    </rating:SfRating>

{% endhighlight %}

![PointOverFill](images/pointover_fill.png)

### PointerOverStroke

The `PointerOverStroke` property sets the stroke color to the mouse over area with the specified solid color in the SfRating control.

{% highlight xaml %}

    <rating:SfRating ItemsCount="5">
        <rating:SfRating.ItemContainerStyle>
            <Style TargetType="rating:SfRatingItem">
                <Setter Property="PointerOverStroke" Value="Green"></Setter>
            </Style>
        </rating:SfRating.ItemContainerStyle>
    </rating:SfRating>

{% endhighlight %}

![PointOverStroke](images/pointover_stroke.png)

### PointerOverStrokeThickness

The `PointerOverStrokeThickness` property sets the stroke thickness to the mouse over area with the specified value in the SfRating control.

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

### Height

You can set the height of each SfRatingItem using the `Height` property.

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

To set same height to each SfRatingItem, use the `ItemContainerStyle` property.

{% highlight xaml %}

    <rating:SfRating Value="4" ItemsCount="10" >
        <rating:SfRating.ItemContainerStyle>
            <Style TargetType="rating:SfRatingItem">
                <Setter Property="Height" Value="12"></Setter>
            </Style>
        </rating:SfRating.ItemContainerStyle>
    </rating:SfRating>

{% endhighlight %}

![SfRating item normal height](images/equal_height.png)
