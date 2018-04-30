---
layout: post
title: Getting Started | DomainUpDown | wpf | Syncfusion
description: getting started
platform: wpf
control: DomainUpDown
documentation: ug
---

# Getting Started

 Namespace:  Syncfusion.Windows.Controls.Input
 Assembly:  Syncfusion.SfInput.WPF (in Syncfusion.SfInput.WPF.dll)

The following code sample shows how to create the DomainUpDown from code-behind and XAML:

{%tabs%}

{%highlight xaml%}

<Page xmlns:editors="clr-namespace:Syncfusion.Windows.Controls.Input;assembly=Syncfusion.SfInput.Wpf">
<Grid>
<editors:SfDomainUpDown x:Name="domainUpDown"
                       HorizontalAlignment="Center"
                       VerticalAlignment="Center"
                       Width="200"/>
</Grid>
</Page>

{%endhighlight%}

{%highlight c#%}

SfDomainUpDown domainUpDown = new SfDomainUpDown();

{%endhighlight%}

{%endtabs%}
