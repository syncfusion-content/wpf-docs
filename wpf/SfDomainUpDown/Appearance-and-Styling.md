---
layout: post
title: Appearance-and-Styling
description: appearance and styling
platform: wpf
control: DomainUpDown
documentation: ug
---

# Appearance and Styling

## Spin Animation

Items will spin up or down with smooth transition. The transition can be disabled using the EnableSpinAnimation property.

{%highlight xml%}

[XAML]



<syncfusion:SfDomainUpDown x:Name="domain"

                                 HorizontalAlignment="Center"

                                 VerticalAlignment="Center"

                                 Width="200" EnableSpinAnimation="True"/>


{%endhighlight%}

## Accent Brush

The AccentBrush property is used to decorate the hot spots of a control with a solid color. 

{%highlight xml%}

[XAML]



<Page xmlns:editors="clr-namespace:Syncfusion.Windows.Controls.Input;assembly=Syncfusion.SfInput.Wpf">

    <Grid>



        <editors:SfDomainUpDown x:Name="domainUpDown"

                               HorizontalAlignment="Center"

                               VerticalAlignment="Center"

                               Width="200" 

                              AccentBrush="Black"

                              Value="James">

        </editors:SfDomainUpDown >



    </Grid>

</Page>

{%endhighlight%}



