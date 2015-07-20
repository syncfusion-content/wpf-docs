---
layout: post
title: Customize-the-marker-for-specific-data-point
description: customize the marker for specific data point
platform: wpf
control: Sparkline
documentation: ug
---

### Customize the marker for specific data point

We can customize the marker for specific data point with custom template for LineSparkline and AreaSparkline, in order to customize the marker we need to inherite the MarkerTemplateSelector class and override the SelectTemplate method.

[XAML]

   <Syncfusion:SfLineSparkline x:Name="sparkline" MarkerVisibility="Visible" ItemsSource="{Binding UsersList}" YBindingPath="NoOfUsers" >

            <Syncfusion:SfLineSparkline.MarkerTemplateSelector>

                <local:CustomMarkersTemplateSelector MarkerHeight="10" MarkerWidth="10"/>

            </Syncfusion:SfLineSparkline.MarkerTemplateSelector>

        </Syncfusion:SfLineSparkline>



[C#]

     public class CustomMarkersTemplateSelector : MarkerTemplateSelector

    {

        protected override DataTemplate SelectTemplate(double x, double y)

        {

            if (y == MaximumY)    

        {

                DataTemplate markerTemplate = Application.Current.Resources["markerTemplate"] as DataTemplate;

                return markerTemplate;

            }

            else

                return base.SelectTemplate(x, y);

        }

    }

Following is the snapshot for custom marker position,

{{ '![C:/Users/ApoorvahR/Desktop/12.png](Customize-the-marker-for-specific-data-point_images/Customize-the-marker-for-specific-data-point_img1.png)' | markdownify }}
{:.image }


