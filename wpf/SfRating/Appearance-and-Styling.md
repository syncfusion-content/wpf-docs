---
layout: post
title: Appearance-and-Styling
description: appearance and styling
platform: wpf
control: Rating
documentation: ug
---

# Appearance and Styling

### RatedFill

The RatedFill property fills the rated area with the specified solid color in the Rating control.

{%highlight xaml%}

[XAML]



<editors:SfRating ItemsCount="5" Value="2">

            <editors:SfRating.ItemContainerStyle>

                <Style TargetType="editors:RatingItem">

                    <Setter Property="RatedFill" Value="Green"/>

                </Style>

            </editors:SfRating.ItemContainerStyle>

</editors:SfRating>

{%endhighlight%}

![][C:/Users/ApoorvahR/Desktop/7.png](Appearance-and-Styling_images/Appearance-and-Styling_img1.png)



### PointerOverFill

The PointerOverFill property fills the mouse over area with the specified solid color in the Rating control.

{%highlight xaml%}

[XAML]



<editors:SfRating ItemsCount="5" Value="2">

            <editors:SfRating.ItemContainerStyle>

                <Style TargetType="editors:RatingItem">

<Setter Property="PointerOverFill" Value="Green"/>

                </Style>

            </editors:SfRating.ItemContainerStyle>

</editors:SfRating>


{%endhighlight%}


![](Appearance-and-Styling_images/Appearance-and-Styling_img2.png)



### RatedStroke

RatedStroke sets the stroke for the rated area with the specified solid color in the Rating control.

{%highlight xaml%}

[XAML]



<editors:SfRating ItemsCount="5" Value="2">

            <editors:SfRating.ItemContainerStyle>

                <Style TargetType="editors:RatingItem">

                    <Setter Property="RatedStroke" Value="Green"/>

                </Style>

            </editors:SfRating.ItemContainerStyle>

</editors:SfRating >


{%endhighlight%}


![](Appearance-and-Styling_images/Appearance-and-Styling_img3.png)



### RatedStrokeThickness

RatedStrokeThickness sets the stroke thickness for the rated area with the specified value in the Rating control.

{%highlight xaml%}

[XAML]



<editors:SfRating ItemsCount="5" Value="2">

            <editors:SfRating.ItemContainerStyle>

                <Style TargetType="editors:RatingItem">

                    <Setter Property="RatedStroke" Value="Green"/>

<Setter Property="RatedStrokeThickness" Value="2"/>

                </Style>

            </editors:SfRating.ItemContainerStyle>

</editors:SfRating>


{%endhighlight%}

![](Appearance-and-Styling_images/Appearance-and-Styling_img4.png)


### PointerOverStroke

PointerOverStroke sets the stroke for the mouseover area with the specified solid color in the Rating control.

{%highlight xaml%}

[XAML]



<editors:SfRating ItemsCount="5" Value="2">

            <editors:SfRating.ItemContainerStyle>

                <Style TargetType="editors:RatingItem">

<Setter Property="PointerOverStroke" Value="Green"/>

                </Style>

            </editors:SfRating.ItemContainerStyle>

</editors:SfRating>


{%endhighlight%}


![](Appearance-and-Styling_images/Appearance-and-Styling_img5.png)



### PointerOverStrokeThickness

PointerOverStrokeThickness sets the stroke thickness for the mouseover area with the specified value in the Rating control.

{%highlight xaml%}

[XAML]



<editors:SfRating ItemsCount="5" Value="2">

            <editors:SfRating.ItemContainerStyle>

                <Style TargetType="editors:RatingItem">

                    <Setter Property="PointerOverStroke" Value="Green"/>

<Setter Property="PointerOverStrokeThickness" Value="2"/>

                </Style>

            </editors:SfRating.ItemContainerStyle>

</editors:SfRating>

{%endhighlight%}

![](Appearance-and-Styling_images/Appearance-and-Styling_img6.png)



### UnratedFill

The UnratedFill property fills the unrated area with the specified solid color in the RatingControl.

{%highlight xaml%}

[XAML]



<editors:SfRating ItemsCount="5" Value="2">

            <editors:SfRating.ItemContainerStyle>

                <Style TargetType="editors:RatingItem">

<Setter Property="UnratedFill" Value="Green"/>

                </Style>

            </editors:SfRating.ItemContainerStyle>

</editors:SfRating >

{%endhighlight%}

![](Appearance-and-Styling_images/Appearance-and-Styling_img7.png)



### UnratedStroke

UnratedStroke sets the stroke for the unrated area with the specified solid color in the Rating control.

{%highlight xaml%}


[XAML]



<editors:SfRating ItemsCount="5" Value="2">

            <editors:SfRating.ItemContainerStyle>

                <Style TargetType="editors:RatingItem">

<Setter Property="UnratedStroke" Value="Green"/>

                </Style>

            </editors:SfRating.ItemContainerStyle>

</editors:SfRating >

{%endhighlight%}

![](Appearance-and-Styling_images/Appearance-and-Styling_img8.png)



### UnratedStrokeThickness

UnratedStrokeThickness sets the stroke thickness for the unrated area with the specified value in the Rating control.

{%highlight xaml%}

[XAML]



<editors:SfRating ItemsCount="5" Value="2">

            <editors:SfRating.ItemContainerStyle>

                <Style TargetType="editors:RatingItem">

                    <Setter Property="UnratedStroke" Value="Green"/>

<Setter Property="UnratedStrokeThickness" Value="2"/>

                </Style>

            </editors:SfRating.ItemContainerStyle>

</editors:SfRating >

{%endhighlight%}

![](Appearance-and-Styling_images/Appearance-and-Styling_img9.png)



> _Note: The above properties are available in RatingItem. To set this property, use the ItemContainerStyle property of Rating._



### Height

You can set the Height of each SfRatingItem by using Height property. 

{%highlight xaml%}

XAML

<syncfusion:SfRating Height="50" VerticalAlignment="Center" HorizontalAlignment="Center" 

                             VerticalContentAlignment="Center" Value="3">

<syncfusion:SfRatingItem Height="20"/>

                    <syncfusion:SfRatingItem Height="18"/>

                    <syncfusion:SfRatingItem Height="16"/>

                    <syncfusion:SfRatingItem Height="14"/>

                    <syncfusion:SfRatingItem Height="12"/>

                </syncfusion:SfRating>

{%endhighlight%}

![](Appearance-and-Styling_images/Appearance-and-Styling_img10.png)



To set same Height for each SfRatingItem, you can use the ItemContainerStyle.

{%highlight xaml%}

XAML

<syncfusion:SfRating Height="50" Width="300" ItemsCount="10" Value="4">

<syncfusion:SfRating.ItemContainerStyle>

                        <Style TargetType="syncfusion:SfRatingItem">

<Setter Property="Height" Value="12"/>

                        </Style>

                    </syncfusion:SfRating.ItemContainerStyle>

                </syncfusion:SfRating>


{%endhighlight%}

![](Appearance-and-Styling_images/Appearance-and-Styling_img11.png)





