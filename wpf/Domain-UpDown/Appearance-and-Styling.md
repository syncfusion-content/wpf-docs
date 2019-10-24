---
layout: post
title: Appearance and Styling | DomainUpDown | wpf | Syncfusion
description: appearance and styling
platform: wpf
control: DomainUpDown
documentation: ug
---

# Appearance and Styling

## Spin animation

Items will spin up or down with smooth transition. The transition can be disabled using the EnableSpinAnimation property.

{% tabs %}
{%highlight xaml%}

<syncfusion:SfDomainUpDown x:Name="domain"
                         HorizontalAlignment="Center"
                         VerticalAlignment="Center"
                         Width="200" EnableSpinAnimation="True"/>

{%endhighlight%}
{% endtabs %}

## Accent brush

The AccentBrush property is used to decorate the hot spots of a control with a solid color. 

{% tabs %}
{%highlight xaml%}

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
{% endtabs %}
