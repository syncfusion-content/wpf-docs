---
layout: post
title: Appearance-and-Styling
description: appearance and styling
platform: wpf
control: Rating
documentation: ug
---

# Appearance and Styling

RatedFill

The RatedFill property fills the rated area with the specified solid color in the Rating control.

[XAML]



<editors:SfRating ItemsCount="5" Value="2">

            <editors:SfRating.ItemContainerStyle>

                <Style TargetType="editors:RatingItem">

                    <Setter Property="RatedFill" Value="Green"/>

                </Style>

            </editors:SfRating.ItemContainerStyle>

</editors:SfRating>



{{ '![C:/Users/ApoorvahR/Desktop/7.png](Appearance-and-Styling_images/Appearance-and-Styling_img1.png)' | markdownify }}
{:.image }


PointerOverFill

The PointerOverFill property fills the mouse over area with the specified solid color in the Rating control.

[XAML]



<editors:SfRating ItemsCount="5" Value="2">

            <editors:SfRating.ItemContainerStyle>

                <Style TargetType="editors:RatingItem">

<Setter Property="PointerOverFill" Value="Green"/>

                </Style>

            </editors:SfRating.ItemContainerStyle>

</editors:SfRating>



{{ '![](Appearance-and-Styling_images/Appearance-and-Styling_img2.png)' | markdownify }}
{:.image }


RatedStroke

RatedStroke sets the stroke for the rated area with the specified solid color in the Rating control.

[XAML]



<editors:SfRating ItemsCount="5" Value="2">

            <editors:SfRating.ItemContainerStyle>

                <Style TargetType="editors:RatingItem">

                    <Setter Property="RatedStroke" Value="Green"/>

                </Style>

            </editors:SfRating.ItemContainerStyle>

</editors:SfRating >





{{ '![](Appearance-and-Styling_images/Appearance-and-Styling_img3.png)' | markdownify }}
{:.image }


RatedStrokeThickness

RatedStrokeThickness sets the stroke thickness for the rated area with the specified value in the Rating control.

[XAML]



<editors:SfRating ItemsCount="5" Value="2">

            <editors:SfRating.ItemContainerStyle>

                <Style TargetType="editors:RatingItem">

                    <Setter Property="RatedStroke" Value="Green"/>

<Setter Property="RatedStrokeThickness" Value="2"/>

                </Style>

            </editors:SfRating.ItemContainerStyle>

</editors:SfRating>



{{ '![](Appearance-and-Styling_images/Appearance-and-Styling_img4.png)' | markdownify }}
{:.image }


PointerOverStroke

PointerOverStroke sets the stroke for the mouseover area with the specified solid color in the Rating control.

[XAML]



<editors:SfRating ItemsCount="5" Value="2">

            <editors:SfRating.ItemContainerStyle>

                <Style TargetType="editors:RatingItem">

<Setter Property="PointerOverStroke" Value="Green"/>

                </Style>

            </editors:SfRating.ItemContainerStyle>

</editors:SfRating>





{{ '![](Appearance-and-Styling_images/Appearance-and-Styling_img5.png)' | markdownify }}
{:.image }


PointerOverStrokeThickness

PointerOverStrokeThickness sets the stroke thickness for the mouseover area with the specified value in the Rating control.

[XAML]



<editors:SfRating ItemsCount="5" Value="2">

            <editors:SfRating.ItemContainerStyle>

                <Style TargetType="editors:RatingItem">

                    <Setter Property="PointerOverStroke" Value="Green"/>

<Setter Property="PointerOverStrokeThickness" Value="2"/>

                </Style>

            </editors:SfRating.ItemContainerStyle>

</editors:SfRating>



{{ '![](Appearance-and-Styling_images/Appearance-and-Styling_img6.png)' | markdownify }}
{:.image }


UnratedFill

The UnratedFill property fills the unrated area with the specified solid color in the RatingControl.

[XAML]



<editors:SfRating ItemsCount="5" Value="2">

            <editors:SfRating.ItemContainerStyle>

                <Style TargetType="editors:RatingItem">

<Setter Property="UnratedFill" Value="Green"/>

                </Style>

            </editors:SfRating.ItemContainerStyle>

</editors:SfRating >



{{ '![](Appearance-and-Styling_images/Appearance-and-Styling_img7.png)' | markdownify }}
{:.image }


UnratedStroke

UnratedStroke sets the stroke for the unrated area with the specified solid color in the Rating control.

[XAML]



<editors:SfRating ItemsCount="5" Value="2">

            <editors:SfRating.ItemContainerStyle>

                <Style TargetType="editors:RatingItem">

<Setter Property="UnratedStroke" Value="Green"/>

                </Style>

            </editors:SfRating.ItemContainerStyle>

</editors:SfRating >



{{ '![](Appearance-and-Styling_images/Appearance-and-Styling_img8.png)' | markdownify }}
{:.image }


UnratedStrokeThickness

UnratedStrokeThickness sets the stroke thickness for the unrated area with the specified value in the Rating control.

[XAML]



<editors:SfRating ItemsCount="5" Value="2">

            <editors:SfRating.ItemContainerStyle>

                <Style TargetType="editors:RatingItem">

                    <Setter Property="UnratedStroke" Value="Green"/>

<Setter Property="UnratedStrokeThickness" Value="2"/>

                </Style>

            </editors:SfRating.ItemContainerStyle>

</editors:SfRating >



{{ '![](Appearance-and-Styling_images/Appearance-and-Styling_img9.png)' | markdownify }}
{:.image }


> _Note: The above properties are available in RatingItem. To set this property, use the ItemContainerStyle property of Rating._



Height

You can set the Height of each SfRatingItem by using Height property. 

XAML

<syncfusion:SfRating Height="50" VerticalAlignment="Center" HorizontalAlignment="Center" 

                             VerticalContentAlignment="Center" Value="3">

<syncfusion:SfRatingItem Height="20"/>

                    <syncfusion:SfRatingItem Height="18"/>

                    <syncfusion:SfRatingItem Height="16"/>

                    <syncfusion:SfRatingItem Height="14"/>

                    <syncfusion:SfRatingItem Height="12"/>

                </syncfusion:SfRating>



{{ '![](Appearance-and-Styling_images/Appearance-and-Styling_img10.png)' | markdownify }}
{:.image }


To set same Height for each SfRatingItem, you can use the ItemContainerStyle.

XAML

<syncfusion:SfRating Height="50" Width="300" ItemsCount="10" Value="4">

<syncfusion:SfRating.ItemContainerStyle>

                        <Style TargetType="syncfusion:SfRatingItem">

<Setter Property="Height" Value="12"/>

                        </Style>

                    </syncfusion:SfRating.ItemContainerStyle>

                </syncfusion:SfRating>



{{ '![](Appearance-and-Styling_images/Appearance-and-Styling_img11.png)' | markdownify }}
{:.image }




